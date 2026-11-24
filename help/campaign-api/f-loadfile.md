---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '103'
ht-degree: 13%
---
# loadFile

> 警告：
>
> 通过文件API进行的访问仅限于&#x200B;**var**、**sftp**&#x200B;和Adobe Campaign的临时文件夹。

返回文本文件的内容

```text
loadFile (filename [, codePage ])
```

## 参数

**filename**&#x200B;要加载的文件的全名。

**codePage**&#x200B;此可选参数允许您指定字符编码。 示例：

* iso-8859-1
* utf-8
* utf-16
* us-ascii
* shift-jis
* euc-kr

## 返回值

对应于文本文件内容的字符串。

## 备注

如果未指定字符编码，则使用服务器默认值。

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
