

 The following method is used to check a user's existing purchased products.
### Obtain the current valid orders
#### Description:
 The following method is used to check a user's existing valid orders, including valid subscription and unconsumed INAPP products.


import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

<Tabs>
  <TabItem value="Java" label="Java" default>

```Java
UserOrderManager.getProvider().getOrders()
```
  </TabItem>
  <TabItem value="Kotlin" label="Kotlin">

```Kotlin
UserOrderManager.getProvider().getOrders()
```
  </TabItem>
</Tabs>

### Obtain current subscription
#### Description:
 This method is used to obtain a user's existing valid subscription. If there is no valid subscription, an empty result will be returned.



<Tabs>
  <TabItem value="Java" label="Java" default>

```Java
SubsPurchase recentSubsPurchase = UserOrderManager.getProvider().getRecentSubsPurchase();
```
  </TabItem>
  <TabItem value="Kotlin" label="Kotlin">

```Kotlin
val recentSubsPurchase = UserOrderManager.getProvider().recentSubsPurchase
```
  </TabItem>
</Tabs>