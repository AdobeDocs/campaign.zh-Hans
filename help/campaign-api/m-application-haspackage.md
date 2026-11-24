---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '42'
ht-degree: 23%
---
# hasPackage

测试软件包是否已安装。

```text
hasPackage (name)
```

## 参数

**name**&#x200B;包的全名。

## 返回值

如果已安装软件包，则为True。

## 备注

示例：

```javascript
var hasMRM = application.hasPackage("nms:mrm")
```

## 功能

**类的方法：** [应用程序](c-application.md)

**可用位置：**

* 内容管理
* 投放属性
* 类型规则
* JSSP
* SOAP方法
* WebApp
* 工作流
