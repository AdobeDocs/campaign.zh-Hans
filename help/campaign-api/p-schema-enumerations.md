---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '37'
ht-degree: 27%
---
# 明细列表

返回包含此架构中定义的[枚举](c-enumeration.md)列表的表。

```text
enumerations
```

## 备注

示例：

```javascript
var schema = application.getSchema("nms:delivery")
for each(var e in schema.enumerations)
{
  logInfo(e.name)
}
```

## 功能

**类的属性：** [架构](c-schema.md)

**只读：**

是

**可用位置：**

* 内容管理
* 投放属性
* 类型规则
* JSSP
* SOAP方法
* WebApp
* 工作流
