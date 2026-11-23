---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '99'
ht-degree: 10%
---
# 列表

返回服务器上指定目录中的文件列表。

```text
list (URL, pattern [, max ])
```

## 参数

FTP服务器的&#x200B;**URL**&#x200B;地址作为URL。

**pattern**&#x200B;要检索的文件列表的文件和掩码。

**最大**&#x200B;要返回的最大文件数。 如果缺少此参数，此方法将返回文件的完整列表。

## 返回值

包含与指定路径和掩码对应的文件名的表。

## 备注

如果FTP命令失败，则会引发异常。 示例：

```javascript
var ftp = new FTP
var files = ftp.list("ftp://ftp.funet.fi/", "pub/standards/RFC/rfc*.txt", 10)
for(var i in files)
  logInfo(files[i])
ftp.dispose()
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
