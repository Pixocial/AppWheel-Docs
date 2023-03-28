---
sidebar_position: 10
title: 推荐词
id: 推荐词
---


import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';


<Tabs>
  <TabItem value="Java" label="Java" default>

```Java
Market.getInstance().getTrending(lanaguage, type, new Callback() {
    @Override
    public void onFailure(Call call, IOException e) {

    }

    @Override
    public void onResponse(Call call, Response response) throws IOException {

    }
});
```

  </TabItem>
  <TabItem value="Kotlin" label="Kotlin">

```Kotlin
Market.getInstance().getTrending(language,type,object : Callback{
    override fun onFailure(call: Call?, e: IOException?) {
    }

    override fun onResponse(call: Call?, response: Response?) {
    }
})
```

  </TabItem>
  <TabItem value="Objective-C" label="Objective-C">

```Objective-C 
[AWPurchaseKit getTrendingWithLanguage:language withType:type withCompletion:^(BOOL, NSDictionary * _Nullable, AWError * _Nullable) {
            
}];
```

  </TabItem>
  <TabItem value="Swift" label="Swift">

```Swift
AWPurchaseKit.getTrendingWithLanguage(language, withType: type) { success, data, error in

}         
```

  </TabItem>
</Tabs>

### 请求参数

**Query**

| 参数名称             | 是否必须 | 示例  | 备注                                                                        |
|------------------|------|-----|---------------------------------------------------------------------------|
| language           | 是    | en |                                                              |
| type             | 否    |     |                                                                         |

### 返回数据


```json

```