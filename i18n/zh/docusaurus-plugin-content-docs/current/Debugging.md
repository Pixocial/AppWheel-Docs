---
sidebar_position: 12
title: 调试
id: Debugging
---


查看和了解购买日志

AppWheel的 SDK 将记录重要信息和错误，以帮助您了解幕后发生的事情。在测试模式下，你可以打开日志的打印开关配置以便能够看到更详细的调试日志。

 
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

<Tabs>
  <TabItem value="Java" label="Java" default>

```Java
    BillingLog.isDebug = true;
```

  </TabItem>
  <TabItem value="Kotlin" label="Kotlin">

```Kotlin
    BillingLog.isDebug = true
```

  </TabItem>
  <TabItem value="Objective-C" label="Objective-C">

```Objective-C 
    [AWLogUtil isCanLog:YES];
```
  </TabItem>
  <TabItem value="Swift" label="Swift">

```Swift
    AWLogUtil.isCanLog(true)
```
 </TabItem>
</Tabs>