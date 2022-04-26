---
sidebar_position: 8
title: Stripe Payments
id: Query Stripe Orders
---

This document serves as a guide on how to add Stripe configuration in the AppWheel management backend and implement the use of Web/iOS/Android order interoperability.

## Configure Stripe App Profile

To support Stripe payments, you must have your own Stripe account, and also fill out the relevant information in AppWheel.

### Get a secret key in the Stripe backend

![1-1](/img/stripePayments/apikey-en.png)

### 1.2 Add the Stripe App in AppWheel
Fill in the AppWheel with the secret key obtained from the Stripe backend.


![1-2](/img/stripePayments/1-2.png)

### 1.3  Stripe Notification Configuration

![1-3](/img/stripePayments/1-3.png)
Copy the WebHook URL, create a WebHook in Stripe, and backfill the secret key signature in AppWheel and in WebHook.


![1-4](/img/stripePayments/webhooks-en.png)

## SKU Configuration
### 2.1 Add Products and Prices in Stripe
Add a product price in Stripe and copy the price code

![2-1](/img/stripePayments/pricing-en.png)

### 2.2 Add Groups in AppWheel
A group has two functions:
- It is used to control SKUs which cannot be purchased simultaneously, such as products with annual payments and products with monthly payments. Such SKUs which cannot be purchased simultaneously should be assigned to the same group.
- It is also used to control the upgrade and downgrade relationships between different SKUs, such as from Silver member to Gold member; these memberships cannot be purchased simultaneously, and at the same time they are part of the operation of upgraded plans.

![2-2](/img/stripePayments/2-2.png)

### 2.3 Add SKUs in AppWheel
To complete purchases through AppWheel, you must add SKUs first .
You must fill in the Price ID with the price copied from Stripe, otherwise you will not be able to proceed with the next step of purchasing a subscription. If there are multiple SKUs which cannot be purchased simultaneously, you will also need to configure a group.

![2-3](/img/stripePayments/2-3.png)

### 2.4 Add Entitlements in AppWheel
With AppWheel, it is recommended that entitlements be used to map the relationships between SKUs and user entitlements; for example, plans with monthly payments and plans with annual payments correspond to the same member entitlements.
At the same time, you can do cross-queries of orders in apps under the same entitlements, making it possible to do cross-terminal purchases as needed.

![2-4](/img/stripePayments/2-4.png)

## Subscription Management Interface
Subscription purchases must be done through the interface. Before calling the interface, make sure you are familiar with interface signatures.
签名规则
Host URL: https://sdk-api.appwheel.com
### 3.1 Create Subscription
Purpose: Users use this interface to create subscriptions and complete payments
path：/v1/purchase/create
method: Post
Body:

```json
{
    "appUserId":"{{appuserid}}",  //  Required,Business side customized subscriber ID
  "productId":"{{productId}}",  //  Required,SKU ID filled out in 2.3
    "successUrl":"{{SucessUrl}}", // Required,Address for redirection back to the business side after a successful purchase
    "cancelUrl":"{{CancelUrl}}", // Required,Address for redirection back to the business side after the cancellation of a purchase
  "trialPeriodDays": 3  // Optional,trial Period Days
}
```

Response
```json
{
    "code": 0,
    "message": "success",
    "data": {
        "checkoutUrl": "https://checkout.stripe.com/pay/cs_test_b1w30tabJbJnX8GMOoZVvLef1ReZ1phM6N7aRceXwezIGKa8gKFOWTakhA#fidkdWxOYHwnPyd1blpxYHZxWjA0Tlc8XXBNYGFBT1Vwa01qQFNGdmA9TmlTTnU1SkZnNWJBfFZWX0tPQjBqalc0TU9yY0xMalZAfXFSbHJqX2REPEFBNGRBbkRKMGxXc2xjcUxiaHxKPUtmNTVRRkN%2FSnBmMCcpJ2N3amhWYHdzYHcnP3F3cGApJ2lkfGpwcVF8dWAnPydocGlxbFpscWBoJyknYGtkZ2lgVWlkZmBtamlhYHd2Jz9xd3BgeCUl" //付款页面
    }
}
```


