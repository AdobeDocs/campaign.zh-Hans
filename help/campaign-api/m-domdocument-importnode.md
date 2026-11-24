---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 25%
---
# importNode

从另一文档创建节点副本。

```text
importNode (importedNode, deep)
```

## 参数

**importedNode** Source节点。

如果必须复制完整节点，则为&#x200B;**deep** true，否则为false。

## 返回值

节点的副本。

## 备注

示例：

```javascript
var result = doc.importNode(rcpResult, true);
doc.root.appendChild(result);
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
