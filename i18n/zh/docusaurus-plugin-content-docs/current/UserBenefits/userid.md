---
sidebar_position: 1
title: 用户身份标识
id: user-ids
---

# 用户身份识别

用户身份是许多移动应用程序最重要的组成部分之一，AppWheel会跟踪订阅状态并与用户ID关联，通过SDK和API的方式提供查询。

AppWheel支持程序提供自定义的用户ID，也支持匿名的ID，还支持匿名用户ID到自定义ID的订阅状态迁移。

# 使用匿名用户ID

如果您在实例化 AppWheel SDK 时未提供 AppUserid，AppWheel 将为您生成一个新的随机 AppUserid 并将其缓存在设备上。如果用户删除并重新安装应用程序，将生成一个新的随机 ID。

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

# 使用登录用户ID初始化AppWheel

大多数App都有自己的登录流程和用户系统，可以选择将登录后获取的用户唯一标识（AppUserid）在初始化SDK时进行绑定，此后进行的任何购买订单都将关联到该用户ID上，如将[Athena](https://docs.pixocial.io/athena/docs/intro)
作为应用程序用户账号系统，可以把`openid`作为用户ID上传到AppWheel。

使用登录用户ID拥有额外的好处

- 当用户删除并重新安装您的应用程序时 - 使用相同的应用程序用户 ID 将确保他们仍然可以访问之前开始的订阅而无需通过[恢复购买](/Restoring_Purchases)。
- 当用户在多台设备上登录时 - 您可以兑现在任何其他设备上购买的订阅。
- 当用户在多个平台（IOS,Android,Web或PC）登录相同项目下的多款App时，也可以兑现在任何其他平台上购买的订阅。

如果您在应用启动时拥有自己的应用用户ID，则可以在实例化时将其传递给AppWheel。

<Tabs>
 <TabItem value="Java" label="Java" default>

```Java
Billing.configure(context,"appId","secret").setAppUserId("appUserId").build();
```

  </TabItem>
  <TabItem value="Kotlin" label="Kotlin">

```Kotlin
Billing.configure(context, "appid", "secret").setAppUserId("appUserId").build()
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

# 匿名用户到登录用户的权益迁移

如果您的应用再启动后不能马上获取到登录用户ID，或者应用在经过好几个迭代版本后才决定要上用户系统，AppWheel也支持匿名用户到登录用户的订阅状态迁移，不过存在以下情况需要特别注意

- 订阅的迁移是通过[恢复购买](/Restoring_Purchases)的方式实现的，因此只支持iOS应用商店和Google Play Store的订阅
- 使用Stripe作为支付平台的应用不支持迁移，因为Stripe应用必须提供登录用户ID才能完成订阅
- 订阅迁移是可重复性的动作，在提供登录用户ID后，执行恢复购买将在AppWheel后台将订阅和新用户ID绑定，因此要注意保持订阅状态的刷新。

# 跨应用程序和平台共享订阅

同一AppWheel项目中的应用程序共享相同的登录用户ID命名空间，这意味着它们也共享订阅。在同一项目的不同应用程序中登录同一用户ID的用户将有权访问相同的权利。这允许在不同应用程序之间共享订阅状态，甚至在不同平台上也是如此。

**请注意，匿名应用用户ID无法跨应用和平台共享订阅状态，因此您需要通过自己的身份验证系统使用自定义应用用户ID进行标识。**

[更多请看](/sharing_subscriptions)

