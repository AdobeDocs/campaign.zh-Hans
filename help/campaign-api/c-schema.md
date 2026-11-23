---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 8%
---
# 架构（类）

表示架构定义。

通过调用`application`全局变量的方法获取架构。 此对象的实例将对象作为原型，因此会继承其方法。

## 方法

| 方法 | 描述 |
| --- | --- |
| [toDocument](m-schema-todocument.md) | 将架构转换为XML文档表单。 |

## 属性

| 属性 | 描述 |
| --- | --- |
| [枚举](p-schema-enumerations.md) | 返回包含此架构中定义的[枚举](c-enumeration.md)列表的表。 |
| [id](p-schema-id.md) | 字符串形式的架构标识符。 |
| [isLibrary](p-schema-islibrary.md) | 返回一个布尔值，该值指定架构是否为组件库。 |
| [标签单数](p-schema-labelsingular.md) | 字符串形式的架构的单数名称。 |
| [mappingType](p-schema-mappingtype.md) | 字符串形式的架构映射的特性 |
| [md5](p-schema-md5.md) | 以十六进制字符串形式表示的架构的MD5代码。 |
| [命名空间](p-schema-namespace.md) | 字符串形式的架构命名空间。 |
| [根](p-schema-root.md) | 架构的主元素，如果未定义，则为null。 |
| [用户描述](p-schema-userdescription.md) | 以字符串形式显示的架构描述。 |

## 功能

**可用位置：**

* 内容管理
* 投放属性
* 类型规则
* JSSP
* SOAP方法
* WebApp
* 工作流
