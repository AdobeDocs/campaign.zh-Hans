---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '54'
ht-degree: 29%
---
# GetFilesToDownload

返回在与投放关联的服务器上找到的文件列表。

```text
[ XML filesToDownload, XML filesNotToDownload ] = GetFilesToDownload ( Number deliveryId )
```

## 参数

**deliveryId**&#x200B;投放标识符

## 返回值

**filesToDownload**&#x200B;返回可以作为元素\[properties/filesToDownload\]下载的文件列表

**filesNotToDownload**&#x200B;返回无法作为元素\[properties/filesNotToDownload\]下载的文件列表

## 功能

**架构：** [nms:delivery](s-nms-delivery.md)

**静态：**

是
