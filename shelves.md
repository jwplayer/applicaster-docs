---
layout: default
title: Shelves
nav_order: 100
nav_exclude: false
---
# Shelves
{: .no_toc }

1. TOC
{:toc}

## What are shelves? 
<img align="right" src="./img/shelves.png" width="200">
Shelves highlight the most relevant videos and are a proven way of increasing engagement. They are visualized in rows of typically 20-40 items and typically 

Example shelves
- New in Drama
- Popular
- Scifi
- New releases

There are some special shelves:
- Featured shelf: highlight special videos, typically manually curated and visualized in the top of the homepage
- Favorite shelf: a list of videos a user likes to watch in the future. 
- Continue watching shelf:  a list of videos a user has not completed yet. 

See screenshots

## Adding shelves
You can build shelves with components in Applicaster Zapp studio. The contents of a shelf are coming from a JW Playlist.

Steps in more detail: 
1. Create a JW playlist containing the items you want to show in the shelf.  
1. Register the playlist as a feed in Applicaster. See here
1. Create a group in Zapp Studio
1. Assign the feed as the datasource to the group
1. Add a title header using the group info component.  The title will come JW Playlist playlist name
1. Place an horizontal list inside the group component.

Tips
- It is possible to override the JW Player Playlist title using a URL parameter feedTitle. E.g.`feedTitle=Popular Drama`
<img src="./img/shelf-in-studio.png">


## Popular videos shelf 
To add the most popular content in the beginning of the row make sure to use a [dynamic playlist](https://support.jwplayer.com/articles/create-a-dynamic-playlist) which is sorted on ‘Most played first”.

## Newly published shelf
To add the new  content in the beginning of the row make sure to use a [dynamic playlist](https://support.jwplayer.com/articles/create-a-dynamic-playlist) which is sorted on ‘Most recently published”.

<!--
Because you watched’ shelf
Grab the most recently completed movie and put its MediaID in the Related videos feed.-->

## Favorites shelf 
https://docs.applicaster.com/using-zapp/favourites/#introduction 

Note that syncing favorites anc continue watching across devices is not supported at this time. 


## Continue watchting shelf 
https://docs.applicaster.com/using-zapp/continue-watching 

Note that syncing favorites anc continue watching across devices is not supported at this time. 

