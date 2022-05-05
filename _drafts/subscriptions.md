---
layout: default
title: Subscriptions
nav_order: 1300
---

# Subscriptions

## Transactional video on demand (TVOD)
By default a subscription gives viewers access to all videos. It is possible to link an specific product id to an video. It allows viewers to buy access to an individual video, rather then the whole library. 

You can link a specific product by adding custom field: `productIds` to the video and enter the product ids according the following format `productIds: <vendor-prefix>:<offerid>, <vendor-prefix>:<offerid>`. For example: `cleeng:S916977979_NL, adobe:123456`

The values are as 
| Vendor/System       | Prefix | Product Id      | Example              | Comment                                                           |
|---------------------|--------|-----------------|----------------------|-------------------------------------------------------------------|
| Cleeng              | cleeng | Id of the offer | cleeng:S916977979_NL | Subscription offers start with `s` and transaction offers with `t` |
| Adobe TV everywhere | adobe  |                 |                      |                                                                   |
| InPlayer            |        |                 |                      |                                                                   |
| MPX                 |        |                 |                      |                                                                   |

## TVOD only videos
Sometimes customers need to pay for a video, even if the customer already has a subscription. E.g. to support concepts like 'Premier Access': access to videos before they are provided to the all subscribers.

This can be done by putting an exclamation mark `!` before the value . E.g. `!cleeng:S916977979_NL`. Applicaster will ignore the global subscription ids when checking if the user is entitled to access the video. 

