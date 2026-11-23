---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 21%
---
# getCurrentDate

返回数据库服务器的当前日期。

```text
getCurrentDate ()
```

## 参数

无。

## 返回值

数据库服务器的当前日期。

## 备注

示例：

```javascript
      date = formatDate(getCurrentDate(),"%4Y/%2M/%2D %02H:%02N:%02S")
```

有关formatDate()函数的更多信息，请参阅[formatDate(date， format)](f-formatdate.md)

## 功能

**可用位置：**

* 内容管理
* 投放属性
* 类型规则
* JSSP
* SOAP方法
* WebApp
* 工作流
