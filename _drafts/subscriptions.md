---
layout: default
title: Subscriptions
nav_order: 1300
---

# Subscriptions

JWP and Applicaster support monetisation through subscriptions. This setup allows you to restrict your video library and allow access only to registered and viewers who have purhcased a subscription.

In this guide we focus on describing the steps needed to integrate your app stores (e.g. Apple, Google) with the JWP & Applicaster systems in order to introduce the in-app subscription flow in your mobile/TV apps.

Today, until the Dashboard integration between the InPlayer and JWP is complete, this in-app integration needs to be completed using the three Dashboards, InPlayer, JWP & Applicaster.

## [InPlayer] Integrating app store with InPlayer account
This entails connecting your App store account (e.g. Apple, Google) with your InPlayer account to enable communication during the processing of in-app transactions. In essense, when a transaction is completed, the InPlayer system needs to validate with the app store that the payment has indeed occurred before granting access to the viewer. To perform this check, the InPlayer system needs specific tokens from the app store account.

This integration is different for each app store account, however it generally consists of adding specific parameters from the app store in the InPlayer settings page, and vice versa.

Specific details on each parameter for every different app store can be found on the following links:

- [Apple](https://client.support.inplayer.com/integrations/in-app-integrations/ios/#connecting-your-inplayer-account-and-app-store-connect-app-4)
- [Google](https://client.support.inplayer.com/integrations/in-app-integrations/android/#connecting-your-inplayer-and-google-play-store-accounts-4)
- [Amazon](https://client.support.inplayer.com/integrations/in-app-integrations/amazon/#connecting-your-inplayer-and-amazon-accounts-4)
- [Roku](https://client.support.inplayer.com/integrations/in-app-integrations/roku/#connecting-your-inplayer-and-roku-accounts-4)

## [InPlayer] Creating and connecting price offers
The second step is creating in-app offers, or subscription prices that would be available for purchase inside your mobile/TV apps and then connecting them with InPlayer prices. This one-to-one connection is needed to enable the successful processing of transactions and having all your transaction data inside the JWP system for full overview of the subscription revenue coming from different apps/devices.

Again, this process is twofold:
1. a product is created on the app store side
2. an asset is created in the InPlayer system and the subscription prices are added in the asset
3. each app store product is connected with the replicated subscriptio price in the InPlayer system

Specific details on how both steps can be completed for each app store account can be found on the following links*:

- [Apple](https://client.support.inplayer.com/integrations/in-app-integrations/ios/#using-an-existing-apple-ppv-purchase-or-subscription-4)
- [Google](https://client.support.inplayer.com/integrations/in-app-integrations/android/#using-an-existing-google-ppv-or-subscription-product-4)
- [Amazon](https://client.support.inplayer.com/integrations/in-app-integrations/amazon/#setting-up-a-subscription-4)
- [Roku](https://client.support.inplayer.com/integrations/in-app-integrations/roku/#using-an-existing-roku-product-4)

\* _make sure to use the **external In-App ID** when connecting the product with the price_

## [JWP] Media setup for monetisation
The final step in the process is to add metadata parameters on your JWP media items to indicate that they are available for playing only if a viewer has purchased a subscription. To do so, the following metadata parameter should be added on all your premium videos: `inplayer_id` with the value of the InPlayer asset created in the previous step. 

![image](https://github.com/matejpetrovjwp/applicaster-docs/assets/138796738/8fe2eb69-ac39-4f9e-bac8-a5c6553e7704)

Last thing to note is that if you wish specific videos to be free, meaning available without a subscription to be purchased, you need to add the tag `free` to it, as shown on the screenshot below

![image](https://github.com/matejpetrovjwp/applicaster-docs/assets/138796738/75dc775d-90a0-417c-bf40-87df99dd1ad1)


- every media should have a parameter indicating which prices are available
- every free media is marked with free

## [Applicaster] Zapp app config setup
On the Applicaster side, the Zapp application should be marked as premium, in order to automatically check for the subscription prices of the connected app store. Additionally, the app store application should be connected with the Zapp app, so the correct in-app products can be fetched and the in-app payment flow can be implemented.

