---
layout: default
title: Libraries
nav_order: 200
---

# Libraries
{: .no_toc}

1. TOC
{:toc}

## What is a library screen?
<img align="right" src="./img/library.png" width="200">

A library allows viewers to browse all videos. This in contrast with shelves, that highlight a subset of the videos. 

The standard usage is: 
- Have a  libraries per format e.g  ‘movies’, ‘shorts’, ‘shows’
- About 50-500 items per library
- 5-20 genre filters e.g ‘action’, ‘drama’, ‘comedy’

## Develop a library screen

This behavior can created as follows: 
1. Create a JW playlist containing the items you want to show in the library. 
1. Register the playlist as a feed in Applicaster. See here
1. Create a group in Zapp Studio
1. Assign the feed as the datasource to the group
1. Place an grid component inside the screen


<img src="./img/library-in-studio.png" width="768">

  <!--
## Filtering on genres 
By creating a genre screen. –>
