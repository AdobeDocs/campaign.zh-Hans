---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 11%
---
# getUrl

从URL恢复文本内容。

```text
getUrl (url [, timeout ])
```

## 参数

**url**&#x200B;要恢复的页面地址。

**超时**&#x200B;连接超时。 如果在给定的延迟内无法建立连接，则会引发错误并中断脚本。

## 返回值

包含文本页面的字符串。

## 备注

返回的字符串的编码是由响应(Content-Type)指定的编码。 如果在下载期间发生错误或返回代码不是200（确定），则会引发错误并中断正在执行的脚本。 示例：

```javascript
      var content = getUrl("http://www.google.com/index.html")
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
