---
layout: default
title: Video playback
nav_order: 400
nav_exclude: false
parent: Screens
---
# Video playback 
{: .no_toc}

- TOC
{:toc}

## Target screens
<img align="right" src="./img/movie-target.png" width="250">
A 'target' screen is where the user lands after selecting a video from a homepage or library.

Commonly used target screens:
- A movie target.
- Series target. 
- Player target. 

This article focuses on the player target screen 

## Create a player target screen 
1. Create a 'general content screen' 
1. Add a player, and if needed a related videos shelf
1. Define it as a 'target' for 'video' using [type mapping](https://jwplayer.github.io/applicaster-docs/type-mapping.html)

## How to add subtitles / captions?
See JW Documentation on [adding closed captions](https://docs.jwplayer.com/platform/docs/vdh-add-closed-captions). Captions will automatically appear in Applicaster Apps. 

*Subitles on Samsung and LG*
- Samsung and LG using Shaka Player. Shakaplayer needs a two-letter code entere. Entering language code in the captions editor (`srclang` field in the API). See also [Update a text track developer documentation](https://developer.jwplayer.com/jwplayer/reference/patch_v2-sites-site-id-media-media-id-text-tracks-track-id-)
- Samsung and LG require in-manifest subtitles that need to be enabled on property level. See [Setup](https://jwplayer.github.io/applicaster-docs/setup.html#3-enable-captions-for-samsung-and-lg-optional)

## Enabling casting or airplay
This is available in Applicasters platform. See for more info [applicaster documenation](https://docs.applicaster.com). Search for chromecast or airplay.

*Airplay is enabled by default on iOS apps with no further setup. Chromecast, requires clients to provide a Chromecast app ID created here:
https://cast.google.com/publish/

## How to enable “Play Next”?
JW config: when a new JW endpoint is created, pipes2 enables play next feed by default.

Applicaster:
1. Add play next plugin on your mobile/TV platform in Zapp
1. Assign the correct image key from your media items based on size. See [images](https://jwplayer.github.io/applicaster-docs/)
1. Save and build the app for changes to appear

## Offline download
Requires a custom param on the item `hqme=true`

See [Applicaster docs](https://docs.applicaster.com/using-zapp/mobile/downloads/download-and-offline/)

## Multi-lingual audio tracks
To ensure that multiple audio tracks show up in the player correctly it is neccessary for customers to set the audio track NAME in the JW dashboard (not just the language). Additionally if an Application has a language selector for the Application UI as well as an audio language selector in the player and the desire is for the default audio in the player to follow the UI language then it is neccessary to set the language of the default audio track as well which can only be managed through the create media or update media endpoints of the Management API (This can not be managed in the dashboard as yet). 

