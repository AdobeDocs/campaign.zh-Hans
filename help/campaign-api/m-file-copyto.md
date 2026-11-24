---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '40'
ht-degree: 22%
---
# copyto

复制文件。

```text
copyTo (fileName)
```

## 参数

**fileName**&#x200B;目标文件或文件夹的名称（必须为完整路径）。

## 返回值

无。

## 备注

示例：

```javascript
var f = new File("c:/file.txt")
f.copyTo("c:/file2.txt")

var f2 = new File("c:/file.txt")
f2.copyTo("c:/dir/")
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
