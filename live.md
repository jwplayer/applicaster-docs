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
Live events are like any other media item.  Once they’re created in the Broadcast Live Dashboard, media items representing those streams will appear. They can then be added to a playlist. 

### Creating a Live Playlist
- Create a dynamic playlist for anything with the tag `live`.
- On the [DAPI endpoint](https://developer.jwplayer.com/jwplayer/reference/get_v2-playlists-playlist-id) use the `exclude_media_filtering` query parameter
- Filter on custom parameter `VCH.EventState` and exclude whatever you don't want to be shown.

A regular live event goes through the following state lifecycle:`PRE_LIVE` > `LIVE_UNPUBLISHED` > `LIVE_PUBLISHED` > `INSTANT_VOD` > `VOD_PUBLIC`.

  e.g. 
    - Only `LIVE_PUBLISHED` content will have the following query params:
      - `?exclude_media_filtering=VCH.EventState:PRE_LIVE%2CVCH.EventState:LIVE_UNPUBLISHED%2CVCH.EventState:INSTANT_VOD%2CVCH.EventState:VOD_PUBLIC&exclude_media_filtering_mode=any&exclude_tags=&page_limit=100&tags=Live`

#### Grouping Together Events
- Group the individual shows for an event together by creating a dummy asset for the event. This dummy asset has no content, it will contain a thumbnail and metadata for the series to display. 
  -  To create the dummy asset upload a placeholder video into the JW Dashboard. A 1 second video is suggested as the video will not be played.
  -  The title, thumbnail, and description set on this video will represent the event. 
-  Add in custom parameters to the placeholder video.
  - These custom parameters will contain the id for the individual shows.  
    - key: ''
    - value: `mediaID`
- This dummy asset will be given a tag so that it appears in a Future Events rail. This tag will need to be removed once the event is over so it is no longer shown in the Future Events section. 
  -   tag: ''


## How to setup EPG?
See [Applicaster documentation](https://applicaster.zendesk.com/hc/en-us/articles/360041871512-Create-an-EPG-like-program-list-with-existing-components-in-QB-Mobile)
