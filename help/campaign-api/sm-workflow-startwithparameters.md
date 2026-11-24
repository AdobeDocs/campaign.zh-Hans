---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '92'
ht-degree: 4%
---
# StartWithParameters

启动工作流并为其提供参数。

```text
StartWithParameters ( String workflowId, XML parameters )
```

## 参数

**workflowId**&#x200B;工作流的标识符或内部名称。

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

无。

## 备注

命令是异步执行的，在方法返回后不会立即生效。

## 功能

**架构：** [xtk:workflow](s-xtk-workflow.md)

**静态：**

是
