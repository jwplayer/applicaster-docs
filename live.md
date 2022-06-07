---
layout: default
title: Live
nav_order: 700
nav_exclude: false
---
# Live Video
{: .no_toc}

- TOC{:toc}

## How to show Broadcast Live streams in Applicaster?
<img align="right" src="./img/broadcast-live-stream-parameters.png" width="250">
Broadcast Live streams are represented as media items in the JW Dashboard. Those media items can be grouped into JW Player playlists and there shown as feeds in Applicaster.

Broadcast Live will automatically update the fields in JW Player.The following fields are important
- VCH.EventState.  A regular live event goes through the following states:`PRE_LIVE` > `LIVE_UNPUBLISHED` > `LIVE_PUBLISHED` > `INSTANT_VOD` > `VOD_PUBLIC`.

- VCH.ScheduledStart
- VCH.ScheduledEnd 

## Creating a playlist with live streams
1. Create a dynamic playlist for anything with the tag `live` in your JW Dashboard account.
1. On the [DAPI endpoint](https://developer.jwplayer.com/jwplayer/reference/get_v2-playlists-playlist-id) use the `exclude_media_filtering` query parameter to filter on `VCH.EventState` and exclude what you don't want to be shown.

e.g.  Only `LIVE_PUBLISHED` content will have the following query params:
```
?exclude_media_filtering=VCH.EventState:PRE_LIVE%2CVCH.EventState:LIVE_UNPUBLISHED%2CVCH.EventState:INSTANT_VOD%2CVCH.EventState:VOD_PUBLIC&exclude_media_filtering_mode=any&exclude_tags=&page_limit=100&tags=Live
```

## Grouping together live streams
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

## Opening live streams in a seperate target windo
Coming soon.

## How to setup EPG?
See [Applicaster documentation](https://applicaster.zendesk.com/hc/en-us/articles/360041871512-Create-an-EPG-like-program-list-with-existing-components-in-QB-Mobile)
