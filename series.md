---
layout: default
title: Series
nav_order: 600
parent: Screens
---
# Series
{: .no_toc}

- TOC
{:toc}

## Introduction
This page describes how to define and show series, with seasons and episodes.

## Define a series in JW (Using contentTypes)

### Create Series in JWP
Create a series media asset in JW Player [JWP Add a Series](https://docs.jwplayer.com/platform/docs/add-a-series) 

### Create Feeds in Zapp
- series/series hero: `zapp-dsp-base-url/jw/series/{{seriesId}}` 
- seasons tabs: `zapp-dsp-base-url/jw/series/{{seriesId}}/seasons`
- episodes within a season: `zapp-dsp-base-url/jw/series/{{seriesId}}/seasons/{{seasonId}}/episodes`
  - seasonId= `extensions.season_number`

If you do not use seasons here is the feed format for all episodes:

- episodes within a series: `zapp-dsp-base-url/jw/series/{{seriesId}}/episodes`
 - seriesId= `id`

### Zapp setup
For the zapp set up of a series without tabs use a playlist with a series item that uses series management
Type mapping: `series` to connect to your series screen in zapp

For the zapp set up of a series with tabs use a playlist with a series item that user series management
Type mapping: `series` to connect to your tabs season screen in zapp
Type mapping: `season` to connect to the screen to display the episode list within a season tab


## Define a series in JW (Deprecated - playlist based method)
You need:
- A media item (a.k.a. card) that links to the series playlist using `seriesId`
- A 'series' playlist that includes episodes based on a tag 
- Episodes with fields `episodeNumber` and `seasonNumber` and a tag, that includes the epsidoe in the in the series playlist

<div style="display:flex; justify-content: center;"> 
  <img src="./img/series-jw-card.png" width="600"> 
</div>
<br>
<div style="display:flex; justify-content: center;"> 
  <img src="./img/series-jw-playlist.png" width="600"> 
</div>
<br>
<div style="display:flex; justify-content: center;"> 
  <img src="./img/series-jw-episode.png" width="600"> 
</div>

## Create an all-series playlist in JW 
Create a playlist in JW Player, containing all the series. There are no special requirements.

## Create an all series screen
1. Create a all-series/shows feed using the middleware endpoint  `/jw/all-series-playlists/`. This endpoint will ensure the type to `series`
1. Create a series/shows screen pointing to the newly created feed
1. Do the type mapping to the [series target screen](https://jwplayer.github.io/applicaster-docs/target-screens.html)

<div style="display:flex; justify-content: center;"> 
  <img src="./img/series-all-feed.png" width="600"> 
</div>
<br>
<div style="display:flex; justify-content: center;"> 
  <img src="./img/series-all-screen.png" width="600"> 
</div>
<br>
<div style="display:flex; justify-content: center;"> 
  <img src="./img/series-type-mapping.png" width="600"> 
</div>

## Create an series screen
1. Create a feed for all possible seasons in your environment. E.g season 4 looks like this:  `/jw/playlists/{{playlistId}}?media_filtering=seasonNumber:4&feedTitle=Season%204`
1. Create a series/show screen containing all possible seasons
1. Ensure to enable 'Hide Component if data is empty' 

<div style="display:flex; justify-content: center;"> 
  <img src="./img/series-season-feeds.png" width="600"> 
</div>
<br>
<div style="display:flex; justify-content: center;"> 
  <img src="./img/series-show-screen.png" width="600"> 
</div>
