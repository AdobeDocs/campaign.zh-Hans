---
title: 跟踪个性化链接
description: 了解如何跟踪电子邮件中的个性化链接
feature: Personalization
role: User
level: Beginner
exl-id: d0e00b40-e7dd-4484-b37c-fd3f3ac70fda
source-git-commit: 6e465ec24f72d0b30c4fc287da5d4c4bcaeda05b
workflow-type: tm+mt
source-wordcount: '637'
ht-degree: 2%

---

# 跟踪个性化链接 {#tracking-personalized-links}

电子邮件内容中包含个性化的链接需要跟踪特定语法。

在电子邮件内容(HTML或文本)中使用JavaScript允许您生成动态内容并将其发送给收件人，但存在两个限制：

* 脚本无法直接访问数据库（SQL函数和API函数不可用），
* Adobe Campaign必须能够检测URL，以便可以跟踪链接。

## 预处理指令 {#pre-processing-instructions}

您可以添加特定的预处理指令来编写URL的脚本并对其进行跟踪。 这些说明必须在JavaScript中编写并以`<%@`开头。

例如：

```
<%@ value object="myObject" xpath="@myField" %>
```

此指令从`myField`对象中检索`myObject`字段的值。

## URL检测 {#url-detection}

对于跟踪检测，Adobe Campaign嵌入[Tidy](https://www.html-tidy.org/)以解析HTML源并检测模式。 其中列出了内容的所有URL，以便可以单独对其进行跟踪。 Adobe Campaign再次使用Tidy将URL (`http://myurl.com`)替换为指向Adobe Campaign重定向服务器的URL。

例如，在初始内容中： `http://myurl.com/a.php?name=<%=escapeUrl(recipient.lastName)%>`被替换为一个特定收件人： `http://emailing.customer.com/r/?id=h617791,71ffa3,71ffa8&p1=CustomerName`

其中：

* “h”表示HTML内容（或者“t”表示文本内容）。
* 617791是消息ID/broadLog ID（十六进制）。
* 71ffa3是NmsDelivery ID（十六进制）。
* 71ffa8是NmsTrackingUrl ID（十六进制）。
* p1、p2等都是要在URL中替换的参数。

### 非检测示例 {#non-detection-example}

`<%= getURL("http://mynewsletter.com") %>`工作，并通过电子邮件将网页的实际内容发送给收件人。 但这些链接都未被跟踪。 原因是MTA在发送之前对每个电子邮件执行`"<%=getURL(..."`。 由于每个收件人的名称可能不同，因此Adobe Campaign无法知道用于跟踪的URL并为他们分配标记ID。

当所有收件人的下载页面都相同时，最佳实践为使用：

```
<%@ include url="http://mynewsletter.com" %>
```

在这种情况下，页面将在分析期间以及跟踪检测之前下载。 它允许Adobe Campaign发现链接、分配标记ID并跟踪它们。

### 推荐的模式 {#recommended-pattern}

在处理`<%@`说明后，要跟踪的URL应具有以下语法：

```
<a href="http://myurl.com/a.php?param1=aaa&param2=<%=escapeUrl(recipient.xxx)%>&param3=<%=escapeUrl(recipient.xxx)%>">
```

>[!IMPORTANT]
>
>所有其他模式均不受Adobe支持，应避免使用，以防止潜在的安全漏洞。

## URL 参数 {#url-parameters}

为确保正确跟踪个性化URL，您必须对URL中的参数使用`escapeUrl()`函数或相应的编码方法。

**示例：**

```
<a href="http://myurl.com/a.php?name=<%=escapeUrl(recipient.lastName)%>">Click here</a>
```

这将确保Adobe Campaign正确编码和跟踪个性化参数。

## 与`<%@ foreach %>`循环 {#foreach}

`<%@ foreach %>`指令允许您对投放中加载的对象数组进行迭代，以跟踪与对象相关的单个链接。

### 语法

```
<%@ foreach object="myObject" xpath="myLink" index="3" item="myItem" %>
  <!-- Content to repeat -->
<%@ end %>
```

**参数：**

* **`object`**：要从中开始的对象的名称（通常是额外的脚本对象，但可以是投放）
* **`xpath`** （可选）：要循环的集合的XPath。 默认值为“。”，这意味着对象是要循环处理的数组
* **`index`** （可选）：如果xpath不是“。” 而对象本身是一个数组，即对象的项索引（从0开始）
* **`item`** （可选）： foreach循环中可通过`<%@ value %>`访问的新对象的名称。 默认值为架构中的链接名称

### 示例

在投放属性/个性化中，加载项目数组，以及收件人和项目之间的关系表。

您可以通过单独跟踪显示指向这些文章的链接：

```
<%@ foreach object="articleList" item="article" %>
  <a href="http://example.com/article.jsp?id=<%@ value object="article" xpath="@id" %>">
    <%@ value object="article" xpath="@title" %>
  </a>
<%@ end %>
```

这允许Adobe Campaign跟踪每个收件人点击了哪些特定文章，而不是仅跟踪是否点击了文章链接。

## 最佳实践 {#best-practices}

* 始终将`escapeUrl()`函数用于动态URL参数
* 当您需要跟踪收藏集中的单个项目时使用`<%@ foreach %>`
* 在发送投放之前测试跟踪，以确保所有链接正常工作
* 验证投放内容中的个性化链接格式是否正确
* 检查跟踪日志，以确认正确捕获了个性化参数

## 相关主题 {#related-topics}

* [了解如何配置跟踪的链接](tracked-links.md)
* [了解如何配置URL跟踪选项](url-tracking.md)
* [了解如何添加个性化字段](personalization-fields.md)

