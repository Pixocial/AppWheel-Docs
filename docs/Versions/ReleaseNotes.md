
### Latest SDK versions


import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

<Tabs>
<TabItem value="Android" label="Android" default>

#### Update - Jul 18,2022
##### version 1.0.13.1
- 添加Stripe订单接口的返回数据model：EntitlementOrders

#### Update - Jul 15,2022
##### version 1.0.13.0
- 修改初始化轮询机制
- 修复请求服务器概率性签名错误

#### Update - Apr 15,2022
##### version 1.0.12.0
- 修改服务器请求地址为V2版本


#### Update - Apr 15,2022
##### version 1.0.11.0
- 添加请求appUserId接口：Market.getInstance().delUserId()

#### Update - Apr 15,2022
##### version 1.0.10.0
- 添加跨端支付的订单请求接口


#### Update - Apr 13,2022
##### version 1.0.9.0
- 修复特殊字符导致的上报商品信息错误

#### Update - Apr 2,2022
##### version 1.0.8.0
- 添加了订阅搭建工具的原生界面

#### Update - Mar 11,2022
##### version 1.0.7.1
- 修复了特殊字符"-"导致的上报商品信息错误

#### Update - Mar 9,2022
##### version 1.0.6.0
- 修改saas.pixocial的域名为appwheel.com
- 添加firebaseId\appsFlyerId上报


#### Update - Feb 10,2022
##### version 1.0.5.6
- 增加折扣码功能

#### Update - Nov 9,2021
##### version 1.0.5.5
- 修复多次初始化导致订单翻倍
- 修复订单都是订阅订单时，订阅过期了清空历史记录

#### Update - Oct 20,2021
##### version 1.0.5.4
- 兼容订阅中台老版本

</TabItem>


<TabItem value="iOS" label="iOS">

#### Update - Jul 18,2022
##### version 2.0.7.1
- 添加Stripe订单接口的返回数据model：AWEntitlementOrders
- 修改初始化轮询机制
- 修复请求服务器概率性签名错误

#### Update - May 10,2022
##### version 2.0.6.1
- 修改服务器请求地址为V2版本

#### Update - May 10,2022
##### version 2.0.5.0
- 修改订阅页的一些UI样式

#### Update - May 5,2022
##### version 2.0.4.0
- 添加清楚appUserId接口：[AWPurchaseKit delUserId]

#### Update - Apr 15,2022
##### version 2.0.3.0
- 添加跨端支付的订单请求接口

#### Update - Apr 7,2022
##### version 2.0.2.1
- 添加了订阅搭建工具的原生界面

#### Update - Feb 18,2022
##### version 2.0.1.4
- 添加firebaseId\appsFlyerId上报

#### Update - Feb 10,2022
##### version 2.0.1.3
- 添加折扣码功能

#### Update - Jan 26,2022
##### version 2.0.1.2
- 更改userId的缓存逻辑

#### Update - Dec 14,2021
##### version 2.0.1.0
- 添加productType枚举
- 添加一些购买的监听回调
- 添加获取服务器的方法
- 补全了一些属性为nullable

#### Update - Oct 12,2021
##### version 2.0.0.1
- 兼容订阅中台

</TabItem>

</Tabs>