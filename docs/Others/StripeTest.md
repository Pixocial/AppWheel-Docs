---
sidebar_position: 1
title: Stripe test
id: stripe-test
---

# Stripe 订阅测试

在stripe中，因为订阅周期最少也是一天的限制，所以在测试的过程中如果想观察订阅的生命周期（新建、续订、欠费、取消订阅、到期等），正常情况下只能被动等待，不过Stripe提供了相关的测试工具。

### 注意

***Stripe 测试时钟只针对Stripe测试环境有用，正式环境不可用。
只支持未调用过任何Stripe相关接口用户的修改。***

## 测试时钟

用测试时钟通过时间来模拟计费场景。
Stripe参考文档：https://stripe.com/docs/billing/testing/test-clocks
注意：每次调整stripe时钟不应该超一个订阅周期，否则会出现账单丢失的情况。如订阅周期是2天，那则每次调整时间不能超过2天，可以每次加一天。

## 配置方法

### 1、在Stipe添加时钟模拟对象。

https://dashboard.stripe.com/test/test-clocks
![1](/img/other/image.png)

### 2、在时钟对象添加客户

填基本信息，用于以后识别身份，建议与appuserid一致
![1](/img/other/stripe2.png)

记录好创建出来的stripe customer id
![1](/img/other/stripe3.png)

### 3、调用AW 初始化用户接口

AppWheel - Stripe支付接入文档 - 用户初始化接口，appuserid 需要以 `test_` 为前缀
![1](/img/other/stripe4.png)

### 4、登录管理后台 https://dashboard.appwheel.com

https://dashboard.appwheel.com/customers，选择刚才初始化的用户appuserid，打开详情页，填写新的Stripe Customer ID。

![1](/img/other/stripe5.png)

### 5、正常新建订阅

略。

### 6、时钟对象客户修改时间

***修改时间的步长，不能超过订阅产品的周期，否则会出现丢数据的情况。
如订阅周期是2天，则每次调整时间不能超过2天，可以每次加一天。***
![1](/img/other/stripe6.png)
