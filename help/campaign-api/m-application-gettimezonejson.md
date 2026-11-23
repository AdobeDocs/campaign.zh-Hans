---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 5%
---
# getTimezoneJson

返回一个字符串，该字符串是UTC时间及其开始日期与时区的UNIX时段相比的时间差列表的JSON表示形式。

```text
getTimezoneJson ( [timezone ])
```

## 参数

**时区**&#x200B;您需要返回与UTC时差列表的时区的名称。 每次差异均链接到适用到下一个开始日期的开始日期。 如果未返回值，则使用默认运算符时区。

## 返回值

返回一个字符串，该字符串是用于表示基于日期应用的时间差异的JSON表示形式。 将在{startDate， offset}对的表中评估返回的JSON字符串。 返回的字符串具有以下形式：

```javascript
[
  {"startDate" : -1855958901000, "offset" : 0},
  {"startDate" : -1689814800000, "offset" : 3600000}
]
```

* startDate是从应用失效开始的Posix时间。
* offset是与UTC的时间差值（以毫秒为单位）。 例如，UTC+02:00等于7200000。

## 备注

通过应用程序实例调用getTimezoneJson。

```javascript
var tzList = eval(application.getTimezoneJson());
```

## 功能

**类的方法：** [应用程序](c-application.md)

**可用位置：**

* 内容管理
* 投放属性
* 类型规则
* JSSP
* SOAP方法
* WebApp
* 工作流
