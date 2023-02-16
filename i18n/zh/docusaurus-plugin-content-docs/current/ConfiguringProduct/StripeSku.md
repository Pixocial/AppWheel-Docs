---
sidebar_position: 1
title: Stripe Product Setup
id: stripe-sku
---

# Stripe Sku Configuration

## Add Products and Prices in Stripe

Add a product price in Stripe and copy the price code

![2-1](/img/stripePayments/pricing-en.png)

## Add Skus in AppWheel

To complete purchases through AppWheel, you must add SKUs first .
You must fill in the Price ID with the price copied from Stripe, otherwise you will not be able to proceed with the next step of purchasing a subscription. If there are multiple SKUs which cannot be purchased simultaneously, you will also
need to configure a group.

![2-3](/img/stripePayments/create_sku.png)

## Add Entitlements in AppWheel

With AppWheel, it is recommended that entitlements be used to map the relationships between SKUs and user entitlements; for example, plans with monthly payments and plans with annual payments correspond to the same member entitlements.
**At the same time, you can do cross-queries of orders in apps under the same entitlements, making it possible to do cross-terminal purchases as needed.**

[Read More](/ConfiguringProduct/entitlements)