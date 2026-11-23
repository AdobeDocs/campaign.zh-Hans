---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '84'
ht-degree: 11%
---
# 列表

列出目录的内容。

```text
list ( [mask ] [, sort ] [, noCase ])
```

## 参数

**掩码**&#x200B;搜索掩码（\*默认为）。

**排序** true以对结果进行排序（默认为false）。

**noCase** true表示排序时忽略类（默认为false）。

## 返回值

包含与指定路径和掩码匹配的文件（[文件](c-file.md)）列表的表。

## 备注

在Linux中，目录名称必须以/结尾，在Windows中必须以\\结尾。 示例：

```javascript
var dir = new File("c:\\temp\\")
var files = dir.list("*.*")
for each (var file in files)
  logInfo(file.name)
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
