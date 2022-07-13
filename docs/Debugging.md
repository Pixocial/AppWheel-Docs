---
sidebar_position: 103
title: Debugging
id: Debugging
---


View and understand Purchases logs

AppWheel's SDK will log important information and errors to help you understand what is going on behind the scenes. You can enable more detailed debug logs with the debugLogsEnabled flag. You can set this immediately in your app while testing, before you configure Purchases.

 
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