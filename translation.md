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


A language tag, also known as the 'locale', consists of a 2-3 letter base language tag that indicates a language, optionally followed by additional subtags separated by '-'. The most common extra information is the country or region variant like 'en-US' or 'fr-CA'. 

1. Add the Applicaster DI Plugin to your project
1. Add an [ISO 2 letter language  code]() as Tag according to format `lang:{country code}` on JW Player media items that are only available in specific country. E.g. `lang:nl-BE`.
1. 


The system will query take the base language of the operating system
It will always query on language AND (if apprlicable) the region variant

To 
