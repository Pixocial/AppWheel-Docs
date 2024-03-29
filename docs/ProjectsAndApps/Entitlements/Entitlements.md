---
sidebar_position: 0
title: Entitlements
id: entitlements
---

# 权益

权益表示用户“有权”访问的访问级别、功能或内容。

授权用于确保用户能够根据其购买内容适当访问内容，而无需管理应用程序代码中的所有产品标识符。

大多数应用程序只有一项权益，即解锁所有高级功能。但是，如果您有两层内容（如黄金和白金），您将有两种权益。

**用户的权限在同一项目中包含的所有应用程序中共享。**

如有一个叫`Pro`会员服务。通常情况下，会提供不同的商品对应该项服务，如按月续订的`com.appwheel.1month.normal`和按年续订的`com.appwheel.1year.normal`
，或者在IOS端和Android端都提供相同的服务，但是因为平台不一样所以产品标识分别为`com.appwheel.1month.ios.normal`、`com.appwheel.1month.google.normal`，这些都可以配置到同一个权益中方便管理，同时这对于跨App共享订阅权益也是有益的。

![entitlement-sku](/img/tutorial/entitlement_sku.jpg)

## 权益的使用场景

当用户在APP上完成购买后，应用应该立即向用户解锁相应的服务或者功能。

### 传统模式

未使用权益的传统模式下，App需要根据用户购买订单的具体商品ID解锁服务，这种方式存在缺点：

- 如果商店内配置了上百种商品，那么App需要硬编码映射
- 后面增加的商品，用户需要升级App后才能使用
- 如果某个商品对应的功能发生变化，也需要用户升级

### 使用权益模式

将产品和权益绑定后，App购买订单后，可以通过订单的商品和权益关联解锁用户功能

- 在AppWheel设置好商品和服务的映射关系，不需要app保存
- 可以动态修改映射关系，不需要等待用户升级app

## 创建权益

要创建新权益，请单击项目面板左侧菜单中的权益，然后单击`+ NEW`。你需要为你的权利输入一个唯一的标识符，你可以在你的应用程序中引用，比如`Pro`。

![setup entitlement](/img/tutorial/create_entitlement.png)

## 关联产品和权益

创建权益后，应将产品附加到权益（请确保您已创建产品：[Android](/ProjectsAndApps/Products/androidSku.md)、[iOS](/ProjectsAndApps/Products/iossku.md)、[Stripe](/ProjectsAndApps/Products/StripeSku.md)）。这让AppWheel知道在用户购买特定产品后要解锁哪些权限。

查看授权时，单击编辑按钮以附加产品。如果您已经添加了您的产品，则可以从列表中选择一个要附加的产品。

![setup entitlement](/img/tutorial/attact_product_entitlement.png)

当购买附于权利的产品时，该权利在产品的有效期内变为有效。订阅产品将在订阅期间解锁授权，而附加到授权的非消耗品和消耗品购买将永久解锁该内容。

如果您有非订阅产品，您可能希望也可能不希望将它们添加到权利中，具体取决于您的用例。如果产品是非消耗品（例如终身使用`Pro`功能），您可能希望将其附加到权利中。然而，如果它是消耗品（例如在游戏中购买更多生命），您可能不想将其添加到权利中。

将权利附加到产品将授予先前购买过该产品的任何客户。同样，从产品中分离权利将删除以前购买过该产品的任何客户的权利。

在设计权利结构时，请记住，单个产品可以解锁多个权利，而多个产品可以解锁同一权利。



