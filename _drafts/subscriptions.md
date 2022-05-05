---
layout: default
title: Subscriptions
nav_order: 1300
---

# Subscriptions

## How to make video specific offers?
By default a subscription gives viewers access to all videos. The subscription is checked at the moment of play. 

It is possible to link an specific offer to an video by adding the custom field: `productIds` to the video and enter the productIds according the following format `productIds: <vendor>:<offerid>, <vendor>:<offerid>`. For example: `cleeng:S916977979_NL, adobe:123456`

For Cleeng the product id is the `id` of the offer. 

| Vendor/System      | Prefix | Example              | Comment                                                                   |   |
|--------------------|--------|----------------------|---------------------------------------------------------------------------|---|
| Cleeng             | cleeng | cleeng:S916977979_NL | Subscripton offers can be recognized by `s` and transaction offers by `t` |   |
| Adobe TV everywher | adobe  |                      |                                                                           |   |
|                    |        |                      |                                                                           |   |



## How to TVOD only offer
By starting the value with an exclamation mark `!` only the TVOD offers are accepted. E.g. `!cleeng:S916977979_NL, adobe:123456`

