
### bitcode error

#### Error:
'*/PurchaseSDK.framework/PurchaseSDK(AWHttpManager.o)' does not contain bitcode. You must rebuild it with bitcode enabled (Xcode setting ENABLE_BITCODE), obtain an updated library from the vendor, or disable bitcode for this target. file '*/PurchaseSDK.framework/PurchaseSDK' for architecture arm64

![bitcodeError](/img/commonErrors/bitcodeError.png)

#### solution
disable 'bitcode' in project.like this

![bitcodeError](/img/commonErrors/bitcodeErrorSolution.png)