### 3.2 User Subscription Management Page
Purpose: Users can use this page to cancel or modify their subscription plans
path：/v1/purchase/customPortal
method：Post
Body:
```json
{
    "appUserId":"{{appuserid}}", // Required,Subscriber ID
    "returnUrl":"{{returnRul}}" // Required,Redirect back to the business side page
}
```


```json

Response:
{
    "code": 0,
    "message": "success",
    "data": {
        "sessionUrl": "https://billing.stripe.com/session/test_YWNjdF8xS1I5WHVIZWRESlB1bkhvLF9MTmVTZUVSaXhMVW1YZDEyU3ZZNktTT1Zyb2U1NzVy01005iaVqmkS"//管理页面
    }
}
```

### 3.3 Get Current Subscription Entitlements and Orders
Purpose: Get orders that users have purchased and their corresponding entitlements. If multiple apps have been configured in 2.4 under the same entitlements, you can go back to orders across apps.
path: /v1/subscriber/{{appuserid}}
Method: Get
Body: None
Response:

```json
{
    "code": 0,
    "message": "success",
    "data": {
        "entitlement": { // Entitlements
            "abc": { // Entitlements identifier
                "orderId": "2000000015808544", // Order ID
              "appId": 329386269, // App ID
                "productId": "com.stripe.s", // Product ID
                "productType": 2, // Product type
                "isAutoRenew": true, // Renew automatically
              "isTrialPeriod": false, // Trial period
              "platform": "ios", // Platform
                "purchaseDateMs": 1647960466000, // Time of purchase
              "expiresDateMs": 1648964066000, // Time of expiration
              "originalPurchaseDateMs": 1647942348000, // Time of original purchase
              "gracePeriodExpiresDateMs": 0, // Time of grace period expiration
                "status": 0 // Status  Order status: 0 Unpaid; 1 Paid with normal use; 2 Cancelled; 3 Expired; 4 Grace period; 5 Suspended
            }
        },
        "subscriberOrders": [
            {
                "orderId": "2000000015808544",
                "appId": 329386269,
                "productId": "com.stripe.s",
                "productType": 2,
                "isAutoRenew": true,
                "isTrialPeriod": false,
                "platform": "ios",
                "purchaseDateMs": 1647960466000,
                "expiresDateMs": 1648964066000,
                "originalPurchaseDateMs": 1647942348000,
                "gracePeriodExpiresDateMs": 0,
                "status": 0
            }
        ]
    }
}
```

## Get the order in the SDK
Here is how to get a cross-end payment order through the SDK

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

<Tabs>
  <TabItem value="Java" label="Java" default>

```Java
        Market.getInstance().getStripePurchaseInfo(new StripeQueryOrderListener() {
            @Override
            public void onSuccess(StripePurchaseInfo info) {
              //get Orders
              List<StripeOrderModel> list = info.subscriberOrders;
            }

            @Override
            public void onError(String msg) {

            }
        });
```
  </TabItem>
  <TabItem value="Kotlin" label="Kotlin">

```Kotlin

Market.getInstance().getStripePurchaseInfo(object :StripeQueryOrderListener{
            override fun onSuccess(info: StripePurchaseInfo?) {
            }

            override fun onError(msg: String?) {
            }
})

```
  </TabItem>
  <TabItem value="Objective-C" label="Objective-C">

```Objective-C 
    [AWPurchaseKit queryStripeOrdersWithCompletion:^(BOOL success, AWStripePurchaseInfo * _Nullable info, AWError * _Nullable error) {
        [self hideLoading];
        if (error) {
          //do something
            return;
        }
        if (info.orders && info.orders.count > 0) {
            //get orders
        }
    }];
```
  </TabItem>
  <TabItem value="Swift" label="Swift">

```Swift
AWPurchaseKit.queryStripeOrders { success, stripePurchaseInfo, error in
                
}
```
  </TabItem>
</Tabs>