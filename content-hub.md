---
layout: default
title: Content Hub
nav_order: 700
nav_exclude: false
parent: Screens
---
# Content Hub
{: .no_toc }

- TOC
{:toc}

## What is a content hub?
A content hub is where the desire is to have tiles on an Applicaster app driven by non-video assets in the JW platform that navigate through to screens in the app that are dynamicallt driven by the JW media asset (with playlists selected and sorted in JW). These are used to create multiple app screens that can be organised and rearranged from the JW platform without having to touch Zapp.

## Creating the ott-data "stub" media assets
Content hubs can be created from either video assets in JW (such as a match hub page from a match video asset) or from non-video assets that in JW are called ott_data.
For hubs within a video asset just upload a video and then follow the subsequent steps in this guide.
For non-video assets create a new content type with `hosting_type = ott_data`

## Selecting the content hub playlists
To enable a user to easily select content hub playlists create a new custom parameter called `playlist` that includes a comma separated list of the playlists to be shown in the page in order. For ease of editing create this as a part of the custom content type created above with `field_type: playlist_multiselect`.

## Adding the content hub playlists to the application
- Create a Zapp feed to load the hub items.
- Create a dynamic Zapp feed to load the playlists like: `https://zapp-5434-volleyball-tv.web.app/jw/playlists/{{playlistId}}`
- Preview the zapp feed, the extension `playlist` should be expanded to be `hubPlaylists` with an entry for each playlist selected.

Once confirmed you can:
- create a new Zapp screen
- map the content type to the new screen 
- Create the maximum number of rails that are to be expected 
- add the dynamic playlist feed above to each rail with the playlistID set as: `extensions.hubPlaylists.playlist1`, `extensions.hubPlaylists.playlist2` etc

