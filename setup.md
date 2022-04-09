---
layout: default
title: Setup
nav_order: 50
nav_exclude: false
---

# Setup
{: .no_toc}

1. TOC
{:toc}


## Create and register the JW Player Endpoint (required)
Applicaster needs to setup middleware (Firebase) for the communication beetween JW Player and Applicaster. This middleware has BASE_URL like `https://zapp-706-jw-player-demo.web.app`:

1. Retrieving the v1 API Credentials
   1. From your JW Player dashboard, click the gear next to your name > API Credentials.
   2. In the v1 API Credentials section, click SHOW CREDENTIALS next to a property name.
   3. Copy the `key` and the `Secret`.
2. Share them with the Applicaster Customer Success representative for the creation of the middleware
3. Registering the endpoint in Applicaster. See [here](https://docs.applicaster.com/integrations/jw-endpoints)

<img src="./img/jw-endpoint.png" width="1024">

## Enable JW Analytics plugin (required)
- Provide Applicaster JW analytics token. Each platform can contain and report to only one analytics token
- See [analytics](https://marcovandeveen.github.io/jwp-applicaster-docs/analytics.html)

## Creating the playlist feeds (advised)
1. Create your initialy playlist feed
1. Add the `?adId={scheduleId)`
<img src="./img/feeds.png" width="1024">
1. The developer of the data source or can be overwritten via the feed manager in Zapp using: `?overrideType=<new type>`

## Create a search feeds (advised)
1. Create a playlist feed

## Link JW ad schedules to your feeds

## Setup default meta data (advised)
The default metadata displayed from JWplatform are the title of the video and description, for any additional metadata to be displayed custom parameters need to be used, please use the best practices metadata structure mentioned in this documentand note that theseparameters arecase sensitive.

## Multiple properties 
If there is a use case of multiple properties please provide the V1 secret for each of the properties respectively.
- In applicaster there will then be individual End Points added for each of these properties.

<!-- pending:
- JW Watchlist ID - to lookup favorites and continue watching 
--> 
