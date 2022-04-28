---
layout: default
title: Video protection
nav_order: 8
nav_exclude: false
---

## How to setup geo block?
<img align="right" src="../img/applicaster-di-plugin.png" width="200">

1. Add the Applicaster DI Plugin to your project
1. Add an [ISO 2 letter country code]() as Tag according to format. `geo:{iso2CountryCode}` on JW Player media items that are only available in specific country. E.g. `geo:NL`.

Notes
- The video files (MP4) are still accessible at JW in other countries. This is not an issue as  JW URL signing is applied, so MP4 are only accessible to Applicaster apps.
- Do NOT enable to geo-blocking of JW Platform. See also below. 
- The web app using standard JW geofiltering. See here: https://support.jwplayer.com/articles/set-geoblocking-rules-for-videos  

## Why can't we use the JW player Geo blocks
JW Players [geoblocking rules](https://support.jwplayer.com/articles/set-geoblocking-rules-for-videos) automatically removes country specific media items from playlists based on the clients IP address. The 'clients' is the system to retrieves the playlist from the JW API. 

Applicaster uses [middleware component](https://jwplayer.github.io/applicaster-docs/concepts/content-delivery.html) to retrieve playlists from JW.  So the location of the Applicaster middleware determines the filter. 

See also [here](https://docs.applicaster.com/integrations/jw-endpoints/#appendix-2---geo-blocking)
