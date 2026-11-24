---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '69'
ht-degree: 34%
---
# 生成预览

构建要投放的内容或输出文件行的预览（在外部模式下）。

```text
[ XML preview, XML queryResult ] = delivery.BuildPreview ( XML params ) const
```

## 参数

**参数**&#x200B;收件人过滤条件(@filter = &#39;@id = 5673&#39;)，内容标识符(@content = &#39;html&#39;， &#39;text&#39;， &#39;sms&#39;， &#39;webContent1&#39;， &#39;outputFile&#39;...)，@targetPart = 1345686...

## 返回值

**预览**&#x200B;返回生成的预览的所有参数

**queryResult**&#x200B;返回加载的数据以计算预览。

## 功能

**架构：** [nms:delivery](s-nms-delivery.md)

**静态：**

否

**常量：**

是

仅&#x200B;**键：**

否
