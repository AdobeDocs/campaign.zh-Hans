---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 8%
---
# 加载

> 警告：
>
> 通过文件API进行的访问仅限于&#x200B;**var**、**sftp**&#x200B;和Adobe Campaign的临时文件夹。

加载并返回与给定架构和键对应的实体。

```text
load (key)
```

## 参数

**key**&#x200B;与实体的键对应的字符串。

## 返回值

以JavaScript对象的形式返回实体。

## 备注

load不是全局函数，而是架构方法。 要调用它，必须按所需的架构为其添加前缀。 例如：

```javascript
var delivery = NLWS.nmsDelivery.load("12435")
```

可以随意修改此对象的属性和子属性。 与[get()](f-get.md)方法不同，文档不会自动保存在数据库中，您必须调用对象上的[save()](m-entity-save.md)方法。 如果在数据库中未找到该实体，则为错误并且脚本被中断。

## 功能

**可用位置：**

* 内容管理
* 投放属性
* 类型规则
* JSSP
* SOAP方法
* WebApp
* 工作流
