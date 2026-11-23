---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '119'
ht-degree: 9%
---
# HttpClientResponse（类）

表示对HTTP查询的响应的对象。

只能在`response`属性执行HTTP查询后获取。

## 属性

| 属性 | 描述 |
| --- | --- |
| [正文](p-httpclientresponse-body.md) | 以MemoryBuffer对象形式表示的HTTP响应主体。 |
| [代码](p-httpclientresponse-code.md) | 以JavaScript整数形式表示的HTTP响应的返回代码。 |
| [代码页](p-httpclientresponse-codepage.md) | 响应的codePage的值。 用于解码HTTP响应的正文。 |
| [标头](p-httpclientresponse-header.md) | 包含所有HTTP标头的对象。 |
| [标头](p-httpclientresponse-headers.md) | 按名称分组的HTTP响应的标头列表。 |
| [消息](p-httpclientresponse-message.md) | HTTP响应携带的消息。 |

## 功能

**可用位置：**

* 内容管理
* 投放属性
* 类型规则
* JSSP
* SOAP方法
* WebApp
* 工作流
