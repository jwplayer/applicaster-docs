---
layout: default
title: Live
nav_order: 700
nav_exclude: false
---
# Live Video
{:.no_toc}

- TOC{:toc}

## How to show Broadcast Live streams in Applicaster?
<img align="right" src="./img/broadcast-live-stream-parameters.png" width="250">
Broadcast Live streams are represented as media items in the JW Dashboard. Those media items can be grouped into JW Player playlists and there shown as feeds in Applicaster.

Broadcast Live will automatically update the fields in JW Player.The following fields are important
- `VCH.EventState` which goes through the following states:`PRE_LIVE` > `LIVE_UNPUBLISHED` > `LIVE_PUBLISHED` > `INSTANT_VOD` > `VOD_PUBLIC`.
- `VCH.ScheduledStart` in ISO 8601 format
- `VCH.ScheduledEnd` in ISO 8601 format

## Showing a live streams in your application
*Coming Soon*
When they go live: `live`
IF VCH.ScheduledStart < Now() AND VCH.ScheduledEnd > Now ()   OR VCH.ScheduledEnd = NULL
ELSE IF VCH.EventState  =  LIVE_PUBLISHED

## Showing a list of live streams in your application
1. Create a playlist in JW containing the live streams
   - Manual playlist
   - Dynamic playlist with the tag `live` in your JW Dashboard account.
1. Create a feed in Applicaster and link it to the newly created playlists
   - Use the [exclude_media_filtering](https://developer.jwplayer.com/jwplayer/reference/get_v2-playlists-playlist-id) query parameter to filter on `VCH.EventState` and exclude the streams you don't want show. 
   - E.g. only showing `LIVE_PUBLISHED` streams: `?exclude_media_filtering=VCH.EventState:PRE_LIVE%2CVCH.EventState:LIVE_UNPUBLISHED%2CVCH.EventState:INSTANT_VOD%2CVCH.EventState:VOD_PUBLIC&exclude_media_filtering_mode=any`

## Grouping together live streams on a page
<img align="right" src="./img/live-events-grouped.png" width="450">

1. Create a playlist representing the grouped live streams
   - A Manual Playlist in the JW Dashboard that will house the content in the series. Place the videos from the event series within this playlist.
1. A Dynamic Playlist, set Filter by Tag to include `future_live`
1. Create a dummy media item for the event to group the individual shows for an event together. This dummy asset has no content, it will contain a thumbnail, metadata, and a reference to the playlist to display. 
  -  To create the dummy media item  upload a placeholder video into the JW Dashboard. For example, you could enter http://foo.com/bar.mp4. The actual URL is not important. For DRM properties, you need a short (e.g. 1 second) video. 
  -  The title, thumbnail, and description set on this video will represent the event. 
  -  Add in custom parameters to the placeholder video.
  -  These custom parameters will contain the playlist id hosting the individual shows.  
      - key: 'playlistId'
      - value: Id of the playlist, e.g. `0w1ITloK`
  1 Give the asset a tag so that it appears in a future Events rail. This tag will need to be removed once the event is over so it is no longer shown in the Future Events section. 
    -   tag: 'future-live'

## Opening live streams in a seperate target window
Coming soon.

## How to setup EPG?
See [Applicaster documentation](https://applicaster.zendesk.com/hc/en-us/articles/360041871512-Create-an-EPG-like-program-list-with-existing-components-in-QB-Mobile)
