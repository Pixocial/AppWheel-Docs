---
sidebar_position: 8
title: 高级开关
id: 高级开关
---


import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

<Tabs>
  <TabItem value="Java" label="Java" default>

```Java
MarvelManager.getInstance().advancedSwitch(MarvelConfig.getInstance().countryCode, MarvelConfig.getInstance().language, switchKeyET.getText().toString(), updateET.getText().toString(),  new AWHttpOriginalCallback() {
    @Override
    public void response(int code, String data) {

    }
});
```
  </TabItem>
  <TabItem value="Kotlin" label="Kotlin">

```Kotlin


MarvelManager.getInstance().advancedSwitch(countrycode,language,key,update,object : AWHttpOriginalCallback{
    override fun response(code: Int, data: String?) {
    }
})
```
  </TabItem>
  <TabItem value="Objective-C" label="Objective-C">

```Objective-C 
[[AWPurchaseKit getMarvelManager] getBannerWithLanguage:language withCountryCode:countryCode withPhrase:phrase withUpdate:update withAbcodes:abcodes withEffectiveFilter:effectiveFilter withTimezoneOffset:timezoneOffset withCompletion:^(NSInteger result, NSString * _Nonnull errorMsg, NSDictionary * _Nullable data) {
            
}];
```
  </TabItem>
  <TabItem value="Swift" label="Swift">

```Swift

AWPurchaseKit.getMarvelManager().advancedSwitch(with: language, withCountryCode: countryCode, withKey: key, withUpdate: update){ result, errorMsg, data in
    
}
```
  </TabItem>
</Tabs>

### 参数
- language：语言
- countryCode：国家
- key： 从AW管理后台获取的key（可空，未填时返回全部）
- update: 当前MD5值（可空）

### 返回
```Json
{
  "status": 1,
  "key": "key",
  "value": "ceshi",
  "update": "c7c7480df826d81e5146d52e9c1f83b9"
}

```