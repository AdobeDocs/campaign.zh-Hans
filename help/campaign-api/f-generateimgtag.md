---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 20%
---
# generateImgTag

允许基于公共资源生成HTML &lt;img>标记。

```text
generateImgTag (ID)
```

## 参数

**ID**&#x200B;公共资源ID

## 返回值

返回带有公共资源定义中包含的图像属性的HTML &lt;img>标记。

## 备注

必须在前端服务器上发布资源。 示例：

```xml
              <%= generateImgTag(content.@["banner-id"]) %>Code HTML généré :<img src="http://media.adobe.com/res/img/18cd386d9e8b7f35f3477ac6a9efd762.jpg" width="800" height="200" alt="My image"/>
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
