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
// 服务不可用/不支持
int SERVICE_UNAVAILABLE = 2;
int BILLING_UNAVAILABLE = 3;
int ITEM_UNAVAILABLE = 4;
int DEVELOPER_ERROR = 5;
int ERROR = 6;
int ITEM_ALREADY_OWNED = 7;
int ITEM_NOT_OWNED = 8;

// 后台校验请求异常
int SERVER_VERIFY_ERROR = 100;
// 订单后台校验未通过（订单不合法）
int SERVER_VERIFY_PURCHASE_NO_PERMISSION = 101;
// 用户在后台没有关联成功
int SERVER_USER_NOT_ATTACH = 103;
```

  </TabItem>
  <TabItem value="iOS" label="iOS">


```Object-C
    AWErrorTypeUnknown = 0,
    
    AWErrorTypeClientInvalid = 1,
    AWErrorTypePaymentCancelled = 2,
    AWErrorTypePaymentInvalid = 3,
    AWErrorTypePaymentNotAllowed = 4,
    AWErrorTypeStoreProductNotAvailable = 5,
    
    AWErrorTypeInvalidOfferIdentifier = 11,
    AWErrorTypeInvalidOfferPrice = 12,
    AWErrorTypeInvalidSignature = 13,
    AWErrorTypeMissingOfferParams = 14,
    
    AWErrorTypeAPISecretError = 10000,
    AWErrorTypeAPICertError = 10001,
    AWErrorTypeClientParamError = 10002,
    AWErrorTypeSqlExecuteError = 10100,
    AWErrorTypeDBDataError = 10101,
    AWErrorTypeRedisConnectError = 10200,
    
    AWErrorTypeAppStoreConnectError = 20000,
    
    AWErrorTypeSubOfferSubscriptionError = 20001,
    AWErrorTypeSubOfferSubscriptionExpired = 20002,
    AWErrorTypeSubOfferCancelSubInfoError = 20003,
    AWErrorTypeSubOfferParamsEmpty = 20004,
    AWErrorTypeSubOfferGenerateSignatureError = 20005,
    
    AWErrorTypeNoReceiptDataOnDevice = 30000,
    AWErrorTypeInvalidRawData = 30001,
    AWErrorTypeNothingToDecrypt = 30002,
    AWErrorTypeFailedToDecrypt = 30003,
    AWErrorTypeDataDecryptedNotInJSON = 30004,
    AWErrorTypeNoItemInReceipt = 30005,
    AWErrorTypeNoSubscriptionInReceipt = 30006,
    AWErrorTypeSubscriptionExpiredInReceipt = 30007,
    AWErrorTypePurchaseItemError = 30008,
    
    AWErrorTypeInvalidProductIdentifier = 30009,
    ///商品类型错误
    AWErrorTypeInvalidProductType = 30010,
    /// 初始化错误
    AWErrorTypeInit = 30011,
    /// 未知的错误(网络错误啊之类的)
    AWErrorTypeUnknow = 30012,
    /// 解析get_ios_retry_period接口出错
    AWErrorTypeRetryPeriod = 30013,

```

  </TabItem>
</Tabs>