---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '68'
ht-degree: 33%
---
# BuildPreviewFromId

构建要投放的内容或输出文件行的预览（在外部模式下）。

```text
[ XML preview, XML queryResult ] = BuildPreviewFromId ( Number deliveryId, XML params ) const
```

## 参数

**deliveryId**&#x200B;投放ID。

**参数**&#x200B;收件人过滤条件(@filter = &#39;@id = 5673&#39;)，内容标识符(@content = &#39;html&#39;， &#39;text&#39;， &#39;sms&#39;， &#39;webContent1&#39;， &#39;outputFile&#39;...)，@targetPart = 1345686...

## 返回值

**预览**&#x200B;返回生成的预览的所有参数。

**queryResult**&#x200B;返回加载的数据以计算预览。

## 示例

```javascript
var res = nms.delivery.BuildPreviewFromId(
                           deliveryId,
                           {params: {content: "html", filter: "@id=1234"}})
var preview     = res[0]
var queryResult = res[1]
```

## 功能

**架构：** [nms:delivery](s-nms-delivery.md)

**静态：**

是
