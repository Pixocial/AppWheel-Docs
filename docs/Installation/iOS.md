
### Integration Requirements iOS 10.0 and above

The integration should be done with CocoaPods and the following orders should be added to Podfile.

```Objective-C 
pod 'AppWheel'
```

The latest version can be obtained through the official website or by executing pod search AppWheel.
 All methods support Swift calls. Please add the following sentences to the Bridging-Header file.

```Objective-C 
import <PurchaseSDK/AWPurchaseKit.h>
```
>   <font color="red">**Note: This SDK only supports the real machine rather than a simulator for the time being.**</font> 
