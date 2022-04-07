---
layout: default
title: Video playback
nav_order: 400
nav_exclude: false
---

1.{:toc}

# Video playback {: .no_toc}
## How does video playback happen in Applicaster for JWplayer feeds?
By default everytime a feed is setup in Applicaster there has to be a value defined, applicaster by default defines this value as Video in the feeds that is returned from JWplatform, below is an example:

<>
It is this value is what then used in Type screen definition in Applicasters Zapp platform to tell the app what screen needs to be opened for the media that has this value in it. In this case the value defined is video player which then opens the video player in the app. Below is an example of that:

## How to assign the correct image size to a cell (large image for TVs smaller for mobile)?

JW config: JW generates by default standard 16:9 images. You can override the default image, see https://support.jwplayer.com/articles/update-a-video-thumbnail 

To add additional image sizes:
1. Upload a dummy video in the media library
1. Override the default image with the aspect ratio
1. Link with a customer property on the original image. Naming best practice img[LabelName]. See also  data dictionairy in the appendix

Note: the web app doesn’t support additional images at this moment. 

Applicaster: 
When creating/modifying a cell style,in the image section you need to insert a key, the default is: image_base, change to the image size you desire based on the resolutions delivered on the JW feed. Default are: 320/460/640/720/1280/1920 OR a custom size based on the data dictionary 


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
