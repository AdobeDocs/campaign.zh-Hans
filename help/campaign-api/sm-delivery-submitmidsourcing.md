---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 21%
---
# SubmitmidSourcing

以中间源模式提交投放。

```text
[ Number remoteId, Number remoteMatchId ] = SubmitMidSourcing ( XML delivery, XML routingMatch, String folderName )
```

## 参数

表示投放的&#x200B;**投放**&#x200B;文档。

**routingMatch**&#x200B;不再使用

**folderName**&#x200B;完整文件夹名称（在发件人数据库中）。

## 返回值

接收方数据库中投放的&#x200B;**remoteId**&#x200B;标识符。

**remoteMatchId**&#x200B;不再使用

## 功能

**架构：** [nms:delivery](s-nms-delivery.md)

**静态：**

是
