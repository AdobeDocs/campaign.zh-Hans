---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '95'
ht-degree: 12%
---
# isEqualNode

比较两个节点。

```text
isEqualNode (arg)
```

## 参数

**arg**&#x200B;第二个节点。

## 返回值

如果两个节点相等，则返回true，否则返回false。

## 备注

如果验证了以下条件，则两个节点相等：

* 这两个节点属于类型类型。
* nodeName、localName、namespaceURI、前缀和nodeValue属性必须相同。
* 这两个节点属于类型类型。
* 属性必须相等。
* 节点必须相等。

由于标准化会影响平等，因此我们建议您在比较之前进行标准化。

## 功能

**类的方法：** [DOMNode](c-domnode.md)

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
