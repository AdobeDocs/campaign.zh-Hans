---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 2%
---
# SpawnWithParameters

从模板创建工作流实例，然后调用此实例上的[StartWithParameters](sm-workflow-startwithparameters.md)方法。

```text
Number instanceId = SpawnWithParameters ( String workflowId, XML parameters )
```

## 参数

**workflowId**&#x200B;工作流模板的标识符或内部名称。

**参数**&#x200B;要传递给实例的参数。 这些参数将成为工作流的实例变量。 此参数是一个XML元素，其名称必须是变量并且只能包含属性。 示例：

```xml
<variables foo="abc" bar="def">
```

工作流中的JavaScript脚本可以从instance.vars对象访问这些变量：

```javascript
    var foo = instance.vars.foo   // "abc"
    var bar = instance.vars.bar   // "def"
            
```

## 返回值

从模板创建的实例的&#x200B;**instanceId**&#x200B;标识符。

## 备注

该命令以异步模式执行，在方法返回后不会立即生效。 工作流从调用操作员的帐户开始，除非特定登录链接到工作流登录表中的模板，在这种情况下使用此登录。

## 功能

**架构：** [xtk:workflow](s-xtk-workflow.md)

**静态：**

是
