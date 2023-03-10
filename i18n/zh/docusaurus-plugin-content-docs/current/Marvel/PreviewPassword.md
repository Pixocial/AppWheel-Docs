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

### 返回数据

<table>
  <thead class="ant-table-thead">
    <tr>
      <th key=name>名称</th><th key=type>类型</th><th key=required>是否必须</th><th key=default>默认值</th><th key=desc>备注</th><th key=sub>其他信息</th>
    </tr>
  </thead><tbody className="ant-table-tbody"><tr key=0-0><td key=0><span ><span ></span> code</span></td><td key=1><span>number</span></td><td key=2>非必须</td><td key=3></td><td key=4><span ></span></td><td key=5></td></tr><tr key=0-1><td key=0><span ><span ></span> data</span></td><td key=1><span>object</span></td><td key=2>非必须</td><td key=3></td><td key=4><span ></span></td><td key=5></td></tr><tr key=0-1-0><td key=0><span ><span >├─</span> preview_pwd</span></td><td key=1><span>string</span></td><td key=2>非必须</td><td key=3></td><td key=4><span ></span></td><td key=5></td></tr><tr key=0-1-1><td key=0><span ><span >├─</span> ttl</span></td><td key=1><span>number</span></td><td key=2>非必须</td><td key=3></td><td key=4><span >秒</span></td><td key=5></td></tr><tr key=0-2><td key=0><span ><span ></span> message</span></td><td key=1><span>string</span></td><td key=2>非必须</td><td key=3></td><td key=4><span ></span></td><td key=5></td></tr>
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