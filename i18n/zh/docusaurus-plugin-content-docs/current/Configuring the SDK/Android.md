

SDK的初始化方法，用户根据自己的情况尽早在app中初始化

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

<Tabs>
  <TabItem value="Java" label="Java" default>

```Java
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
  </TabItem>
  <TabItem value="Kotlin" label="Kotlin">

```Kotlin
///Older than version 1.0.5.6
//Initialize the configuration in Application - oncreate. The appId refers to the ID you received when registering. 
Billing.configure(context ,"appid" , appUserId , listener)
///Version 1.0.5.6 or later
Billing.configure(context ,"appid" , secret, appUserId , listener)
```
  </TabItem>

</Tabs>



### 参数：
- appId: 由AW生成，生成步骤请见文档：新建应用（外部版） 
- secret: V1.0.5.6版本新增，由AW生成，生成步骤请见文档：新建应用（外部版） 
- uid: userId，没有可传空字符串
- listener: 初始化的监听，可传空，在初始化之后会通过监听返回回调结果通过
`onBillingSetupFinished`方法

 ```
