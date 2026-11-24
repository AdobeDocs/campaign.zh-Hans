---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 33%
---
# 文件存在

检查文件是否已存在于服务器上（作为文件或在资源表中）。

```text
XML exist = FilesExist ( XML files )
```

## 参数

**文件**&#x200B;文件(@name)及其MD5密钥(@md5)的列表和布尔值，指示它是否可以作为资源(@checkResource)。

## 返回值

**存在**&#x200B;结果列表（@md5和@exists）

## 功能

**架构：** [xtk:job](s-xtk-job.md)

**静态：**

是
