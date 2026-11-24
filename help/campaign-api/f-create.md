---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '93'
ht-degree: 11%
---
# 创建

创建与给定架构对应的新实体。

```text
create ( [content ])
```

## 参数

**content**&#x200B;与要创建的实体的XML对应的可选字符串。

## 返回值

以JavaScript对象的形式返回实体。

## 备注

创建不是全局函数，而是架构方法。 要调用它，必须按所需的架构为其添加前缀。 例如：

```javascript
var recipient = NLWS.nmsRecipient.create(
      {recipient: {
        email: "support@adobe.com", 
        lastName: "Adobe", 
        firstName: "Support"}})
recipient.save()
```

文档不会自动保存到数据库。 必须在实体上使用⌐⌐[save()](m-entity-save.md)方法。

## 功能

**可用位置：**

* 内容管理
* 投放属性
* 类型规则
* JSSP
* SOAP方法
* WebApp
* 工作流
