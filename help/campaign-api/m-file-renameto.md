---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '37'
ht-degree: 24%
---
# renameTo

重命名文件。

```text
renameTo (fileName)
```

## 参数

**文件名**&#x200B;新文件名（必须为完整路径）。

## 返回值

无。

## 备注

示例：

```javascript
var f = new File("c:/file.txt")
f.renameTo("c:/file2.txt")

var f2 = new File("c:/file.txt")
f2.renameTo("c:/dir/")
```

## 功能

**类的方法：** [文件](c-file.md)

**可用位置：**

* 内容管理
* 投放属性
* 类型规则
* JSSP
* SOAP方法
* WebApp
* 工作流
