---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '82'
ht-degree: 15%
---
# escapeUrl

转换字符串以将其插入到URL中。

```text
escapeUrl (value)
```

## 参数

要转换的&#x200B;**值**&#x200B;字符串。

## 返回值

转换后的字符串。

## 备注

函数会将$-\_.\！\*&#39;()、？/：@&amp;=以外的非字母数字字符转换为相应的十六进制值。 函数符合RFC1738规范，并且仅允许您编码ISO — 拉丁字符。 要编码UTF-8字符，请使用encodeURIComponent() JavaScript函数。 示例：

```javascript
escapeUrl("a#value!")               // "a%23value!"
escapeUrl("Système d'exploitation") // "Syst%E8me%20d'exploitation"
```

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
