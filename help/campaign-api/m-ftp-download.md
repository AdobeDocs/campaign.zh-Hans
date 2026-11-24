---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '106'
ht-degree: 9%
---
# 下载

将文件从服务器下载到本地文件或内存。

```text
download (URL [, append ])
```

## 参数

要下载的文件的&#x200B;**URL** URL。

**附加**&#x200B;默认情况下，如果下载的文件已存在于本地磁盘上，则会被收到的新文件覆盖。 如果激活布尔值，则Adobe Campaign会将下载的内容与现有内容一起写入具有相同名称的文件中。

## 返回值

无。

## 备注

要恢复本地文件中的文件，请使用setFile方法启动。 示例：

```javascript
var ftp = new FTP
ftp.setFile("c:/rfc.txt")
ftp.download("ftp://ftp.funet.fi/pub/standards/RFC/rfc2068.txt")
```

## 功能

**类的方法：** [FTP](c-ftp.md)

**可用位置：**

* 内容管理
* 投放属性
* 类型规则
* JSSP
* SOAP方法
* WebApp
* 工作流
