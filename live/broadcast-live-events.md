---
layout: default
title: Broadcast Live Events
nav_order: 700
nav_exclude: false
parent: Live
---
# Broadcast Live Events
{:.no_toc}

- TOC
{:toc}

## DISCLAIMER
This page explains functionality that is not fully developed and tested yet.

## Introduction
JW Player offers different types of live services:
- Broadcast Live 24x7
- Broadcast Live Events
- Instant Live 

This article describes how to implement Broadcast Live Events

## Broadcast Live Events in JW Player and Applicaster
<img align="right" src="../img/broadcast-live-stream-parameters.png" width="250">
Broadcast Live Events are represented as media items in the JW Dashboard. Those media items can be grouped into JW Player playlists and this can be registered as feed in Applicaster

Broadcast Live will automatically update the fields in JW Player. The following fields are important
- `VCH.EventState` goes through the following states:`PRE_LIVE` > `LIVE_UNPUBLISHED` > `LIVE_PUBLISHED` > `INSTANT_VOD` > `VOD_PUBLIC`
- `VCH.ScheduledStart` in ISO 8601 format
- `VCH.ScheduledEnd` in ISO 8601 format

Applicaster will assing a video type based on the fields:
|Zapp Video Type|Conditions||
|`live-future`| Stream is in future based on `VCH.ScheduledStart`|
|`live`||

| Zapp Video Type | Conditions | Comments |  
|----|----|----|---|---|
| `live-future`|`VCH.ScheduledStart` is in the future  |   n/a |      
| `live`| `VCH.ScheduledStart`is in the past and `VCH.ScheduledEnd`in the future   |  t.b.d  |   
|       |  `VCH.EventState` is `LIVE_PUBLISHED`  |to handle last-minute manual override of the scheduled time   |   
| `live-vod`| `VCH.EventState` is `INSTANT_VOD` or `VOD_PUBLIC` |  to handle last-minute manual override of the scheduled times  |   


   - The stream is live based on`VCH.ScheduledStart` and `VCH.ScheduledEnd`, this will ensure the stream will be playable
   - Or when the stream is live based on`VCH.EventState` is `LIVE_PUBLISHED`, to handle last-minute manual override of the scheduled time. 
- `live-vod` whe:  
    - The stream is live when its ended based on `VCH.ScheduledEnd`
    - OR when VCH.EventState is `INSTANT_VOD` or ‘VOD_PUBLIC’, to handle last-minute manual override of the scheduled times 

Notes
- It takes a few minutes before updates propagate in Applicaster apps due to caching
- Other fields added to the JW Player Dashboard or MAPI will not get overwritten

## Create a live and upcoming shelf
<img align="right" src="../img/live-and-upcoming-shelf.png" width="350">
1. Create a playlist in JW Player that contain your live events 
2. Create a feed in Applicaster, and filter it on PRE_LIVE, LIVE_UNPUBLISHED and LIVE_PUBLISHED using parameter`?media_filtering=VCH.EventState:PRE_LIVE%2CVCH.EventState:LIVE_UNPUBLISHED%2CVCH.EventState:LIVE_PUBLISHED&media_filtering_mode=any`
3. Add a list component in Applicaster and link it to the newly created  feed
4. Set autorefresh on 60 seconds to deal with VCH.EventState changes
6. Ensure the videos with type `live-future` link to a video landing page *WITHOUT a player*. See here
6. Ensure the videos with type `live` link to a video landing page *WITH a player*. See here
 
## Create a video-on-demand shelf of live events
<img align="right" src="../img/live-vod-shelf.png" width="350">
Live events will automatically become VOD streams in Broadcast Live 
1. Create a playlist in JW Player that contain your live events
1. Create a feed in Applicaster, and filter it `INSTANT_VOD` or `VOD_PUBLIC`  using parameter `?media_filtering=VCH.EventState:PRE_LIVE%2CVCH.EventState:LIVE_UNPUBLISHED&media_filtering_mode=any`
1. Add a list component in Applicaster and link it to the newly created  feed
1. Set autorefresh on 60 seconds to deal with VCH.EventState changes
6. Ensure the videos with type `live-vod` link to a video landing page *WITH a player*. See here

## Grouping multiple live streams on a dedicated page
<img align="right" src="../img/live-events-grouped.png" width="450">
1. Create a playlist representing the grouped live streams
1. Create a media item for the event to group the individual shows for an event together. 
- This media item asset has no content, it will contain a thumbnail, metadata, and a reference to the playlist to display. 
  -  To create the dummy media item upload a placeholder video into the JW Dashboard. For example, you could enter http://foo.com/bar.mp4. The actual URL is not important. For DRM properties, you need a short (e.g. 1 second) video. 
  -  The title, thumbnail, and description set on this video will represent the event. 
  -  Add custom parameters that will contain the playlist id hosting the individual playlist.  
      - key: 'playlistId'
      - value: Id of the playlist, e.g. `0w1ITloK`
  
## Promoting live & VOD content in a single list
Instead of using a `media_filtering` attribute, you use the `exclude_media_filtering` attribute. 
`?exclude_media_filtering=VCH.EventState:PRE_LIVE%2CVCH.EventState:LIVE_UNPUBLISHED%2CVCH.EventState:INSTANT_VOD%2CVCH.EventState:VOD_PUBLIC&exclude_media_filtering_mode=any`

Ensure you handle the `live`, `live-future` and ‘live-vod’ video types as described above.
