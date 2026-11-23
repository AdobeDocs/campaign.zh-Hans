---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '103'
ht-degree: 13%
---
# 加载

> 警告：
>
> 通过文件API进行的访问仅限于&#x200B;**var**、**sftp**&#x200B;和Adobe Campaign的临时文件夹。

从XML文件创建新文档。

```text
load (filename [, allowEmpty ])
```

## 参数

**文件名**&#x200B;要加载的文件的名称。

**allowEmpty**&#x200B;如果为true，则当文件为空时，不会引发异常（默认值=false）。

## 返回值

无。

## 备注

如果无法加载文件或文件内容不是有效的XML文档，则会引发异常。 此函数适用于DOMDocument类。 示例：

```javascript
var doc = DOMDocument.load("data/test.xml")
```

## 功能

**类的方法：** [DOMDocument](c-domdocument.md)

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
