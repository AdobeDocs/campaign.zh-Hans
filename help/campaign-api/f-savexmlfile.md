---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 8%
---
# saveXmlFile

> 警告：
>
> 通过文件API进行的访问仅限于&#x200B;**var**、**sftp**&#x200B;和Adobe Campaign的临时文件夹。

将与XML文档对应的字符串保存到文件。

```text
saveXmlFile (text, filename [, codePage ])
```

## 参数

**文本**&#x200B;要保存的字符串形式的XML文档。

**filename**&#x200B;要保存的文件的全名。

**codePage**&#x200B;此可选参数允许您指定字符编码。 示例：

* iso-8859-1
* utf-8
* utf-16
* us-ascii
* shift-jis
* euc-kr

## 返回值

无。

## 备注

此函数在文件中插入一个XML prolog（如有必要），并指定文档编码。 如果未指定字符编码，则使用服务器默认值。

## 功能

**可用位置：**

* 内容管理
* 投放属性
* 类型规则
* JSSP
* SOAP方法
* WebApp
* 工作流
