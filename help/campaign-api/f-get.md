---
source-git-commit: 3319b56a62aa8a8364c7f2f85bc81708a66a5978
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 7%
---
# get

加载并返回与给定架构和键对应的实体。

```text
get ( [key or content ])
```

## 参数

**key或content**&#x200B;与XML内容实体的键对应的字符串，用于创建或启动新实体。

## 返回值

以JavaScript对象的形式返回实体。

## 备注

get不是全局函数，而是架构方法。 要调用它，必须按所需的架构为其添加前缀。 例如：

```javascript
var delivery = NLWS.nmsDelivery.get("12435")
```

可以随意修改此对象的属性和子属性。 如果修改了文档，则当脚本完成执行时，文档会自动保存到数据库中。 如果这不是创建操作，并且实体尚未在数据库中，则为错误操作，脚本将中断。

## 功能

**可用位置：**

* 内容管理
* 投放属性
* 类型规则
* JSSP
* SOAP方法
* WebApp
* 工作流
