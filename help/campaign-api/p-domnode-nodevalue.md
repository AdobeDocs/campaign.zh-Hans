---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 15%
---
# 节点值

节点值。 该值取决于节点的类型。

```text
nodeValue
```

## 备注

此属性可使用读取和写入权限进行访问。 检索主题行并将其添加到工作流中查询活动的其他数据的示例：

```javascript
      Substring(NodeValue('/delivery/mailParameters/subject/text()',data), 1, 255)
```

从工作流中的扩充活动中检索主题行的示例：

```javascript
      Substring(NodeValue('/delivery/mailParameters/subject/text()',[target/data]), 1, 255)
```

## 功能

**类的属性：** [DOMNode](c-domnode.md)

**只读：**

是

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
