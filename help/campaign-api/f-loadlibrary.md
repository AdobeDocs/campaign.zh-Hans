---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 11%
---
# loadLibrary

加载JavaScript库。

```text
loadLibrary (filename [, boolean ])
```

## 参数

**filename**&#x200B;要加载的JavaScript库的名称。

**布尔值**&#x200B;启用或禁用加载缓存。 默认情况下，为true。

> 注意：当参数设置为false时，您需要在loadLibrary调用被验证为运算符之前使用logon()函数。

## 返回值

无。

## 备注

默认情况下，将启用缓存。 如果禁用了缓存，则将为每次调用查询数据库。 此查询允许您加载最新版本的库。 示例： loadLibrary(&#39;xtk:shared/nl.js&#39;)

## 功能

**可用位置：**

* 内容管理
* 投放属性
* 投放消息
* 类型规则
* 导入
* JSSP
* SOAP方法
* WebApp
* 工作流
