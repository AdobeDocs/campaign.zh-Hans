---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '60'
ht-degree: 15%
---
# setEntry

在存档中添加或更新文件。

```text
setEntry (filename, buffer)
```

## 参数

**文件名**&#x200B;源文件的名称。

包含文件的&#x200B;**buffer** MemoryBuffer。

## 返回值

无。

## 备注

在调用[save()](m-zipfile-save.md)方法之前，将不会在磁盘上有效修改存档。

## 功能

**类的方法：** [ZipFile](c-zipfile.md)

**可用位置：**

* 内容管理
* 投放属性
* 类型规则
* JSSP
* SOAP方法
* WebApp
* 工作流
