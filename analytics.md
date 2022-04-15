---
layout: default
title: Analytics
nav_order: 800
---
# Analytics
{: .no_toc}

- TOC
{:toc}

## How does JW Analytics work in Applicaster? 
Applicaster has a JW Analytics Plugin that feeds events to the [JW OTT Ping Interface](https://github.com/jwplayer/ott-web-app/blob/develop/docs/features/video-analytics.md)

The plugin sends 'pings' to JW Player endpoint when
- Video has been loaded
- While a video is played (every x seconds)
- When an advertisement is shown

The parameters send to JW Player include:
- The video being watched
- The device and operation systems of the user
- The application (version) of the user
- The `analytics id` belonging to the JW customer environment

Full details of the JW OTT Ping Interface can be found [here](https://github.com/jwplayer/ott-web-app/blob/develop/docs/features/video-analytics.md)

## How to set up JW analytics?
The JW plugin needs to be enabled in Applicaster:
1. Retrieve the JW token from the JW account manager or solution engineer.
1. Add the JW Analytics plugin from the gallery
1. Insert the JW token provided by the JW AM/SE and save
1. Build the app so the changes will take effect.

 *Applicaster uses the same analytics token for all platforms (iOS/Android etc.). 

## How to access JW analytics in Applicaster? 
For all OTT Apps, JW Player tracks a suite of video engagement analytics. Analytics needs to be enabled per customer.

We offer the following reporting on analytics data
- [OTT reports in the JW dashboard](https://support.jwplayer.com/articles/create-ott-apps-reports) (minutes watched, unique viewers, ad impressions, plays)
- [Reporting API](https://developer.jwplayer.com/jwplayer/docs/analytics-getting-started)
- Play Sessions Data Export (s3 bucket of aggregated play session data), which can be arranged by a JW Player Account Manager

## Which values is Applicaster sending?
All the required field of the  [JW OTT Ping Interface](https://github.com/jwplayer/ott-web-app/blob/develop/docs/features/video-analytics.md). As well as `oaid` App User ID if configure appropriately. 

Applicaster is not sending the following values:
- `ofv` Device firmware version. The Zapp platform doesn't have access to this value.
- `oos` OS Language. The Zapp platform doesn't have access to this value.
- `oiid` App Install Instance ID. There isn't any id that remains stable between installations. 


## How can I analyze traffic on a user basis? 
The applicaster plug in sends the `oaid` App User ID, which can be used to analyze traffic per user, instead of per session. 

You need to have a proper the `User identity storage key` on the plugin setting. See how to setup 

Note that the user level data is only accessible using the Play Sessions Data Export.

For OAuth Applicaster can only share the 'access_token'. The access token is a [jwt](https://jwt.io/) provided by the Identity Provider. It can can be decoded and could include user information.

## Does Applicaster support other analytics systems?
Yes. See the Applicaster Plugin Directory in your account.
