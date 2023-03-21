---
sidebar_position: 7
title: App Sharing Subscription Guide
id: sharing_subscriptions
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

同一AppWheel项目中的应用程序共享相同的登录用户ID命名空间，这意味着它们也共享订阅。在同一项目的不同应用程序中登录同一用户ID的用户将有权访问相同的权利。这允许在不同应用程序之间共享订阅状态，甚至在不同平台上也是如此。

*

*
请注意，匿名应用用户ID无法跨应用和平台共享订阅状态，因此您需要通过自己的身份验证系统使用自定义应用用户ID进行标识,如需匿名用户到登录用户的权益迁移请[参考](/UserBenefits/user-ids#%E5%8C%BF%E5%90%8D%E7%94%A8%E6%88%B7%E5%88%B0%E7%99%BB%E5%BD%95%E7%94%A8%E6%88%B7%E7%9A%84%E6%9D%83%E7%9B%8A%E8%BF%81%E7%A7%BB)。
**

以下是简单图示
![绑定](/img/sharingSubs/sharingSubs1.jpg)

## 前置条件

要在应用实现跨平台和App共享订阅，需要您先了解以下内容

- [项目和应用](/Projects)
- [权益和产品配置](/ProjectsAndApps/Entitlements/)
- [用户身份识别](/UserBenefits/user-ids)
- [购买](/MakingPurchases/js)
- [权益查询](/UserBenefits/js)

## 开始步骤

需要明确的是，应用商店或者支付平台间的壁垒是存在的，商品是不能跨支付平台购买的，比如在Google应用商店添加的商品，不可能用苹果应用商店账号支付；同理苹果应用商店的服务也不能通过Stripe购买。

AppWheel支持的跨平台和App共享订阅，其本质是通过识别用户身份，将同一用户在不同App中的订阅状态查询并展示的过程，(<font color="red"> **所以在同一个续订周期内，当在谷歌购买订阅解锁了权益的话，后续只能通过谷歌续订继续解锁权益，不能通过苹果的续订解锁。
**</font>)
在熟悉前置条件中列举的内容和明确共享的实现方式后，按照以下步骤既可以实现订阅共享：

### 1.在同一个项目下创建至少两个需要共享订阅的app，

![项目](/img/tutorial/projects.png)

### 2.商品添加到AppWheel，并配置到同一个Entitlements中

请确保您已经完成[权益和产品配置](/ProjectsAndApps/Entitlements/)

![entitlement-sku](/img/tutorial/entitlements.png)

### 3.相同的用户ID初始化SDK

现在你已经绑定了SKU和权益，可以在项目中使用他们了，首先确保你已经安装对应平台的SDK，SDK安装：[JS](/Installation/JS.md)、[Android](/Installation/Android.md)、[iOS](/Installation/iOS.md)

(<font color="red"> **注意：只有“userId”一样才能获取到跨端的权益**</font>)

<Tabs>
  <TabItem value="Java" label="Java" default>

```Java
Billing.configure(context,"appId","secret").setAppUserId("userId").build();
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
                              uid: userId) { success, error in
      if success == false {
        // init failed,check error
      } else {
        //init success ,do something
      }
    }
    
 ///Use the following method for version 2.0.2.1 and above.
 AWPurchaseKit.configure(withAppId: appId, 
                            secret:appSecret, 
                               uid: userId) { success, error in
      if success == false {
        // init failed,check error
      } else {
        //init success ,do something
      }
    }
```

  </TabItem>

<TabItem value="javascript" label="javascript">

```javascript
const appwheel = new AppWheel({AppID}, {platfrom}, {AppSecret})
appwheel.initUser("appuserid").then(res => res.json()).then((json) => {
    console.log("初始化结果:", json)
})

```

</TabItem>

</Tabs>

### 4.购买

接下来需要在各端进行购买以此来解锁相对应的的权益

使用[JS购买](/MakingPurchases/JS.md)、[Android购买](/MakingPurchases/Android.md)、[iOS购买](/MakingPurchases/iOS.md)

### 5.查询权益

当你在任意一端已经购买了权益绑定的SKU的时候，这时候你可以在任意一端查询你已经拥有的权益从而去解锁你的VIP了

<Tabs>
  <TabItem value="Java" label="Java" default>

```Java
Market.getInstance().getStripePurchaseInfo(new StripeQueryOrderListener(){
@Override
public void onSuccess(StripePurchaseInfo info){
        //拿到权益
        List<StripeOrderModel> list=info.entitlement;
        }

@Override
public void onError(String msg){

        }
        });
```

  </TabItem>
  <TabItem value="Kotlin" label="Kotlin">

```Kotlin

Market.getInstance().getStripePurchaseInfo(object : StripeQueryOrderListener {
    override fun onSuccess(info: StripePurchaseInfo?) {
        //获取权益
        info?.entitlement
    }

    override fun onError(msg: String?) {
    }
})

```

  </TabItem>
  <TabItem value="Objective-C" label="Objective-C">

```Objective-C 
[AWPurchaseKit queryStripeOrdersWithCompletion:^(BOOL success, AWStripePurchaseInfo * _Nullable info, AWError * _Nullable error) {
    if (error) {
      //do something
        return;
    }
    //获取权益
    if (info.entitlement) {

    }
}];
```

  </TabItem>
  <TabItem value="Swift" label="Swift">

```Swift
AWPurchaseKit.queryStripeOrders { success, info, error in
    //获取权益
    info?.entitlement
}
```

  </TabItem>

 <TabItem value="javascript" label="javascript">

```javascript
const appwheel = new AppWheel({AppID}, {platfrom}, {AppSecret})
appwheel.entitlement(this.appuserid).then(res => res.json()).then((json) => {
    console.log("当前有效权益", Object.keys(json.data.entitlement))
    console.log("当前已失效权益", Object.keys(json.data.invalidEntitlement))
})

```

</TabItem>
</Tabs>