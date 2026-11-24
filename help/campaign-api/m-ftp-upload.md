---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 20%
---
# 上传

将文件从本地文件下载到FTP服务器。

```text
upload (URL)
```

## 参数

**URL**&#x200B;服务器URL。

## 返回值

无。

## 备注

URL必须以“ftp:&#39;”开头，示例：

```javascript
var ftp = new FTP
ftp.setFile("c:/rfc.txt")
ftp.upload("ftp://ftp.funet.fi/pub/standards/RFC")
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
