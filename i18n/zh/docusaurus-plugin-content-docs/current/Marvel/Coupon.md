---
sidebar_position: 11
title: 发券机
id: 发券机
---


import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';


<Tabs>
  <TabItem value="Java" label="Java" default>

```Java

MarvelManager.getInstance().getCoupon(countryCode, language, previewPwd, update, effetive, new AWHttpOriginalCallback() {
@Override
        public void response(int code, String data) {

        }
});
```

  </TabItem>
  <TabItem value="Kotlin" label="Kotlin">

```Kotlin
MarvelManager.getInstance().getCoupon(countryCode, language, abcodes,phrase, update, effectiveFilter, object : AWHttpOriginalCallback{
    override fun response(code: Int, data: String?) {
    }
})
```

  </TabItem>
  <TabItem value="Objective-C" label="Objective-C">

```Objective-C 

#import <AWMarvel/AWMarvel.h>
......
[[AWMarvelManager sharedInstance] getCouponWithLanguage:language withCountryCode:countryCode withPhrase:phrase withUpdate:update withEffectiveFilter:effectiveFilter withCompletion:^(NSInteger result, NSString * _Nonnull errorMsg, NSDictionary * _Nullable data) {
            
}];

```

  </TabItem>
  <TabItem value="Swift" label="Swift">

```Swift
#import <AWMarvel/AWMarvel.h>
......
AWMarvelManager.sharedInstance().getCouponWithLanguage(language, withCountryCode: countryCode, withPhrase: phrase, withUpdate: update, withEffectiveFilter: effectiveFilter) { result, errorMsg, data in
            
}       
```

  </TabItem>
</Tabs>

### 参数
- language：语言
- countryCode：国家
- phrase： 预发布密码（可空）
- update: 当前MD5值（可空）
- effectiveFilter： 传1新时区逻辑，不传为旧逻辑 （可空）


### 返回数据

```json

```