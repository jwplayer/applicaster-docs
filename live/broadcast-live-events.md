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

This article describes how to implement Broadcast Live Events with Applicaster Zapp. 

## Broadcast Live Events

Broadcast Live Events are represented as media items in the JW Dashboard. Those media items can be grouped into JW Player playlists and these playlist can be registered as feed in Applicaster. 

### Media Fields
<img align="right" src="../img/broadcast-live-stream-parameters.png" width="350">
Broadcast Live will automatically add and update the fields in JW Player. Manually added fields will not get overwritten by Broadcast Live. 

The important fields are `VCH.EventState`, `VCH.ScheduledStart` and `VCH.ScheduledEnd`

#### VCH.EventState
Goes through the following states:
1. `PRE_LIVE`
2. `LIVE_UNPUBLISHED` 
3. `LIVE_PUBLISHED` 
4. `INSTANT_VOD` 
5. `VOD_PUBLIC`

#### VCH.ScheduledStart and VCH.ScheduledEnd
These written in the [ISO 8601 format](https://en.wikipedia.org/wiki/ISO_8601O). 

### Zapp Video Types
Zapp assigns a video type based on the fields. It takes a few minutes before changes to media items fields are availalbe in Applicaster apps due to caching. Applicaster Zapp therefore also uses `VCH.ScheduledStart` and `VCH.ScheduledEnd` to determine when an event is live. 

| Zapp Video Type | Conditions | Comments |  
| ------ | ------ | ------ |
| `live-future` | `VCH.ScheduledStart` is in the future  |  Link to a landing page WITHOUT a player |      
| `live` | `VCH.ScheduledStart`is in the past <br> `VCH.ScheduledEnd`in the future  <br>  `VCH.EventState` is `LIVE_PUBLISHED`  | Link to a landingpage WITH a player |     
| `live-vod` | `VCH.EventState` is `INSTANT_VOD` or `VOD_PUBLIC` |  Link to a landing page WITHOUT a player  |   

<div style="display:flex; justify-content: center;"> <img src="../img/live-type-mapping.png" width="450"> </div>

## Create a live and upcoming shelf
<img align="right" src="../img/live-and-upcoming-shelf.png" width="350">

1. Create a playlist in JW Player that contain your live events 
2. Create a feed in Applicaster, and filter it on PRE_LIVE, LIVE_UNPUBLISHED and LIVE_PUBLISHED using parameter
```?media_filtering=VCH.EventState:PRE_LIVE%2CVCH.EventState:LIVE_UNPUBLISHED%2CVCH.EventState:LIVE_PUBLISHED&media_filtering_mode=any```
3. Add a list component in Applicaster and link it to the newly created  feed
4. Set autorefresh on 60 seconds to deal with VCH.EventState changes
5. Ensure the videos with type `live-future` link to a [target screen](https://jwplayer.github.io/applicaster-docs/target-screen.html) *WITHOUT a player*
6. Ensure the videos with type `live` link to a [target screen](https://jwplayer.github.io/applicaster-docs/target-screen.html) *WITH a player*
 
## Create a video-on-demand shelf of live events
<img align="right" src="../img/live-vod-shelf.png" width="350">

Live events will automatically become VOD streams in Broadcast Live 
1. Create a playlist in JW Player that contain your live events
1. Create a feed in Applicaster, and filter it `INSTANT_VOD` or `VOD_PUBLIC`  using parameter 
```?media_filtering=VCH.EventState:PRE_LIVE%2CVCH.EventState:LIVE_UNPUBLISHED&media_filtering_mode=any```
1. Add a list component in Applicaster and link it to the newly created  feed
1. Set autorefresh on 60 seconds to deal with VCH.EventState changes
1. Ensure the videos with type `live-vod` link to a video landing page *WITH a player*. See here

## Grouping multiple live streams on a dedicated page
<img align="right" src="../img/live-events-grouped.png" width="450">

1. Create a JW Player playlist representing the grouped live streams
1. Create a JW Player media item for the event to group the individual shows for an event together. 
  -  To create the dummy media item upload a placeholder video into the JW Dashboard. For example http://foo.com/bar.mp4. The actual URL is not important. For DRM properties, you need a short (e.g. 1 second) video. 
  -  The title, thumbnail, and description set on this video will represent the event. 
  -  Add custom parameters that will contain the playlist id hosting the individual playlist.  
     - key: 'playlistId'
     - value: Id of the playlist, e.g. `0w1ITloK`

## Assigning a live now badge 
t.b.d.


## Promoting live & VOD content in a single list
Instead of using a `media_filtering` attribute, you use the `exclude_media_filtering` attribute. 
```?exclude_media_filtering=VCH.EventState:PRE_LIVE%2CVCH.EventState:LIVE_UNPUBLISHED%2CVCH.EventState:INSTANT_VOD%2CVCH.EventState:VOD_PUBLIC&exclude_media_filtering_mode=any
```
Ensure you handle the `live-now`, `live-future` and `live-vod` video types as described above.
