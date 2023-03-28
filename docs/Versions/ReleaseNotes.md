
### Latest SDK versions


import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

<Tabs>
<TabItem value="Android" label="Android" default>

#### Update - Mar 28,2023
##### version 1.1.3.0
- 修改marvel的地址
- 缇娜家推荐词功能

#### Update - Mar 7,2023
##### version 1.1.1.0
- 修改权益类名
- 对分库进行优化重新整理

#### Update - Jan 5,2023
##### version 1.0.20.0
- 新增Marvel功能：高级开关、手动解锁
- 修复获取商品异常可能带来的crash

#### Update - Dec 8,2022
##### version 1.0.19.0
- 新增收集：系统版本号、手机型号、sim卡国家

#### Update - Nov 17,2022
##### version 1.0.18.0
- 添加打点上报的失败重试机制
- 修改打点上报的参数

#### Update - Oct 10,2022
##### version 1.0.17.0
- 添加设置属性接口：UserInfoManager.getInstance().setUserAttribute

#### Update - Sep 28,2022
##### version 1.0.16.0
- 添加marvel的功能接口

#### Update - Sep 27,2022
##### version 1.0.15.1
- 修改处于宽限期的订单为有效订单

#### Update - Aug 22,2022
##### version 1.0.15.0
- 升级GoogleBilling版本为4.0

#### Update - Aug 12,2022
##### version 1.0.14.0
- 修改恢复购买的接口调用

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


#### Update - Mar 7,2023
##### version 2.1.1.0
- 修改marvel的地址
- 缇娜家推荐词功能

#### Update - Mar 7,2023
##### version 2.1.1.0
- 新增分库：
- - AppWheel/core：核心库
- - AppWheel/purchase：购买库
- - AppWheel/analytics：打点数据上报库
- - AppWheel/marvel：marvel功能相关库

#### Update - Jan 5,2023
##### version 2.0.13.0
- 新增Marvel功能：高级开关、手动解锁
- 新增收集：购买商品的国家码

#### Update - Dec 8,2022
##### version 2.0.12.0
- 新增收集：系统版本号、手机型号、sim卡国家

#### Update - Nov 17,2022
##### version 2.0.11.0
- 去掉checkProductPurchaseHistoryStatus接口,请用getProductHasPaiedWithProductId代替
- 修复多线程引起的打点上报概率性crash
- 增加打点上报的失败重试机制
- 修改打点上报的参数

#### Update - Oct 31,2022
##### version 2.0.10.2
- 修复bug：用户处于订阅期的时候isSubscriptionUnlockedUser状态返回错误

#### Update - Oct 31,2022
##### version 2.0.10.1
- 修复bug：在初始化之前调用恢复购买的导致的签名secret为空问题

#### Update - Oct 10,2022
##### version 2.0.10.0
- 添加设置属性接口：[AWPurchaseKit setUserAttributes]

#### Update - Sep 29,2022
##### version 2.0.9.0
- 添加marvel的功能接口

#### Update - Sep 16,2022
##### version 2.0.8.1
- 修复优惠必备数据为空导致的crash

#### Update - Aug 9,2022
##### version 2.0.8.0
- 修复验签错误
- 添加商品购买状态接口：getProductHasPaiedWithProductId
- 添加日志上报信息：awTranId

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