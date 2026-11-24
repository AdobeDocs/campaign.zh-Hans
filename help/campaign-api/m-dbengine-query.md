---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 4%
---
# 查询

执行SELECT类型的SQL查询。

```text
query (command [, value1, ... ])
```

## 参数

**命令** SQL命令。

**value1， ...**&#x200B;命令的变量。

## 返回值

可让您对查询结果进行迭代的光标。

## 备注

警告：与“功能”部分中的说明相反，查询函数在WebApp中不可用。 变量将替换命令的参数。 变量类型必须与命令中声明的参数匹配。 可以使用以下类型：

* $(sz)字符串
* $(m)备注
* $(l)长
* $(s)短
* $(b)字节
* $(d)多次
* $(f)浮点数
* $(ts)时间戳
* $(dt)日期
* $(tm)时间
* $(dur)时间跨度

以下替换参数将自动替换为值，并且不需要链接变量。

* $(id)生成标识符
* $(id:NmsTrackingLogId)根据特定序列生成标识符
* $(curdate)当前日期和时间

游标上的迭代通过“for each”进行，并为每个恢复的行返回一个表。 表的每个元素都与查询的一个字段匹配，元素的类型取决于字段的类型。 示例：

```javascript
var cnx = application.getConnection()

var stmt = cnx.query("SELECT iOperatorId, sName, tsLastModified " +
                     "FROM xtkOperator " +
                     "WHERE iOperatorId > $(l)", 1000)
for each(var row in stmt)
  logInfo(row[0] + " : " + row[1] + " " + row[2])

cnx.dispose()
```

在此示例中，row\[0\]是一个与iOperatorId重合的数字，row\[1\]是一个与sName重合的字符字符串，row\[2\]是一个与tsLastModified重合的日期。 运算符需要“sql”权限才能使用此函数，否则将引发异常。

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
