---
layout: default
title: Subscriptions
nav_order: 1300
---

# Subscriptions

## Transactional video on demand (TVOD)
By default a subscription gives viewers access to all videos. It is possible to link an specific product id to an video. It allows viewers to buy access to an individual video, rather then the whole library. 

You can link a specific product by adding custom field: `productIds` to the video and enter the product ids according the following format `productIds: <vendor-prefix>:<product-id>, <vendor-prefix>:<product-id>`. For example: `cleeng:S916977979_NL, adobe:123456`

The values are as 
| Vendor/System       | Prefix   | Product Id      | Example                | Comment                |
| ------------------- | -------- | --------------- | ---------------------- | ---------------------- |
| Cleeng              | `cleeng` | Id of the offer | `cleeng:S916977979_NL` | See Cleeng Notes below |  
| Adobe TV everywhere | `adobe`  | n/a             |                        |                        |
| InPlayer            | n/a      |                 |                        |                        |
| MPX                 | n/a      |                 |                        |                        |

Notes
- InPlayer and MPX don't support TVOD package. 
- Adobe: simply adding `adobe`, means Authenticated Adobe viewers are granted access to the video
- Cleeng :
   -  Subscription offers start with `s` and transaction offers with `t`.
   - `_NL` is the Cleeng locale override. Cleeng automatically selects the proper locale (currency & amount). With `_NL`  you override that mechanism.

## TVOD only videos
Sometimes customers need to pay for a video, even if the customer already has a subscription. E.g. to support concepts like 'Premier Access': access to videos before they are provided to the all subscribers.

This can be done by putting an exclamation mark `!` before the value . E.g. `!cleeng:S916977979_NL`. Applicaster will ignore the global subscription ids when checking if the user is entitled to access the video. 

