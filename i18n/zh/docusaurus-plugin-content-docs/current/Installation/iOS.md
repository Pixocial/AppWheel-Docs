

### 接入要求：iOS 10.0及其以上
### 通过CocoaPods接入，需在Podfile中加入以下命令


```Objective-C
pod 'AppWheel'
```

最新版本请执行：pod search AppWheel 获得

所有方法支持Swift调用，请在Bridging-Header文件中添加语句

```Objective-C
#import <PurchaseSDK/AWPurchaseKit.h>
```

>   <font color="red">**注：本SDK暂时只支持真机，不支持模拟器**</font> 


### 下一步
[配置SDK](/ConfiguringTheSDK/iOS.md)