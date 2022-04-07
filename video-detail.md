---
layout: default
title: Video detail
nav_order: 300
nav_exclude: false
---

# Video detail page
## How to create a video detail page ?
Make sure that you have all the extra meta data like MPAA Rating, Run Time and all the other details that you want to show added as custom parameters in JWplatform.

One suggestion that we give is to have these Custom parameters (the ones you will be using on a regular basis) predefined with keys and default values at the property level, what this does is it automatically populates these values at the media level when the video gets uploaded. The values can then be changed if needed depending on the video that's being uploaded.

Once the key values are all defined, you then need to create a cell style in Applicaster and import all the keys that you want to display on the video detail page in text labels by using the key extensions.(custom-parameter-key) :

This is a one time setup for the cell style and you can keep reusing the cell styles for different screens. Once this is setup the video detailed page can look something like below:

## How to create a movie landing screen?
JW config: Make sure you have movieId as a custom field within the same movie media item. See the data dictionairy in the appendix

Applicaster:
1. Add a Group Component and correlating UI components
1. Assign the “media” dynamic playlist
1. Insert the entry value: extensions.movieId
1. Assign a cell style and save

## How to add trailers?
JW config: Make sure you have trailerId as custom field. See the field catalog in the appendix
Applicaster:
1. Add a Group Component and correlating UI components
1. Assign the “media” dynamic playlist
1. Insert the entry value: extensions.trailerId
1. Assign a cell style and save
1. (see applicaster docs for more info)(
