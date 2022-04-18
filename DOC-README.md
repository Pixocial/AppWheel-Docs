
## 前期准备

### git操作

- 使用[git](https://git-scm.com/) 下载代码
- 打开控制台，进入到需要放工程的目录
- 输入命令: git clone https://github.com/Pixocial/AppWheel-Docs.git
- 得到工程代码 AppWheel-Docs 的文件夹
- 提交代码：`git add . && git commit -m "描述一下这次的修改" && git push`
	- 网页提交 PullRequest
- 注意事项
    - 每次编辑前，先更新代码: `git pull`
 
- 翻译完成后审核
    - 提交分支
    - 审核人员拉取分支
    - 审核人员切换到待审核分支
    - 审核人员运行代码看效果
    - 审核通过，提交人员提交合并

### MD文档编辑
#### 工具
- [Typora](https://typora.io/)
- [MacDown](https://macdown.uranusjr.com/)

#### 语法
[MD语法](https://www.cnblogs.com/liugang-vip/p/6337580.html)


## docusaurus文档上传指南

### 第一步：上传文件到指定位置

英文版md文件上传至.\AppWheel-Docs\docs

多语言版本以中文为例（zh）上传至.\AppWheel-Docs\i18n\zh\docusaurus-plugin-content-docs/current下与英文版相同的位置

如果需要分组展示，可以放在不同的文件夹下，文件夹名即为分组标题名

### 第二步：修改md文件的顺序

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

### 第四步：运行项目检查效果（可选，非技术人员可在技术人员指导下完成）

#### 环境安装
- yarn 安装
      - 打开 Terminal.app
       - yarn 安装: `npm install --global yarn`

安装了yarn之后在项目根目录输入 `yarn` 安装依赖

随后使用 `yarn start` 运行项目

如果md文件出现问题，会在运行后告知你具体那个md文件的那一行出现了问题，方便修改。


### 第五步：新建目录、文档规则
如果乱写目录、文件的名字，会导致超链接失败，故制定了一些规则
#### 目录
新建目录如果是多个单词组成，要使用驼峰规则，(例如:恢复购买，目录名称应该为：restorePurchase),不可为空格或者其他符号。但是展示上在_category_.json文件的"label"属性值可以赋值为 restore purchase，这样子在效果上看起来就是restore purchase。

#### 文件
新建文件的名字也是不要使用其他符号

### 第六步：新文档暂时不想发版时
当你只写中文文档，英文文档暂时没有返回时，又不想文档随便乱丢导致后期不好找，可以先放到\AppWheel-Docs\i18n\目录下，这样子是不会被发版到线上的



