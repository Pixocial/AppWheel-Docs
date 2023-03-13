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
MarvelManager.getInstance().getPreviewPwd(new AWHttpOriginalCallback(){
@Override
public void response(int code,String data){

        }
        });
```

  </TabItem>
  <TabItem value="Kotlin" label="Kotlin">

```Kotlin

MarvelManager.getInstance().getPreviewPwd(object : AWHttpOriginalCallback {
    override fun response(code: Int, data: String?) {
    }
});
```

  </TabItem>
  <TabItem value="Objective-C" label="Objective-C">

```Objective-C 

#import <AWMarvel/AWMarvel.h>
......
[[AWMarvelManager sharedInstance] getPreviewPwdWithCompletion:^(NSInteger result, NSString * _Nonnull errorMsg, NSDictionary * _Nullable data) {
        
}];
```

  </TabItem>
  <TabItem value="Swift" label="Swift">

```Swift

#import <AWMarvel/AWMarvel.h>
......
AWMarvelManager.sharedInstance().getPreviewPwd(){ result, errorMsg, data in
            
}
```

  </TabItem>
</Tabs>

### 返回数据

<table style={{'min-width':'1200px'}}>
  <thead class="ant-table-thead">
    <tr>
      <th >>名称</th><th >>类型</th><th >>是否必须</th><th >>默认值</th><th >>备注</th><th >>其他信息</th>
    </tr>
  </thead><tbody className="ant-table-tbody"><tr >><td >><span ><span ></span> code</span></td><td >><span>number</span></td><td >>非必须</td><td >></td><td >><span ></span></td><td >></td></tr><tr >><td >><span ><span ></span> data</span></td><td >><span>object</span></td><td >>非必须</td><td >></td><td >><span ></span></td><td >></td></tr><tr >><td >><span ><span >├─</span> preview_pwd</span></td><td >><span>string</span></td><td >>非必须</td><td >></td><td >><span ></span></td><td >></td></tr><tr >><td >><span ><span >├─</span> ttl</span></td><td >><span>number</span></td><td >>非必须</td><td >></td><td >><span >秒</span></td><td >></td></tr><tr >><td >><span ><span ></span> message</span></td><td >><span>string</span></td><td >>非必须</td><td >></td><td >><span ></span></td><td >></td></tr>
               </tbody>
              </table>

### Example

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