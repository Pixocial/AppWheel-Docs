---
sidebar_position: 9
title: 手动解锁
id: 手动解锁
---


import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

<Tabs>
  <TabItem value="Java" label="Java" default>

```Java

MarvelManager.getInstance().manualUnlock( new AWHttpOriginalCallback() {
    @Override
    public void response(int code, String data) {

    }
});
```
  </TabItem>
  <TabItem value="Kotlin" label="Kotlin">

```Kotlin

MarvelManager.getInstance().manualUnlock(object : AWHttpOriginalCallback{
    override fun response(code: Int, data: String?) {
    }
})
```
  </TabItem>
  <TabItem value="Objective-C" label="Objective-C">

```Objective-C 
[[AWPurchaseKit getMarvelManager] manualUnlockWithCompletion:^(NSInteger result, NSString * _Nonnull errorMsg, NSDictionary * _Nullable data) {
            });
}];
```
  </TabItem>
  <TabItem value="Swift" label="Swift">

```Swift

AWPurchaseKit.getMarvelManager().manualUnlock{ result, errorMsg, data in
    
}
```
  </TabItem>
</Tabs>

### 参数
无


### Example
```Json
{
  "vip_expires_date": 0
}

```