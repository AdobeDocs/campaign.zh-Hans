---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '54'
ht-degree: 27%
---
# escapeXmlStr

将字符串转换为XML格式。

```text
escapeXmlStr (value)
```

## 参数

要转换的&#x200B;**值**&#x200B;字符串。

## 返回值

转换后的字符串。

## 备注

函数会将&amp;、&lt;、>和\\”字符转换为相应的转义序列：

* &amp;amp；
* &lt; &lt;
* > >
* &quot; &amp;quot;

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
