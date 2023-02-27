---
sidebar_position: 7
title: 跨平台和App共享订阅指引
id: sharing_subscriptions
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

同一AppWheel项目中的应用程序共享相同的登录用户ID命名空间，这意味着它们也共享订阅。在同一项目的不同应用程序中登录同一用户ID的用户将有权访问相同的权利。这允许在不同应用程序之间共享订阅状态，甚至在不同平台上也是如此。

*

*

请注意，匿名应用用户ID无法跨应用和平台共享订阅状态，因此您需要通过自己的身份验证系统使用自定义应用用户ID进行标识,如需匿名用户到登录用户的权益迁移请[参考](/UserBenefits/user-ids#%E5%8C%BF%E5%90%8D%E7%94%A8%E6%88%B7%E5%88%B0%E7%99%BB%E5%BD%95%E7%94%A8%E6%88%B7%E7%9A%84%E6%9D%83%E7%9B%8A%E8%BF%81%E7%A7%BB)。
**

## 前置条件

要在应用实现跨平台和App共享订阅，需要您先了解以下内容

- [项目和应用](/Projects)
- [权益和产品配置](/ConfiguringProduct/entitlements)
- [用户身份识别](/UserBenefits/user-ids)
- [购买](/MakingPurchases/stripe)
- [权益查询](/UserBenefits/api)

## 开始步骤

需要明确的是，应用商店或者支付平台间的壁垒是存在的，商品是不能跨支付平台购买的，比如在Google应用商店添加的商品，不可能用苹果应用商店账号支付；同理苹果应用商店的服务也不能通过Stripe购买。

AppWheel支持的跨平台和App共享订阅，其本质是通过识别用户身份，将同一用户在不同App中的订阅状态查询并展示的过程，在熟悉前置条件中列举的内容和明确共享的实现方式后，按照以下步骤既可以实现订阅共享：

### 1.在同一个项目下创建至少两个需要共享订阅的app，

![项目](/img/tutorial/projects.png)

### 2.商品添加到AppWheel，并配置到同一个Entitlements中

![entitlement-sku](/img/tutorial/entitlements.png)

### 3.安装SDK，并用相同的用户ID初始化SDK

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

### 4.购买订阅

利用Stripe订阅

<Tabs>
<TabItem value="javascript" label="javascript">

```javascript
// See your keys here: https://dashboard.appwheel.com/projects/ and select app
const appwheel = new AppWheel({AppID}, {platfrom}, {AppSecret})
appwheel.createPurchase({
    "appUserId": {appuserid},
    "productId": {productId},
    "successUrl": {successUrl},
    "cancelUrl": {cancelUrl}
}).then(res => res.json()).then(json => window.open(json.data.checkoutUrl))
```

  </TabItem>
</Tabs>

### 5.在另一个APP查询权益

通过SDK查询跨端权益

<Tabs>
  <TabItem value="Java" label="Java" default>

```java

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
        [self hideLoading];
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