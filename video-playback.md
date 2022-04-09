---
layout: default
title: Video playback
nav_order: 400
nav_exclude: false
---
# Video playback 
{: .no_toc}

1. TOC
{:toc}

## How does video playback happen in Applicaster for JWplayer feeds?
By default everytime a feed is setup in Applicaster there has to be a value defined, applicaster by default defines this value as Video in the feeds that is returned from JWplatform, below is an example:

It is this value is what then used in Type screen definition in Applicasters Zapp platform to tell the app what screen needs to be opened for the media that has this value in it. In this case the value defined is video player which then opens the video player in the app. Below is an example of that:

## How to add subtitles / captions?
See https://support.jwplayer.com/articles/how-to-add-closed-captions. Captions will automatically appear in Applicaster Apps. 

Please note that Samsung and LG using Shaka Player. Shakaplayer needs a two-letter code entere. Entering language code in the captions editor (srclang field in the API). See also Update a text track )

## Where is casting or airplay enabled in applicaster?
It is enabled in applicasters platform, if you are interested you can read it on their documentation page here:
https://docs.applicaster.com/plugin-development/30-guides/50-plugins/50-player#properties
Just search for chromecast or airplay.

*Airplay is enabled by default on iOS apps with no further setup. Chromecast, requires clients to provide a chromecast app ID created here:
https://cast.google.com/publish/

## How to enable “Play Next”?
JW config: when a new JW endpoint is created, pipes2 enables play next feed by default.
Applicaster:
Add play next plugin on your mobile/TV platform in Zapp
Assign the correct image key from your media items based on size (320/480/640)
Save and build the app for changes to appear
