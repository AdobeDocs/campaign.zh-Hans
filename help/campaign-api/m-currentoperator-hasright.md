---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '43'
ht-degree: 23%
---
# hasRight

测试运算符是否具有特定的命名权限。

```text
hasRight (name)
```

## 参数

**名称**&#x200B;正确名称。

## 返回值

如果运算符具有此权限，则为true。

## 备注

示例：

```javascript
      var hasAdminRight = application.operator.hasRight("admin")
```

## 功能

**类的方法：** [CurrentOperator](c-currentoperator.md)

**可用位置：**

* 内容管理
* 投放属性
* 类型规则
* JSSP
* SOAP方法
* WebApp
* 工作流
