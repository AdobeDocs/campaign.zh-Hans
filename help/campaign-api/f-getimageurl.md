---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '58'
ht-degree: 22%
---
# getImageUrl

启用生成公共资源访问URL

```text
getImageUrl (ID|internal name)
```

## 参数

公共资源的&#x200B;**ID\|内部名称** ID或资源的内部名称。

## 返回值

返回公共资源访问URL。

## 备注

必须在前端服务器上发布资源。 示例：

```xml
              <%= getImageUrl(content.@["banner-id"]) %>Code HTML généré :http://media.adobe.com/res/img/18cd386d9e8b7f35f3477ac6a9efd762.jpg
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
