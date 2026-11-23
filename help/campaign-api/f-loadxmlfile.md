---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 13%
---
# loadXmlFile

> 警告：
>
> 通过文件API进行的访问仅限于&#x200B;**var**、**sftp**&#x200B;和Adobe Campaign的临时文件夹。

此函数已过时，请使用[DOMDocument.load()](m-domdocument-load.md)。 以XML文档对象的形式加载文件

```text
loadXmlFile (filename [, noErr ])
```

## 参数

**filename**&#x200B;要加载的文件的全名。

**noErr**&#x200B;如果为true，则文件为空时没有错误（默认值=false）。

## 返回值

XML文档。

## 备注

此函数通过检测BOM和XML序号来支持对文件代码页的检测。

## 功能

**可用位置：**

* 内容管理
* 投放属性
* 投放消息
* 类型规则
* 导入
* JSSP
* SOAP方法
* WebApp
* 工作流
