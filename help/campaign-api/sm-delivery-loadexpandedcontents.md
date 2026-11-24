---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '55'
ht-degree: 38%
---
# LoadExtendedContents

加载组件列表以进行具有依赖关系的预处理（个性化块、选项、附加脚本对象等）。

```text
XML material = delivery.LoadExpandedContents ( String ids ) const
```

## 参数

**ids**&#x200B;以逗号分隔的组件标识符列表（例如，&#39;option\|NmsServer\_URL\|text，includeView\|UnsubscriptionLink\|html&#39;）。

## 返回值

**材料**&#x200B;以“材料”元素形式返回内容。

## 功能

**架构：** [nms:delivery](s-nms-delivery.md)

**静态：**

否

**常量：**

是

仅&#x200B;**键：**

否
