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


## How to apply geo blocking?
<img align="right" src="./img/applicaster-di-plugin.png" width="200">

1. Add the Applicaster DI Plugin to your project
1. Add an [ISO 2 letter country code]() as Tag according to format `geo:{iso2CountryCode}` on JW Player media items that are only available in specific country. E.g. `geo:NL`.
1. Make sure you have [URL signing](https://docs.jwplayer.com/platform/docs/how-to-enable-url-token-signing#url-signing-options) enabled on the JW content. This ensures only Applicaster apps can access the video files. 

Notes
- The video files (MP4) are still accessible at JW in other countries. This is not an issue as  JW URL signing is applied, so MP4 are only accessible to Applicaster apps.
- Do NOT enable to geo-blocking of JW Platform. See also below. 
- The JWP web app using standard [JW geo blocking rules](https://docs.jwplayer.com/platform/docs/protection-set-geoblocking-rules-for-videos). So need geo on web app and applicaster in combination is not possible at this moment. 
- The Applicaster geoblocking supports 'allow list': "this video can be viewed in country x,yz". It doesn't support 'block list': "this video cannot be viewed in country a, b, c.:

## Why can't we use the JW player geo blocking rules?
JW Players [geoblocking rules](https://docs.jwplayer.com/platform/docs/protection-set-geoblocking-rules-for-videos) automatically remove country specific media items from playlists based on the clients IP address. The 'client' is the system that retrieves the playlist from the JW Player API. 

Applicaster uses [middleware component](https://jwplayer.github.io/applicaster-docs/concepts/content-delivery.html) to retrieve playlists from JW.  So the location of the Applicaster middleware determines the filter. As a results viewers don't the right videos. 

See also [here](https://docs.applicaster.com/integrations/jw-endpoints/#appendix-2---geo-blocking)

## Enabling DRM
Applicaster supports DRM on JWP VOD and Live Streams.

Ask your JWP or Applicaster representative to get this enabled. 
