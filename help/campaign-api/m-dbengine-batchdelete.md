---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '65'
ht-degree: 15%
---
# batchDelete

按数据包删除表的记录。

```text
batchDelete (table, pk [, where ])
```

## 参数

**表**&#x200B;表的SQL名称。

**pk**&#x200B;用作主键的字段名。

**其中** SQL记录过滤条件。

## 返回值

无。

## 备注

示例：

```javascript
      engine.batchDelete("NmsRecipient", "iRecipientId", "sName IS NULL")
```

运算符需要“sql”权限才能使用此函数，否则将引发异常。

## 功能

**类的方法：** [DBEngine](c-dbengine.md)

**可用位置：**

* 内容管理
* 投放属性
* 类型规则
* JSSP
* SOAP方法
* WebApp
* 工作流
