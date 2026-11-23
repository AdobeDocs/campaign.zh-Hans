---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 5%
---
# sqlGetMemo

返回由SQL查询生成的Memo字段。

```text
sqlGetMemo (query [, value1, ... ])
```

## 参数

**查询** SQL查询。

**value1， ...** SQL查询的变量。

## 返回值

与查询匹配的“备注”字段。

## 备注

变量将替换命令中的参数。 变量类型必须与命令中声明的参数一致。 这些变量在“select”或“update”类型声明中可用。 我们有以下类型：

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
* $(dur)时间跨度（毫秒）

以下替换参数（仅对“update”有效）将自动替换为值，并且不需要链接变量。

* $(id)生成标识符
* $(id:NmsTrackingLogId)使用特定序列生成标识符
* $(curdate)当前日期和时间

使用变量不会影响Adobe Campaign的性能。 SQL查询必须选择单行和单文本类型字段。 运算符必须具有“sql”权限才能使用此函数，否则将引发异常。 示例：

```javascript
      var logData = sqlGetMemo('select log from IncomingLog where sEmail =$(sz) order by tsCreated DESC LIMIT 1', email)
```

## 功能

**可用位置：**

* 内容管理
* 投放属性
* 类型规则
* JSSP
* SOAP方法
* WebApp
* 工作流
