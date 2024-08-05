---
layout: default
title: Protection
nav_order: 850
nav_exclude: false
---
# Protection
{: .no_toc}

- TOC
{:toc}

## How can content be protected?
Content can be protected is protected in various ways: 
- URL signing: Ensures only Applicaster Apps can access videos
- Geo blocking: Ensures videos can only be accessed in a specific country
- DRM: Ensure only entitle users can playback video

## How to apply URL Signing?
URL signing is enabled by default on the Applicaster Zapp Middleware. Signed URLs are automatically used by the middleware based on the API keys provided at the time of setup. This means URL signing can simply be enabled on the JW Platform and used within Applicaster apps. 

## How to apply geo blocking?
Applicaster Zapp supports [JW geo blocking rules](https://docs.jwplayer.com/platform/docs/protection-set-geoblocking-rules-for-videos). Applying these rules automatically removes country-specific media items from playlists based on the viewer's location. 

This feature is enabled on the latest applicaster Zapp version (check your account manager).

Note: Zapp determines the country based on the IP address of the viewer and feeds the country as a filter to JWP Delivery APIs (part of the URL signature).

## How to apply geo-blocking? (Deprecated Method)
<img align="right" src="./img/applicaster-di-plugin.png" width="200">

1. Add the Applicaster DI Plugin to your project
1. Add an [ISO 2 letter country code]() as Tag according to format `geo:{iso2CountryCode}` on JW Player media items that are only available in specific country. E.g. `geo:NL`.
1. Make sure you have [URL signing](https://docs.jwplayer.com/platform/docs/how-to-enable-url-token-signing#url-signing-options) enabled on the JW content. This ensures only Applicaster apps can access the video files. 

Notes (for the deprecated method, not applicable when using the JW Geo Blocking Rules)
- The video files (MP4) are still accessible at JW in other countries. This is not an issue as  JW URL signing is applied, so MP4 are only accessible to Applicaster apps.
- The Applicaster geoblocking supports 'allow list': "this video can be viewed in country x,yz". It doesn't support 'block list': "this video cannot be viewed in country a, b, c.:

## Enabling DRM
Applicaster supports DRM on JWP VOD and Live Streams.

Ask your JWP or Applicaster representative to get this enabled. 
