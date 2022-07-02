---
layout: default
title: Language
nav_order: 875
nav_exclude: true
---
# Protection
{: .no_toc}

- TOC
{:toc}

## Langauge handling
There are two ways of handling different language
1. Subtitles and alternate audio tracks on the video
2. Language specific videos

## Adding subtitles and alternate audio tracks
See JW documentation

## Language specific videos
<img align="right" src="./img/applicaster-di-plugin.png" width="200">
**This is NOT yet available.**

A language tag, also known as the 'locale', consists of a 2-3 letter base language tag that indicates a language, optionally followed by the country or regions variant by '-', e.g. 'en-US' or 'fr-CA'. 


### OPTION 1: SIMPLE APPROACH
1. Add the Applicaster DI Plugin to your project
1. Add an [ISO 2 letter language  code]() as Tag according to format `lang:{country code}` on JW Player media items that are only available in specific country. E.g. `lang:nl-BE`.

The system will query the [playlist API](https://developer.jwplayer.com/jwplayer/reference/playlists) on: 
- the base language the operating system, e.g `lang:en`
- the regions variant of the operating system, e.g `lang:en-US` (should we do this?)
- the regions variant of the operating system, e.g `lang:all`

Todo: check language codes and formatting
- Roku: ISO 639-2 Code and `_` as divider. E.g. `en_US`
- Apple:  ISO 639-2 Code and `_` as divider. E.g. `en-US`
- Android: ...

Todo: should we use tags or custom parameters?
- Benefits of custom parameters: we can use a lookup field. 
- This is different from the GEO solution. However we want to move to the [JW native geo solution](https://support.jwplayer.com/articles/set-geoblocking-rules-for-videos) in Q4

### OPTION 2: RULE APPROACH
1. Define rules in system JW App Config / Applicaster Config
   - Rule: NL - Included: `nl-BE`, `nl-NL`, `en_US`. 
   - Rule: Belgium - Inlcuded: `nl-BE`, `fr`, ...
   - Rule: English - Excluded: `nl-BE`, ...
1. Add `languages` tot the media. E.g. `nl-BE`
1. Filter delivery API based on rules

