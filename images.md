---
layout: default
title: Images
nav_order: 625
---

# Images
{: .no_toc}

- TOC
{:toc}

## Image handling in JW Player
In JW Player each media item has a thumbnail, which has the following behavior:
- A static thumbnail is automatically taken from a frame of the video in 16:9 ratio. It is possible to select another frame from the video. 
- A custom thumbnail can be uploaded with a custom aspect ratio
- The thumbnails are included in the delivery API in the Media and Playlist endpoints
- Thumbnails are made available in different widths: 320/460/640/720/1280/1920px. The aspect ratio is not adjusted.

## Image handling in Applicaster: 
When creating/modifying a cell style, you can assign the image using the `image key`. The default is: `image_base`. 

You can change the image size you desire based on the resolutions delivered on the JW feed. It is also possible to define the image. 

| JW image                            | Applicaster cell image key                           | Note                                |
|-------------------------------------|------------------------------------------------------|-------------------------------------|
| Thumbnail default                   | `image_base`                                         | Default                             |
| Thumbnail 320px width               | `images.320` or simply `320`                         |                                     |
| Thumbnail 460px width               | `images.460` or simply `460`                         | Mobile shelf best practice          |
| Thumbnail 640px width               | `images.640` or simply `640`  or `images.640`        | Mobile library & hero best practice |
| Thumbnail 720px width               | `images.720` or simply `720`                         | TV shelf best practice              |
| Thumbnail 1280px width              | `images.1280` or simply `1280`                       | TV library & hero best practice     |
| Thumbnail 1920px width              | `images.1920` or simply `1920`                       |                                     |
| Custom image with custom resolution | `images.img[LabelName]` or simply img[LabelName] |                                     |


## Uploading custom video thumbnail
To upload a custom video thumbnails with a custom aspect ratio, see [here](https://docs.jwplayer.com/platform/reference/post_videos-thumbnails-update)

## Adding additional images to a video
In some cases, a single JW video thumbnail is not enough. E.g. when you need 
- a different aspect ratio on a specific layout e.g. landscape 9:13 on Roku
- a wide banner for display in the "featured" shelf
- a thumbnail with the title as part of the image for a specific platform. 

It is possible to assign additional images to a media: 
1. Upload an alternate image in JW Player.  See [here](https://docs.jwplayer.com/platform/docs/vdh-upload-alternate-thumbnails#upload-alternative-thumbnails)
1. Add a custom parameter on the media according to the format `img[LabelName]` for example, `imgHeroRoku`. 
1. Assign the custom parameter with the image url. E.g. `https://img.jwplayer.com/v1/media/<mediaid>/images/<label>.jpg?width=<pixels>`
1. Open Aplicaster studio and assign the image key of the cell used, e.g. `extensions.imgHeroRoku`

## Motion thumbnails
Applicaster does not support motion thumbnail at the moment. 
