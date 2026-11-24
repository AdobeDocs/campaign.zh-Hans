---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 6%
---
# 添加

向集合中添加新实体。

```text
add ( [index ], xml)
```

## 参数

**index**&#x200B;将在此索引点处添加实体。 如果未指定此参数，则实体将被附加到列表的末尾。

**xml**&#x200B;要插入到XML表单中的实体。

## 返回值

已创建的元素。

## 备注

以下示例显示了将新要素添加到集合的两种不同方式。 第一个解决方案将元素的完整定义传递给add()方法，而第二个解决方案则传递空的&lt;attachment/>元素，然后以正常方式分配属性。

```javascript
var delivery = NLWS.nmsDelivery.load("12435")

delivery.attachment.add(
  {attachment: {
    compressMode: "print", filterActive: "false", label: "First File", 
    nameScriptActive: "false", type: "normal", upload: "false", 
    name: { $: "file1.txt" }
  }})

var attach = delivery.attachment.add()
attach.label            = "Second File"
attach.name             = "file2.txt"
attach.compressMode     = "print"
attach.type             = "normal"
attach.filterActive     = false
attach.nameScriptActive = false
attach.upload           = false

delivery.save()
```

这两种解决方案是等效的，但第二种解决方案允许您使用与属性类型相对应的JavaScript类型，而第一种解决方案仅支持字符串。

## 功能

**类的方法：** [EntityCollection](c-entitycollection.md)

**可用位置：**

* 内容管理
* 投放属性
* 类型规则
* JSSP
* SOAP方法
* WebApp
* 工作流
