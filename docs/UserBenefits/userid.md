---
sidebar_position: 1
title: Identifying User
id: user-ids
---

# 识别客户

AppWheel 为不同平台上的订户状态提供了真实来源。为此，每个订阅者都有一个 App 用户 ID，可以在您的应用程序中唯一标识他们。

用户身份是许多移动应用程序最重要的组成部分之一，确保 AppWheel 跟踪的订阅状态与正确的用户相关联尤为重要。

# 匿名应用程序用户 ID

如果您在实例化 AppWheel SDK 时未提供 AppUserid，AppWheel 将为您生成一个新的随机 AppUserid 并将其缓存在设备上。

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

<Tabs>
  <TabItem value="Java" label="Java" default>

```Java
Billing.configure(context,"appId","secret").build();
```

  </TabItem>
  <TabItem value="Kotlin" label="Kotlin">

```Kotlin
Billing.configure(context, "appid", "secret").build()
```

  </TabItem>

 <TabItem value="Objective-C" label="Objective-C">

```Objective-C 
///Please use the following method for versions older than 2.0.2.1.  
[AWPurchaseKit configureWithAppId:appid 
                             uid:userId     
                      completion:^(BOOL success, AWError * _Nonnull error) {
    if (success) {
      //init success ,do something
    } else {
      // init failed,check error
    }
  }];
  
///Use the following method for version 2.0.2.1 and above.  
[AWPurchaseKit configureWithAppId:appId 
                           secret:appSecret
                              uid:userId
                       completion:^(BOOL success, AWError * _Nonnull error) {
                 if (success) {
                  //init success ,do something
                } else {
                  // init failed,check error
                }
  }];
```

  </TabItem>
  <TabItem value="Swift" label="Swift">

```Swift
///Please use the following method for versions older than 2.0.2.1.  
AWPurchaseKit.configure(withAppId: appId, 
                              uid: uid) { success, error in
      if success == false {
        // init failed,check error
      } else {
        //init success ,do something
      }
    }
    
 ///Use the following method for version 2.0.2.1 and above.
 AWPurchaseKit.configure(withAppId: appId, 
                            secret:appSecret, 
                               uid: uid) { success, error in
      if success == false {
        // init failed,check error
      } else {
        //init success ,do something
      }
    }
```

  </TabItem>

</Tabs>

# 使用自定义应用程序用户 ID 登录
