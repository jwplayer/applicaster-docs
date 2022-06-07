---
layout: default
title: Live
nav_order: 700
nav_exclude: false
---
# Live Video
{: .no_toc}

- TOC
{:toc}


## How to show Broadcast Live streams in Applicaster?
Broadcast Live streams are represented as media items in the JW Dashboard. Those media items can be grouped into playlists / Applicaster Feeds. 

Broadcast Live will automatically update the fields in JW Player.The following fields are important
- VCH.EventState
- VCH.ScheduledStart
- VCH.ScheduledEnd 

<img align="right" src="./img/broacast-live-stream-parameters.png" width="250">


### Creating a Live Playlist
- Create a dynamic playlist for anything with the tag `live` in your JW Dashboard account.
- On the [DAPI endpoint](https://developer.jwplayer.com/jwplayer/reference/get_v2-playlists-playlist-id) use the `exclude_media_filtering` query parameter
- Filter on custom parameter `VCH.EventState` and exclude what you don't want to be shown.

A regular live event goes through the following state lifecycle:`PRE_LIVE` > `LIVE_UNPUBLISHED` > `LIVE_PUBLISHED` > `INSTANT_VOD` > `VOD_PUBLIC`.

  e.g. 
    - Only `LIVE_PUBLISHED` content will have the following query params:
      ```?exclude_media_filtering=VCH.EventState:PRE_LIVE%2CVCH.EventState:LIVE_UNPUBLISHED%2CVCH.EventState:INSTANT_VOD%2CVCH.EventState:VOD_PUBLIC&exclude_media_filtering_mode=any&exclude_tags=&page_limit=100&tags=Live```

#### Grouping Together Events
- Create a Manual Playlist in the JW Dashboard that will house the content in the series. Place the videos from the event series within this playlist.
- Create a Dynamic Playlist, set Filter by Tag to include `future_live`
- Create a dummy asset for the event to group the individual shows for an event together. This dummy asset has no content, it will contain a thumbnail, metadata, and a reference to the playlist to display. 
  -  To create the dummy asset upload a placeholder video into the JW Dashboard. A 1 second video is suggested as the video will not be played.
  -  The title, thumbnail, and description set on this video will represent the event. 
  -  Add in custom parameters to the placeholder video.
  -  These custom parameters will contain the playlist id hosting the individual shows.  
      - key: 'livePlaylistId'
      - value: `playlistID`
  - Give the asset a tag so that it appears in a Future Events rail. This tag will need to be removed once the event is over so it is no longer shown in the Future Events section. 
    -   tag: 'future-live'


## How to setup EPG?
See [Applicaster documentation](https://applicaster.zendesk.com/hc/en-us/articles/360041871512-Create-an-EPG-like-program-list-with-existing-components-in-QB-Mobile)
