---
layout: default
title: Setup
nav_order: 50
nav_exclude: false
---

## What is needed
The following is needed to setup JW video consumption in Applicaster apps: 
- JW v1 API Credentials
- JW Playlist IDs
- JW Search Playlist Id
- JW Watchlist ID
- JW Analytics token

## Retrieving the v1 API Credentials
Use the following steps to locate these credentials:
1. From your JW Player dashboard, click the gear next to your name > API Credentials.
1. In the v1 API Credentials section, click SHOW CREDENTIALS next to a property name.
1. Copy the `key` and the `Secret`.
1. Share them with the Applicaster Customer Success representative

## Create JW Player Endpoint
Applicaster uses middleware (Firebase) for the communication beetween JW Player and Applicaster. This middleware will be setup by the Applicaster Customer Success representative. The customer will receive a BASE_URL like `https://zapp-706-jw-player-demo.web.app`.

## Create the playlist feeds
1. Create a search feed
1. Create a playlist feed

Detailed steps can be found [here](https://docs.applicaster.com/integrations/jw-endpoints)

## Enable JW Analytics plugin
- Provide Applicaster JW analytics token. Each platform can contain and report to only one analytics token
See. 

## Update a plugin
To update a plugin:
1. Go to Zapp Studio
1. Select the release / layout
1. Select the plugin configuration
1. Select the new version 

The developer of the data source or can be overwritten via the feed manager in Zapp using: `?overrideType=<new type>`

## Setup default meta data
The default metadata displayed from JWplatform are the title of the video and description, for any additional metadata to be displayed custom parameters need to be used, please use the best practices metadata structure mentioned in this documentand note that theseparameters arecase sensitive.

  
## Multiple properties 
If there is a use case of multiple properties please provide the V1 secret for each of the properties respectively.
- In applicaster there will then be individual End Points added for each of these properties.
