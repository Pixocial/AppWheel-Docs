

SDK的初始化方法，用户根据自己的情况尽早在app中初始化

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

<Tabs>
  <TabItem value="Java" label="Java" default>


```Java

Billing.configure(context,"appId","secret")
                .setAppUserId("appUserId")
                .setListener(new OnBillingClientSetupFinishedListener(){
                    @Override
                    public void onBillingSetupFinished(int billingResponseCode) {
                    }
                })
                .build();
```
  </TabItem>
  <TabItem value="Kotlin" label="Kotlin">

```Kotlin
Billing.configure(context ,"appid" , “secret”)..setAppUserId("appUserId").build()
```
  </TabItem>

</Tabs>



### 参数：
- appId: 由AW生成，生成步骤请见文档：新建应用（外部版） 
- secret: V1.0.5.6版本新增，由AW生成，生成步骤请见文档：新建应用（外部版） 
- appUserId: userId，请不要使用特殊字符，如：'[` ~! @ # $% ^ & * () + = | {} ':', \ \ [\ \] < > /? ~! @ # $%... & * () - + | {} 【 】 '; : "",.,?]'，使用特殊字符可能导致无法预估的问题。没有userId可传空字符串
- listener: 初始化的监听，可传空，在初始化之后会通过监听返回回调结果通过`onBillingSetupFinished`方法



### 下一步

[请求商品](/DisplayingProducts/Android.md)