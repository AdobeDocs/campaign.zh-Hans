---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 15%
---
# queryWithType

执行具有列类型规范的SELECT类型SQL查询。

```text
queryWithTypes (command, types [, value1, ... ])
```

## 参数

**命令** SQL命令。

**类型**&#x200B;包含列类型的表。

**value1， ...**&#x200B;命令变量。

## 返回值

用于循环查询结果的游标。

## 备注

警告：与“功能”部分中的说明相反，queryWithTypes函数在WebApp中不可用。 该函数与[query](m-dbengine-query.md)相同，具有添加的列类型。 在大多数情况下，不会使用列类型，因为可以自动推断列类型。 这就是[查询](m-dbengine-query.md)应首选的原因。 但在某些情况下，特别是对于Oracle和日期类型列，可能有必要明确类型。 列类型是以下列表中的字符串：

* 字符串
* datetime
* 日期
* time
* timespan
* double
* float
* 布尔值
* 字节
* 短
* 长
* int64
* 备忘录
* blob
* 链接
* 区间

示例：

```javascript
var cnx = application.getConnection()

var stmt = cnx.query("SELECT iOperatorId, sName, tsLastModified " +
                     "FROM xtkOperator " +
                     "WHERE iOperatorId > $(l)",
                     ["long", "string", "datetime"],
                     1000)
for each(var row in stmt)
  logInfo(row[0] + " : " + row[1] + " " + row[2])

cnx.dispose()
```

运算符必须具有“sql”权限才能使用此函数，否则将引发异常。

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
