# Android

## 初始化SDK
### 说明：
SDK的初始化方法，用户根据自己的情况尽早在app中初始化

java:

```java
///低于版本1.0.5.6的
// 在Application中的oncreate中初始化配置，appId为注册应用时候分配的应用id
Billing.configure(context ,"appid" , appUserId , 
new OnBillingClientSetupFinishedListener(){
    @Override
    public void onBillingSetupFinished(int billingResponseCode) {
        super.onBillingSetupFinished(billingResponseCode);
    }
});
///1.0.5.6之后
Billing.configure(context ,"appid" , secret,appUserId , 
new OnBillingClientSetupFinishedListener(){
    @Override
    public void onBillingSetupFinished(int billingResponseCode) {
        super.onBillingSetupFinished(billingResponseCode);
    }
});
```
Kotlin:

```kotlin
///低于版本1.0.5.6的
// 在Application中的oncreate中初始化配置，appId为注册应用时候分配的应用id
Billing.configure(context ,"appid" , appUserId , listener)
///1.0.5.6之后
Billing.configure(context ,"appid" , secret, appUserId , listener)
```



### 参数：
- appId: 由AW生成，生成步骤请见文档：新建应用（外部版） 
- secret: V1.0.5.6版本新增，由AW生成，生成步骤请见文档：新建应用（外部版） 
- uid: userId，没有可传空字符串
- listener: 初始化的监听，可传空，在初始化之后会通过监听返回回调结果通过
`onBillingSetupFinished`方法

 ```
