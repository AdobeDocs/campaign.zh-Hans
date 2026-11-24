---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 3%
---
# generateTrackingTag

自动为Web跟踪生成JavaScript标记。

```text
generateTrackingTag (request [, tagid ] [, folder ])
```

## 参数

**请求** HttpServletRequest对象

**tagid**&#x200B;表示个性化tagid名称的字符串。 如果为空，则函数根据路径名称生成标记。

**文件夹**&#x200B;表示文件夹内部名称的字符串。 如果为空，则会在默认目录中创建标记，即“Web跟踪标记”。

## 返回值

一个字符串，其中包含要包含的JavaScript代码。

## 备注

生成的标记基于Web应用程序的名称、HTML页面、控制器或更一般而言，如果未输入tagid，则基于路径名称。 最后一个参数指定标记目标文件夹。 要调用函数，请将请求对象作为参数传递。 请注意是否使用了&lt;%==，因为函数会生成html代码。 示例：

```xml
              <%== generateTrackingTag(request, request.getParameter('art'), request.getParameter('cat')) %>
```

## 功能

**可用位置：**

* JSSP
* WebApp
