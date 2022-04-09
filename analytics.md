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
- When an adversiment is shown

The parameters send to JW Player include:
- The video being watched
- The device and operation systems of the user
- The application (version) of the user
- The `analytics id` belonging to the JW customer environment

Full details of the JW OTT Ping Interface can be found [here](https://github.com/jwplayer/ott-web-app/blob/develop/docs/features/video-analytics.md)

## How to setup JW analytics?
Provide a Applicaster Solution Engineer or Account Manager with JW Player analytics token for the property that is being added in Applicaster's platform. The JW Player analytics token can be retrieved from the JW Player account manager. 

Please note that you need to provide analytics token for each of the properties that is being used in Applicaster's platform.

Applicaster setup:
1. Add the JW Anlytics plugin from the gallery
1. Insert the JW token provided by the JW AM/SE and save
1. Build the app so the changes will take effect.

 *Applicaster the same analytics token for all platforms (iOS/Android etc).

## How to access JW analytics in Applicaster? 
For all OTT Apps, JW Player tracks a suite of video engagement analytics. Analytics needs to be enabled per customer.

We offer the following reporting on analytics data
- [OTT reports in the JW dashboard](https://support.jwplayer.com/articles/create-ott-apps-reports) (minutes watched, unique viewers, ad impressions, plays)
- [Reporting API](https://developer.jwplayer.com/jwplayer/docs/analytics-getting-started)
- Play Sessions Data Export (s3 bucket of aggregated play session data), which can be arranged by a JW Player Account Manager

## Does Applicaster support other analytics systems?
Yes. See the Applicaster Plugin Directory in your account
