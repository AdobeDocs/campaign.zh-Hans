---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '59'
ht-degree: 28%
---
# GetFilesToDownload

返回由此传输使用且在服务器上找到的文件列表

```text
[ XML filesToDownload, XML filesNotToDownload ] = GetFilesToDownload ( Number jobId )
```

## 参数

**jobId**&#x200B;传输标识符

## 返回值

**filesToDownload**&#x200B;返回可以作为元素\[dataTransfer/properties/filesToDownload\]下载的文件列表

**filesNotToDownload**&#x200B;返回无法作为元素\[dataTransfer/properties/filesNotToDownload\]下载的文件列表

## 功能

**架构：** [xtk:dataTransfer](s-xtk-datatransfer.md)

**静态：**

是
