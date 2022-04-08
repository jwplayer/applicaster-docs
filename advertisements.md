---
layout: default
title: Advertisements
nav_order: 900
nav_exclude: false
---
# Advertisements
{: .no_toc}

1. TOC
{:toc}

## How to setup ads? 
Setup ads as you do normally within the ad schedule and select Google IMA as the ad client and VMAP is recommended over VAST. Once setup the client just needs to use the ad schedule ID which will be entered in the feed during setting up the playlists. 

Note that ads for now are only attached at the playlist level unlike JWplayer platform where it is attached at the player level.

Below is a step by step walkthrough:
1. Setup ads as usual by selecting GoogleIMA as ad client.
2. Add your adtags in there as preroll,midroll or Vmap, whatever applicable
3. Save the ad schedule and grab the adid from there.
4. Go in Zapp (applicasters) platform and in the playlist data feed that you want to show ads, add the schedule id to ?adId={scheduleId)
5. Make sure you add the Google IMA plugin form the plugin gallery, if it wasn’t added before you’ll need to build the version again for the plugin to be enabled.

## Ad Macros - General support
 Below are the macros supported today by Applicaster:
 
 |         | JW Macros         | Supported |
|---------|-------------------|-----------|
| General | __player-height__ | Yes       |
|         | __player-width__  | Yes       |
|         | __timestamp__     | Yes       |
|         | __random-number__ | Yes       |
| App     | __device-id__     | Yes       |
|         | __app-bundle__    | Yes       |
|         | __app-name__      | Yes       |
| Content | __item-title__    | Yes       |
|         | __item-mediaid__  | Yes       |
|         | __item-file__     | Yes       |
|         | __item-duration__ | Yes       |
|         | __item-tags__     | Yes       |
|         | __item-{custom}__ | Yes       |

## Ad Macros - FreeWheel
Below are the macros supported for freewheel ad server:

| FW macros                             | Type         | Supported            |
|---------------------------------------|--------------|----------------------|
| pvrn=(page_view_random)               | Dynamic      | No                   |
| vprn=(video_player_random)            | Dynamic      | No                   |
| vip=(end_user_ip_address)             | Dynamic      | No                   |
| (custom_video_asset_id)               | Dynamic      | __item-mediaid__     |
| vrdu=(video_request_duration)         | Dynamic      | __item-duration__    |
| _fw_did=(device_id)                   | Dynamic      | __device-id__        |
| _fw_vcid2=190200:(unique_customer_id) | Dynamic      | No                   |
| csid=(Platform)                       | Dynamic      | Yes                  |
| slid=(slot_custom_id)                 | Static Value | Entered by publisher |
| mind=(slot_minimum_duration)          | Static Value | Entered by publisher |
| maxd=(slot_maximum_duration)          | Static Value | Entered by publisher |
