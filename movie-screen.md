---
layout: default
title: Movie screen
nav_order: 300
nav_exclude: false
---

#  Movie target screens
{: .no_toc}

1. TOC
{:toc}

## About target screens
A video target screen is where the user lands after selecting a video from a homepage or library.

Commonly used target screens  
- A movie target: that promotes a movie by giving he full details about the video, like a description, rating, duration, etc. 
- Series target. That shows the epsisodes of series. 
- Player target. See video playback

This article focuses on the first. 

## Structure of a movie target screen
A standard movie target screen consist of
1. An hero component that combines an image, texts and a call to action
1. A trailer
1. A related videos shelf

<!-- image here --> 

## Define movie metadata in JW Player
1. Make sure that you have all the meta data like MPAA Rating, Run Time the other details that you want to show added as custom parameters in JW platform.
2.  Add `movieId` as a custom field within the media item in JW Player. See the [field catalog](https://marcovandeveen.github.io/jwp-applicaster-docs/reference/field-catalog.html)
3.  Make sure you have `trailerId` as custom field In JW Player. See the [field catalog](https://marcovandeveen.github.io/jwp-applicaster-docs/reference/field-catalog.html)

Tip: Use [default custom parameters](https://support.jwplayer.com/articles/manage-default-custom-parameters). This automatically populates these values at the media level when the video gets uploaded and can be easily change afterwards. 

## Add a movie target screen as target
1. Add a movie target screen 
1. Define it a 'target' for movies with [type mapping](https://docs.applicaster.com/using-zapp/app-building-walk-through/#add-type-mapping)
1. 

<img src="./img/type-mapping.png" width="1024">

## Adding an hero component with JW Video
1. Add a video [Hero Quick Brick (`Hero QB`)](https://docs.applicaster.com/using-zapp/qb-app-structure/#heroes) component to your video target page
1. Assign a 'single video' datascoure that is linked witht the [media endpoint](https://developer.jwplayer.com/jwplayer/reference/media) of JW Player
1. Link the entry value: `extensions.movieId`. This will be used to get data from the datascource 
1  Select or create a [cell style](https://docs.applicaster.com/using-zapp/qb-app-structure/#cell-style). E.g.  'Mobile Cell 2' would have 2 labels to be assigned and is optimized for mobile phones. 
1. Link the cell.labels to values in JW Player by using the key `extensions.{custom-parameter-key}` 

<img src="./img/video-target-in-studio.png" width="1024">
<img src="./img/cell-field-mapping.png" width="1024">

## Add a trailer?
1. Add a Group Component and correlating UI components
1. Assign the datascoure that fetches single video from JW Player
1. Insert the entry value: `extensions.trailerId`
1. Assign a [cell style](https://docs.applicaster.com/using-zapp/qb-app-structure/#cell-style) and save

## How to add a recommendations shelf?
- A recommendations / related videos shelf (group with group title and horizontal lists)

## Defining multiple target screens
You can make multiple video target screens. E.g. a 'movie target' and a 'show  target'. With [Type mapping](https://docs.applicaster.com/using-zapp/app-building-walk-through/#add-type-mapping) you can map a video type with a target screen.

The default type is video

Using Type mapping you can give types/names to your screens and "tell" Zapp to open all shows in the show screen, but featured shows to be opened on the featured-show screen.

The actual mapping in on 2 places:
Set to a given screen a type
Set the type for a given entry on the feed:
On Manual Feeds this is done on Type Mapping field
On Custom / Provided Pipes2 this is done by the developer of the data source or can be overwritten via the feed manager in Zapp using: ?overrideType=<new type>

  
