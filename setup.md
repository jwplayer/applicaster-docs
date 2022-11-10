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

<br />
<hr />

## Requirements

| Item | Information
| --- | --- |
| Applicaster Zapp environment | Contact your Applicater representative |
| JWP Analytics token | Contact your JWP representative<br /><br />See: [Analytics](https://jwplayer.github.io/applicaster-docs/analytics.html) |
| JWP API Credentials | 1. From your [API Credentials page](https://dashboard.jwplayer.com/account/api-credentials), scroll down to the **v1 API Credentials** section.<br />2. Click **Show Credentials** in the row of the relevant **PROPERTY NAME**.<br />3. Copy both the **Key** and **Secret**.<br /><br />If you are connecting multiple properties for your OTT apps, be sure to copy the API credentials for each property. |
| OTT App entitlement for a JWP account | Contact your JWP representative |

<br />
<hr />

## Implementation
1. Securely provide your JWP API credentials to your Applicaster Customer Success representative. The representative will set up middleware (Firebase) to enable communication between JWP and Applicaster. Once the middleware has been set up, you should be given the base URL, for example: `https://zapp-706-jw-player-demo.web.app`.
2. <a href="https://docs.applicaster.com/integrations/jw-endpoints" target="_blank">Register the base URL</a> as an endpoint in Applicaster. <br /><br /> <img src="./img/jw-endpoint.png" width="1024"><br /><br />
3. Provide your JWP analytics token to your Applicaster Customer Success representative. Each platform can only contain and report to one analytics token.
4. (Samsung, LG) Ask your JWP representative to enable in-manifest subtitles.<br /><br />The video players used in Samsung and LG require the language attributes to be exposed within the manifest. Since JWP HLS streams expose only the language name, a  viewer will not be able to choose another subtitle. Your JWP representative can adjust this for you.<br /><br /><em>JWP internal instructions: Create a SERV ticket titled 'Enable in-manifest subtitles' that includes the account ID and property ID. (Reference: [SERV-10412](https://jwplayer.atlassian.net/browse/SERV-10412))</em><br /><br />
5. (Roku) Ask your JWP representative to enable Trickplay.<br /><br />Trickplay is a particular way of sharing preview images during fast-forward and rewind operations. Roku requires this feature to be enabled for each of your JWP properties. Your JWP representative can enable this for you.<br /><br /><em>JWP internal instructions: Create a SERV ticket titled 'Enable HLS Trickplay' that includes the account name and property IDs. (Reference: [SERV-11610](https://jwplayer.atlassian.net/browse/SERV-11610))</em><br /><br />
6. Enable the subscription management system, e.g.  <a href="https://publisher.support.cleeng.com/hc/en-us/articles/4417301124252-Go-Live-Checklist" target="_blank">Cleeng</a>.
7. Set default metadata, create property-level <a href="https://docs.jwplayer.com/platform/docs/vdh-manage-default-custom-parameters" target="_blank">default custom parameters</a> that are automatically added to all new videos uploaded through your JWP dasboard. **All parameters are case-sensitive**.<br /><br />By default, the video title and video description will be displayed.<br /><br />
8. (Live Events) Set the `publish_start_date_offset_hours` in Broadcast Live (BCL) to ensure events become available in Applicaster feeds, before the scheduled start date. Contact your JWP representative.

## Import playlists as feeds
1. <a href="https://docs.jwplayer.com/platform/docs/vdh-upload-videos" target="_blank">Add videos</a> to your JWP library.
2. <a href="https://docs.jwplayer.com/platform/docs/vdh-playlist-overview" target="_blank">Create a manual or dynamic playlist</a> with the videos that viewers can watch in the Applicaster apps.
3. Copy the manual or dynamic playlist ID to a text file.
4. <a href="https://docs.jwplayer.com/platform/docs/vdh-playlist-overview" target="_blank">Create a search playlist</a>. 
5. Copy the search playlist ID to a text file.
6. Register the <a href="https://docs.applicaster.com/integrations/jw-endpoints/#create-a-simple-playlist-feed" target="_blank">manual or dynamic playlist</a> and the <a href="https://docs.applicaster.com/integrations/jw-endpoints/#create-a-search-feed" target="_blank">seach playlist</a> as feeds in Zapp.
7. <a href="https://docs.jwplayer.com/platform/docs/advertising-schedule-ad-breaks" target="_blank">Create an ad schedule.</a>
8.  Copy the ad schedule ID and append it to the registered (manual or dynamic) feeds in Zapp: `?adId={scheduleId}`. Do not append the ad schedule ID to the search playlist feed.<br /><br /><img src="./img/feeds.png" width="1024">

<!-- pending:
- JW Watchlist ID - to lookup favorites and continue watching

Where can I learn how the app UI structure is built in front end:
Quick Brick app structure | Applicaster Docs 

https://docs.applicaster.com/using-zapp/qb-app-structure/. Requires the OTT Apps entitlement. 
--> 
