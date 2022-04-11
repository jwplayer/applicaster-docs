---
layout: default
title: Setup
nav_order: 50
nav_exclude: false
---

# Setup
{: .no_toc}

- TOC
{:toc}

## Intro
Follow the steps in this document to set up your JW Player - Applicaster environment. The first 3 steps require the help of a JW and/or Applicaster Customer Success representative. 

## 1. Create and register the JW middleware endpoint in Applicaster (required)
Applicaster needs to set up middleware (Firebase) for the communication between JW Player and Applicaster.  To set up the middleware: 
1. Retrieve the v1 API Credentials
   1. From your JW Player dashboard, click the gear next to your name > API Credentials.
   2. In the v1 API Credentials section, click SHOW CREDENTIALS next to a property name.
   3. Copy the `key` and the `Secret`.
2. Share them with the Applicaster Customer Success representative for the creation of the middleware in a secure way
3. Wait until you get the base URL back: e.g. `https://zapp-706-jw-player-demo.web.app`. 
4. Registering the URL as an endpoint in Applicaster. See [here](https://docs.applicaster.com/integrations/jw-endpoints)

Note: If you need to connect multiple properties, individual endpoints need to be added for each of these properties. Each property has v1 API credentials. 

<img src="./img/jw-endpoint.png" width="1024">

## 2. Enable the JW Analytics plugin (required)
- Provide Applicaster JW analytics token. Each platform can contain and report to only one analytics token
- See [analytics](https://marcovandeveen.github.io/jwp-applicaster-docs/analytics.html)

## 3. Enable in-manifest subtitles for Samsung and LG 
The video players used in Samsung and LG require 'in-manifest subtitles': these players expect the language attributes in the manifest. JW Player HLS streams expose only the language name. As a result, the viewer will not be able to choose another subtitle.

This can be enabled on a property level. 

This can't be controlled from the dashboard yet. Ask your JW Player Account Manager or Solution Engineer to adjust this.

JW internal instructions: Create a Serv Ticket titled 'Enable in-manifest subtitles' with the account id & property id. (Reference: [SERV-10412](https://jwplayer.atlassian.net/browse/SERV-10412))

## 4. Enabling the Subscribion Mgmt system 
For Cleeng see [here](https://publisher.support.cleeng.com/hc/en-us/articles/4417301124252-Go-Live-Checklist)

For other platforms, refer to their documentation. 

## 5. Setup default metadata 
The default metadata displayed from JW platform are the title of the video and description. Additional metadata like rating, genre, cast can be defined as custom parameters. A list of advised parameters can be found in the [field catalog](https://marcovandeveen.github.io/jwp-applicaster-docs/reference/field-catalog.html). Note that parameters are case-sensitive.

These custom parameters can be pre-defined on a property level using the [default custom parameter configration](https://support.jwplayer.com/articles/manage-default-custom-parameters). These custom parameters are automatically added to all new videos uploaded through your JW Player dashboard.

## 6. Add videos to your JW library 
See [here](https://support.jwplayer.com/articles/add-videos-to-your-jw-player-library)
Make sure to assign the metadata to your videos.

## 7. Create and register JW Playlist as feeds
1. Create a manual or dynamic playlist with the videos you want to make available in the Applicaster Apps. See [here](https://support.jwplayer.com/articles/create-a-playlist)
2. Register the playlist as a feed in Applicaster Zapp. See [here](https://docs.applicaster.com/integrations/jw-endpoints)
<img src="./img/feeds.png" width="1024">

## 8. Register JW Playlist search playlist as feed 
1. Create a search playlist in JW Player. See [here](https://support.jwplayer.com/articles/create-a-playlist)
2. Register the playlist as a feed in Applicaster Zapp. 

## 9. Link JW ad schedules to your feeds 
1. [Create an ad schedule](https://support.jwplayer.com/articles/how-to-schedule-ad-breaks) in the JW Dashboard
2. Links it to your feeds by adding `?adId={scheduleId)` to the URL 

<!-- pending:
- JW Watchlist ID - to lookup favorites and continue watching

Where can I learn how the app UI structure is built in front end:
Quick Brick app structure | Applicaster Docs 

https://docs.applicaster.com/using-zapp/qb-app-structure/. Requires the OTT Apps entitlement. 
--> 
