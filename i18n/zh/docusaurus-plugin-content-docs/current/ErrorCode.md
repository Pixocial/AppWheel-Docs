---
sidebar_position: 101 
title: 错误码 
id: Error Code
---


import Tabs from '@theme/Tabs'; 
import TabItem from '@theme/TabItem';

<Tabs>
  <TabItem value="Android" label="Android" default>

|  Error Code | explanation  | Suggestions|
|  ----  | ----  |---- |
| -3  | service timeout | check google play service |
| -1  | google service disconnected | check google play service |
| 0  | success | success|
| 1  | user canceled|user canceled|
| 2  | service unavailable |check google play service|
| 3  | billing unavailable |check google play service|
| 5  | developer error | check google play service|
| 6  | unknown error | unknown error |
| 7  | item already owned |item already owned|
| 100  | server verify error | AppWheel server error|
| 101  | SERVER VERIFY PURCHASE NO PERMISSION | Order failed the backend verification (illegal order) |
| 103  | SERVER USER NOT ATTACH | init failed |

  </TabItem>
  <TabItem value="iOS" label="iOS">


|  Error Code | Message | Suggestions|
|  ----  | ----  |---- |
|  0 | unknown error |unknown error |
|  1 | client invalid |client invalid|
|  2 | payment cancelled |user cancelled|
|  3 | payment invalid |payment invalid|
|  4 | pyament no allowed |pyament no allowe|
|  5 | store product not available | store product not available |
|  11 | invalid offer identifier | make sure your offer id is legal|
|  13 | invalid signature | have you upload p8 file to AppWheel|
|  14 | missing offer params | missing offer params|
| 30000 | NoReceipt Data On Device | NoReceipt Data On Device,you can restore|
| 30001 | InvalidRawData | AppWheel server error|
| 30005 | No Item In Receipt | purchase error， No Item In Receipt |
| 30006 | No Subscription In Receipt | purchase error，No Subscription In Receipt |
| 30007 | Subscription Expired In Receipt | purchase error，Subscription Expired In Receipt|
| 30010 | Invalid Product Type | set illegal product type when purchase|
| 30011 | Initialization Error | init error |
| 30013 | Error in Parsing get_ios_retry_period api  | request get_ios_retry_period api error|
| 30014 | Product Error | set illegal product when purchase |
| 30016 | Request OfferCode Product Error | set illegal product when request offercode |
| 30017 | Request Stripe Order Error | request stripe ordder error|


  </TabItem>
  <TabItem value="Stripe" label="Stripe">

|  Error Code   | Message  |    Suggestions|
|  ----  | ----  | ---- |
| 205001  | ErrAwPurchaseSkuIncomplete | complete sku info |
| 205002  | ErrAwPurchaseStripeApi | goto  [Stripe Error](https://stripe.com/docs/error-codes)  |
| 205003  | ErrAwPurchaseSameGroupProduct | select another sku  |
| 205004  | ErrAwPurchaseUserIncomplete | init user before |
| 205005  | ErrAwPurchaseOrderNotExist | check orderId |
| 205006  | ErrAwPurchaseCheckoutNotExist | None |
| 205007  | ErrAwPurchaseSkuNotSameGroup | select another sku  |

  </TabItem>
</Tabs>