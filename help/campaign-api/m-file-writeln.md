---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '39'
ht-degree: 25%
---
# 写入

将一行文本写入文件。

```text
writeln (line)
```

## 参数

**line**&#x200B;要写入的文本行。

## 返回值

无。

## 备注

示例：

```javascript
var f = new File("c:/file.txt")
f.open("a")
f.writeln("line 1")
f.writeln("line 2")
f.close()
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
