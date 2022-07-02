---
layout: default
title: Protection
nav_order: 875
nav_exclude: true
---
# Protection
{: .no_toc}

- TOC
{:toc}


## How to retrieve language specific video'?
<img align="right" src="./img/applicaster-di-plugin.png" width="200">
*This is NOT yet available.*


A language tag, also known as the 'locale', consists of a 2-3 letter base language tag that indicates a language, optionally followed by the country or regions variant by '-', e.g. 'en-US' or 'fr-CA'. 

1. Add the Applicaster DI Plugin to your project
1. Add an [ISO 2 letter language  code]() as Tag according to format `lang:{country code}` on JW Player media items that are only available in specific country. E.g. `lang:nl-BE`.

The system will query the [playlist API](https://developer.jwplayer.com/jwplayer/reference/playlists) using tags.

It will filter on: 
- the base language the operating system, e.g `en`
- the regions variant of the operating system, e.g `en-US
