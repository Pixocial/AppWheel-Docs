## docusaurus文档上传指南


### 第一步：上传文件到指定位置

英文版md文件上传至.\AppWheel-Docs\docs

多语言版本以法语为例（fr）上传至.\AppWheel-Docs\i18n\fr\docusaurus-plugin-content-docs下与英文版相同的位置

如果需要分组展示，可以放在不同的文件夹下，文件夹名即为分组标题名

### 第二步：修改md文件索引

md文件被识别需要添加一个头部说明,使用`---`符号上下包裹

例如：

```
---
sidebar_position: 1
title: AppWheel SDK Integration Document
id: AppWheel-SDK-Integration-Document
---
```

其中id作为url的一部分因此务必不要添加空格

可以参考官网的例子：https://www.docusaurus.cn/docs/create-doc

### 第三步：配置静态资源

静态资源需要存放在`./static`下，
随后在md中使用，注意路径默认根目录是static，因此不需要在url里加入“/static”

例如：

```
![Docs Version Dropdown](/img/tutorial/docsVersionDropdown.png)
```

### 第四步：运行项目检查效果（可选）

clone项目后在项目根目录输入 `yarn` 安装依赖

随后使用 `yarn start` 运行项目

如果md文件出现问题，会在运行后告知你具体那个md文件的那一行出现了问题，方便修改。


### 第五步：新建目录、文档规则
如果乱写目录、文件的名字，会导致超链接失败，故制定了一些规则
#### 目录
新建目录如果是多个单词组成，要使用驼峰规则，(例如:恢复购买，目录名称应该为：restorePurchase),不可为空格或者其他符号。但是展示上在_category_.json文件的"label"属性值可以赋值为 restore purchase，这样子在效果上看起来就是restore purchase。

#### 文件
新建文件的名字也是不要使用其他符号



