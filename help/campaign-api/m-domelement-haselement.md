---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '72'
ht-degree: 16%
---
# hasElement

通过验证给定的标准测试元素是否具有子元素。

```text
hasElement (tagName [, attrName ] [, attrValue ])
```

## 参数

**tagName**&#x200B;搜索元素的名称。

**attrName**&#x200B;必须验证给定值的属性的名称。

**attrValue**&#x200B;属性值。

## 返回值

如果元素通过验证给定数据而具有子项，则返回true，否则返回false。

## 功能

**类的方法：** [DOMElement](c-domelement.md)

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
