---
sidebar_position: 4
title: 预发布密码
id: 预发布密码
---


import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

<Tabs>
  <TabItem value="Java" label="Java" default>

```Java
MarvelManager.getInstance().getPreviewPwd(new AWHttpOriginalCallback() {
                @Override
                public void response(int code, String data) {
                    
                }
            });
```
  </TabItem>
  <TabItem value="Kotlin" label="Kotlin">

```Kotlin

MarvelManager.getInstance().getPreviewPwd(object : AWHttpOriginalCallback{
            override fun response(code: Int, data: String?) {
            }
        });
```
  </TabItem>
  <TabItem value="Objective-C" label="Objective-C">

```Objective-C 
[[AWPurchaseKit getMarvelManager] getPreviewPwdWithCompletion:^(NSInteger result, NSString * _Nonnull errorMsg, NSDictionary * _Nullable data) {
        
    }];
```
  </TabItem>
  <TabItem value="Swift" label="Swift">

```Swift
AWPurchaseKit.getMarvelManager().getPreviewPwd(){ result, errorMsg, data in
            
        }
```
  </TabItem>
</Tabs>

### 返回
```Json
{
  "code": 0,
  "data": {
    "preview_pwd": "new:mrsecret:1:1661742886",
    "ttl": 2496546
  },
  "message": "success",
  "update": ""
}

```