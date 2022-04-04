---
layout: default
title: Advertisements
nav_order: 1
---
## How to setup ads? 
Setup ads as you do normally within the ad schedule and select Google IMA as the ad client and VMAP is recommended over VAST. Once setup the client just needs to use the ad schedule ID which will be entered in the feed during setting up the playlists. Note that ads for now are only attached at the playlist level unlike JWplayer platform where it is attached at the player level.

Below is a step by step walkthrough:
# Setup ads as usual by selecting GoogleIMA as ad client.
# Add your adtags in there as preroll,midroll or Vmap, whatever applicable
# Save the ad schedule and grab the adid from there.
# Go in Zapp (applicasters) platform and in the playlist data feed that you want to show ads, add the schedule id to ?adId={scheduleId)
# Make sure you add the Google IMA plugin form the plugin gallery, if it wasn’t added before you’ll need to build the version again for the plugin to be enabled.
