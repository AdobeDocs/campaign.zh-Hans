---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 5%
---
# DOMNode（类）

DOMNode是构成文档的不同组件的父类。

## 方法

| 方法 | 描述 |
| --- | --- |
| [此项前插入](m-domnode-insertbefore.md) | 在特定位置之前插入节点。 |
| [replaceChild](m-domnode-replacechild.md) | 替换节点。 |
| [removeChild](m-domnode-removechild.md) | 删除节点。 |
| [appendChild](m-domnode-appendchild.md) | 在子文件夹列表的末尾插入一个节点。 |
| [hasChildNodes](m-domnode-haschildnodes.md) | 测试节点是否至少具有一个子文件夹。 |
| [标准化](m-domnode-normalize.md) | 标准化节点：合并相邻文本节点并删除空文本节点。 |
| [hasAttribute](m-domnode-hasattributes.md) | 测试节点是否至少具有一个属性。 |
| [isSameNode](m-domnode-issamenode.md) | 测试给定的引用是否表示同一节点。 |
| [isDefaultNamespace](m-domnode-isdefaultnamespace.md) | 测试给定的命名空间是否为默认值。 |
| [lookupNamespaceURI](m-domnode-lookupnamespaceuri.md) | 搜索链接到给定前缀的命名空间的URI。 |
| [isEqualNode](m-domnode-isequalnode.md) | 比较两个节点。 |

## 属性

| 属性 | 描述 |
| --- | --- |
| [nodeName](p-domnode-nodename.md) | 限定节点名称。 名称取决于节点类型。 |
| [nodeValue](p-domnode-nodevalue.md) | 节点值。 该值取决于节点的类型。 |
| [nodeType](p-domnode-nodetype.md) | 节点类型。 |
| [parentNode](p-domnode-parentnode.md) | 父节点或null。 |
| [childNodes](p-domnode-childnodes.md) | 以表的形式返回子节点的列表。 |
| [firstChild](p-domnode-firstchild.md) | 此节点的第一个子节点；如果没有子节点，则为null。 |
| [lastChild](p-domnode-lastchild.md) | 此节点的最后一个子节点；如果没有子节点，则为null。 |
| [下一个同级](p-domnode-nextsibling.md) | 此节点之后的节点或null。 |
| [previousSibling](p-domnode-previoussibling.md) | 紧靠此节点或null的节点。 |
| [属性](p-domnode-attributes.md) | 如果节点是元素，则返回包含属性列表的表，否则为null。 |
| [namespaceURI](p-domnode-namespaceuri.md) | 节点命名空间的URI。 |
| [前缀](p-domnode-prefix.md) | 此节点的命名空间前缀，如果未指定，则为空。 |
| [localName](p-domnode-localname.md) | 节点的限定名称的本地部分。 |
| [baseURI](p-domnode-baseuri.md) | 此节点的基本URI。 |
| [textContent](p-domnode-textcontent.md) | 节点的文本内容。 该值取决于节点的类型。 |
| [ownerDocument](p-domnode-ownerdocument.md) | 此节点所属的文档。 |

## 功能

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
