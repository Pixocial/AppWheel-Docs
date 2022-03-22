# iOS

## 初始化SDK
### 说明：
SDK的初始化方法，用户根据自己的情况尽早在app中初始化

Objective-C:

```Objective-C
///2.0.1.3版本前请使用以下方式  
AWPurchaseKit configureWithAppId:appid 
                             uid:userId     
                      completion:^(BOOL success, AWError * _Nonnull error) {
    if (success) {
      //init success ,do something
    } else {
      // init failed,check error
    }
  }
  
  ///2.0.1.3版本后修改为  
[AWPurchaseKit configureWithAppId:appId 
                           secret:appSecret
                              uid:userId
                       completion:^(BOOL success, AWError * _Nonnull error) {
                 if (success) {
                  //init success ,do something
                } else {
                  // init failed,check error
                }
  }];
```
  
Swift:

```Swift
///2.0.1.3版本前请使用以下方式  
AWPurchaseKit.configure(withAppId: appId, 
                              uid: uid) { [weak self](success, error) in
      if success == false {
        // init failed,check error
      } else {
        //init success ,do something
      }
    }
    
 ///2.0.1.3之后修改为
 AWPurchaseKit.configure(withAppId: appId, 
                            secret:appSecret 
                               uid: uid) { [weak self](success, error) in
      if success == false {
        // init failed,check error
      } else {
        //init success ,do something
      }
    }
```

### 参数：
*  `appId`: 由AW的服务器生成，生成步骤请见文档：新建应用（外部版） 
*  `secret`: V2.0.1.3版本新增，由AW的服务器生成，生成步骤请见文档：新建应用（外部版） 
*  `uid`: userId，没有可传空字符串
*  `completion`: 初始化结果的block，如果初始化成功block中的返回true，如果错误返回false，在配置失败的情况下无法正常使用本组件

