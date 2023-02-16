---
sidebar_position: 1
title: Entitlements
id: entitlements
---

# Entitlements

An entitlement represents a level of access, features, or content that a user is "entitled" to.

Entitlements are used to ensure a user has appropriate access to content based on their purchases, without having to manage all of the product identifiers in your app code.

Most apps only have one entitlement, unlocking all premium features. However, if you had two tiers of content such as Gold and Platinum, you would have 2 entitlements.

**A user's entitlements are shared across all apps contained within the same project.**


## Creating an Entitlement
To create a new entitlement, click Entitlements in the left menu of the Project dashboard and click + New. You'll need to enter a unique identifier for your entitlement that you can reference in your app, like "pro".

Most apps only have one entitlement, but create as many as you need. For example a navigation app may have a subscription to "pro" access, and one-time purchases to unlock specific map regions. In this case there would probably be one "pro" entitlement, and additional entitlements for each map region that could be purchased.

![setup entitlement](/img/tutorial/create_entitlement.png)

## Attaching Products to Entitlements
Once entitlements are created, you should attach products to entitlements. This lets AppWheel know which entitlements to unlock for users after they purchase a specific product.

When viewing an Entitlement, click the edit button to attach a product. If you've already added your products, you'll be able to select one from the list to attach.

![setup entitlement](/img/tutorial/attact_product_entitlement.png)

When a product that is attached to an entitlement is purchased, that entitlement becomes active for the duration of the product. Subscription products will unlock entitlements for the subscription duration, and non-consumable and consumable purchases that are attached to an entitlement will unlock that content forever.

If you have non-subscription products, you may or may not want to add them to entitlements depending on your use case. If the product is non-consumable (e.g. lifetime access to "pro" features), you likely want to attach it to an entitlement. However, if it is consumable (e.g. purchase more lives in a game) you likely do not want to add them to an entitlement.

Attaching an entitlement to a product will grant that entitlement to any customers that have previously purchased that product. Likewise, detaching an entitlement from a product will remove it for any customers that have previously purchased that product.

When designing your Entitlement structure, keep in mind that a single product can unlock multiple entitlements, and multiple products may unlock the same entitlement.

