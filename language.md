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
There are 3 ways of supporting viewers with a different language than the source video
1. Subtitles
2. Alternate audio tracks, also known as ['dubbing'](https://en.wikipedia.org/wiki/Dubbing)
3. Language specific videos 


## Adding subtitles to videos
See [JW documentation](https://support.jwplayer.com/articles/learn-about-captions)

## Adding alternate audio tracks 
See [JW documentation](https://support.jwplayer.com/articles/add-alternate-audio-tracks)

## Language specific videos
<img align="right" src="./img/applicaster-di-plugin.png" width="200">
**This is NOT yet available.**

A language tag, also known as the 'locale', consists of a 2-3 letter base language tag that indicates a language, optionally followed by the country or regions variant by '-', e.g. American English would be 'en-US', British English would be 'en-GB' and Canadian French would be 'fr-CA'. 

1. Add the Applicaster DI Plugin to your project
1. Add an ISO 2 letter language code to the media items in JW Player media items according to `lang:{language code}`, e.g. `lang:en-US`
1. The Applicaster middleware (pipes2) will filter the feed/playlist on the language
  - the baselanguage the operating system, e.g `lang:en`
  - the regions variant of the operating system, e.g `lang:en-US`
  - all languages, e.g `lang:all`

## Notes
- You are able to with subtitles & audio tracks. E.g. an English video, with Spanish subtitles. 
- This is differeng from geo filtering. 
- Applicaster takes into account the different formatting for language. E.g. 
   - Roku: ISO 639-2 Code and `_` as divider. E.g. `en_US`
   - Apple: ISO 639-2 Code and `-` as divider. E.g. `en-US`

<!--
Todo: explain geo vs language selection 
Todo: when to apply what? 
 - Subtitles
 - Audio tracks for dubbing
 - Language based: if your show is availble multiple language. E.g an English and Spanish video. You get two media items in JW Player.  E.g. a baby video. We are not able to correlate the videos belonging to each other. 
Todo: You can have one playlist with all items. And filter out the video out the videos which are language specifc. 
-->
