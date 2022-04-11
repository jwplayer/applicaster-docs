---
layout: default
title: Video playback
nav_order: 400
nav_exclude: false
---
# Video playback 
{: .no_toc}

- TOC
{:toc}

## Player 'target' screen
<img align="right" src="./img/movie-target.png" width="250">
A 'target' screen is where the user lands after selecting a video from a homepage or library.

Commonly used target screens  
- A movie target: that promotes a movie by giving he full details about the video, like a description, rating, duration, etc. 
- Series target. 
- Player target. 

This article focuses on Player target screen 

## Structure of a movie target screen
A standard movie target screen consist of:
1. An player 
1. A related videos shelf

## Define a player  screen as target
1. Create a'general content screen' 
1. Define it a 'target' for 'video' using [type mapping](https://docs.applicaster.com/using-zapp/app-building-walk-through/#add-type-mapping)

By default everytime a feed is setup in Applicaster there has to be a value defined, applicaster by default defines this value as Video in the feeds that is returned from JWplatform. 

It is this value is what then used in Type screen definition in Applicasters Zapp platform to tell the app what screen needs to be opened for the media that has this value in it. In this case the value defined is video player which then opens the video player in the app. 

<img src="./img/type-mapping.png" width="1024">

## How to add subtitles / captions?
See https://support.jwplayer.com/articles/how-to-add-closed-captions. Captions will automatically appear in Applicaster Apps. 

Please note that Samsung and LG using Shaka Player. Shakaplayer needs a two-letter code entere. Entering language code in the captions editor (srclang field in the API). See also Update a text track )

## Enabling casting or airplay
It is by available in applicasters platform. See for more info [applicaster documenation](https://docs.applicaster.com/plugin-development/30-guides/50-plugins/50-player#properties). Search for chromecast or airplay.

*Airplay is enabled by default on iOS apps with no further setup. Chromecast, requires clients to provide a chromecast app ID created here:
https://cast.google.com/publish/

## How to enable “Play Next”?
JW config: when a new JW endpoint is created, pipes2 enables play next feed by default.

Applicaster:
1. Add play next plugin on your mobile/TV platform in Zapp
1. Assign the correct image key from your media items based on size. See [images](https://marcovandeveen.github.io/jwp-applicaster-docs/)
1. Save and build the app for changes to appear

## Offline downlown
Requires a custom param on the item `hqme=true`

See [Applicaster docs](https://docs.applicaster.com/using-zapp/mobile/downloads/download-and-offline/)
