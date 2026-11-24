---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 12%
---
# open

加载现有档案。

```text
open ()
```

## 参数

无。

## 返回值

无。

## 备注

对于现有存档，必须首先调用⌐[fileCount](p-zipfile-filecount.md)方法以恢复文件数，或者调用[getEntry()](m-zipfile-getentry.md)以提取文件。 如果文件不存在或文件不是有效的存档，则此方法会引发异常。

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
