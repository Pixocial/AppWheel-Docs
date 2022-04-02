---
sidebar_position: 10
title: Error Code
id: Error Code
---


import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

<Tabs>
  <TabItem value="Android" label="Android" default>

```java
int SERVICE_TIMEOUT = -3;
int FEATURE_NOT_SUPPORTED = -2;
int SERVICE_DISCONNECTED = -1;
int OK = 0;
int USER_CANCELED = 1;
//The service is not available/not supported
int SERVICE_UNAVAILABLE = 2;
int BILLING_UNAVAILABLE = 3;
int ITEM_UNAVAILABLE = 4;
int DEVELOPER_ERROR = 5;
int ERROR = 6;
int ITEM_ALREADY_OWNED = 7;
int ITEM_NOT_OWNED = 8;

//Backend verification request exception
int SERVER_VERIFY_ERROR = 100;
// Order failed the backend verification (illegal order)
int SERVER_VERIFY_PURCHASE_NO_PERMISSION = 101;
// User linking in the backend failed
int SERVER_USER_NOT_ATTACH = 103;
```

  </TabItem>
  <TabItem value="iOS" label="iOS">


```Object-C

     InAppPurchaseErrorTypeUnknown = 0,
    
    InAppPurchaseErrorTypeClientInvalid = 1,
    InAppPurchaseErrorTypePaymentCancelled = 2,
    InAppPurchaseErrorTypePaymentInvalid = 3,
    InAppPurchaseErrorTypePaymentNotAllowed = 4,
    InAppPurchaseErrorTypeStoreProductNotAvailable = 5,
    
    InAppPurchaseErrorTypeInvalidOfferIdentifier = 11,
    InAppPurchaseErrorTypeInvalidOfferPrice = 12,
    InAppPurchaseErrorTypeInvalidSignature = 13,
    InAppPurchaseErrorTypeMissingOfferParams = 14,
    
    InAppPurchaseErrorTypeAPISecretError = 10000,
    InAppPurchaseErrorTypeAPICertError = 10001,
    InAppPurchaseErrorTypeClientParamError = 10002,
    InAppPurchaseErrorTypeSqlExecuteError = 10100,
    InAppPurchaseErrorTypeDBDataError = 10101,
    InAppPurchaseErrorTypeRedisConnectError = 10200,
    
    InAppPurchaseErrorTypeAppStoreConnectError = 20000,
    
    InAppPurchaseErrorTypeSubOfferSubscriptionError = 20001,
    InAppPurchaseErrorTypeSubOfferSubscriptionExpired = 20002,
    InAppPurchaseErrorTypeSubOfferCancelSubInfoError = 20003,
    InAppPurchaseErrorTypeSubOfferParamsEmpty = 20004,
    InAppPurchaseErrorTypeSubOfferGenerateSignatureError = 20005,
    
    InAppPurchaseErrorTypeNoReceiptDataOnDevice = 30000,
    InAppPurchaseErrorTypeInvalidRawData = 30001,
    InAppPurchaseErrorTypeNothingToDecrypt = 30002,
    InAppPurchaseErrorTypeFailedToDecrypt = 30003,
    InAppPurchaseErrorTypeDataDecryptedNotInJSON = 30004,
    InAppPurchaseErrorTypeNoItemInReceipt = 30005,
    InAppPurchaseErrorTypeNoSubscriptionInReceipt = 30006,
    InAppPurchaseErrorTypeSubscriptionExpiredInReceipt = 30007,
    InAppPurchaseErrorTypePurchaseItemError = 30008,
    
    InAppPurchaseErrorTypeInvalidProductIdentifier = 30009,
    ///Product Type Error
    InAppPurchaseErrorTypeInvalidProductType = 30010,
    /// /Initialization Error
    InAppPurchaseErrorTypeInit = 30011,
    /// Unknown Error (Network connection and more)
    InAppPurchaseErrorTypeUnknow = 30012,
    /// Error in Parsing get_ios_retry_period Interface 
    InAppPurchaseErrorTypeRetryPeriod = 30013,

```

  </TabItem>
  <TabItem value="Stripe" label="Stripe">

```Object-C

     ErrAwPurchaseSkuIncomplete = 205001
     ErrAwPurchaseStripeApi = 205002
     ErrAwPurchaseSameGroupProduct = 205003
     ErrAwPurchaseUserIncomplete = 205004
     ErrAwPurchaseOrderNotExist = 205005
     ErrAwPurchaseCheckoutNotExist = 205006
     ErrAwPurchaseSkuNotSameGroup = 205007
     
```

  </TabItem>
</Tabs>