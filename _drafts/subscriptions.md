---
layout: default
title: Subscriptions
nav_order: 1300
---

# Subscriptions

## How to make video specific offers?
By default a subscription gives viewers access to all videos. The subscription is checked at the moment of play. 

It is possible to link an specific offer to an video by adding the custom field: `productIds` to the video and enter the product ids according the following format `productIds: <vendor-prefix>:<offerid>, <vendor-prefix>:<offerid>`. For example: `cleeng:S916977979_NL, adobe:123456`

For Cleeng the product id is the `id` of the offer. 

| Vendor/System       | Prefix | Product Id      | Example              | Comment                                                           |
|---------------------|--------|-----------------|----------------------|-------------------------------------------------------------------|
| Cleeng              | cleeng | Id of the offer | cleeng:S916977979_NL | Subscripton offers start with `s` and transaction offers with `t` |
| Adobe TV everywhere | adobe  |                 |                      |                                                                   |
|                     |        |                 |                      |                                                                   |




## How to TVOD only offer
By starting the value with an exclamation mark `!` only the TVOD offers are accepted. E.g. `!cleeng:S916977979_NL, adobe:123456`

