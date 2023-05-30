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

### 请求参数

**Query**

| 参数名称     | 是否必须 | 示例      | 备注                           |
|----------|------|---------|------------------------------|
| language | 是    | en      | 语言简称，ja、en等                  |
| type     | 否    | stikers | 运营自定义类型，如素材类型、搜索框位置等，不传表示查全部 |

### 返回数据

```json

{
  "code": 0,
  "data": {
    "list": [
      {
        "label": [
          "Hot"
        ],
        "type": "anim",
        "name": "CAT"
      },
      {
        "label": [
          "New"
        ],
        "type": "anim",
        "name": "Dog"
      }
    ]
  },
  "message": "success"
}
```