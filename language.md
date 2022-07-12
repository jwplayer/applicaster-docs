---
layout: default
title: Language
nav_order: 875
nav_exclude: true
---
# Language
{: .no_toc}

- TOC
{:toc}

## Language handling
There are 3 ways of supporting different video language
1. Subtitles: 
2. Alternate audio tracks 
3. Language specific videos. 

## Adding subtitles to videos
See JW documentation

## Adding alternate audio tracks 
See JW documentation

## Language specific videos
<img align="right" src="./img/applicaster-di-plugin.png" width="200">
**This is NOT yet available.**

A language tag, also known as the 'locale', consists of a 2-3 letter base language tag that indicates a language, optionally followed by the country or regions variant by '-', e.g. 'en-US' or 'fr-CA'. 

1. Add the Applicaster DI Plugin to your project
1. Add an ISO 2 letter language  code to the media items in JW Player media items 

The pipes2 middleware will filter the feed/playlist on the language

### Tag based -
Applicaster will filter the feed/playlist on tags according to format `lang:{country code}`
- the base language the operating system, e.g `lang:en`
- the regions variant of the operating system, e.g `lang:en-US`
- all languages, e.g `lang:all`


- Drawback: unable to combine with subtitles & audio tracks. E.g. an English video, with Spanish subtitles. So it is availble for people with two languages
- This is different from the GEO solution. However we want to move to the [JW native geo solution](https://support.jwplayer.com/articles/set-geoblocking-rules-for-videos) in Q4

Todo: check language codes and formatting
- Roku: ISO 639-2 Code and `_` as divider. E.g. `en_US`
- Apple: ISO 639-2 Code and `-` as divider. E.g. `en-US`
- Android: ...

Todo: explain geo vs language selection 
Todo: when to apply what? 
 - Subtitles
 - Audio tracks for dubbing
 - Language based: if your show is availble multiple language. E.g an English and Spanish video. You get two media items in JW Player.  E.g. a baby video. We are not able to correlate the videos belonging to each other. 
Todo: You can have one playlist with all items. And filter out the video out the videos which are language specifc. 

