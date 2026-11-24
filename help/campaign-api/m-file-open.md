---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 5%
---
# open

在读取或写入模式下打开文件。

```text
open ( [mode ] [, codepage ])
```

## 参数

**模式**&#x200B;文件打开模式。 模式可以是以下多个值之一：

* “r” — 以只读模式打开文件。 此模式为默认模式。
* “w” — 以写入模式打开文件。
* “a” — 以“附加”模式打开文件，写入文件的数据在末尾附加。

**代码页**&#x200B;文件编码。 编码可以是以下值之一：

* File.CODEPAGE\_CURRENT — 这是缺省代码页。
* File.CODEPAGE\_OEM
* File.CODEPAGE\_MAC
* File.CODEPAGE\_THREAD
* File.CODEPAGE\_LATIN1
* File.CODEPAGE\_LATIN2
* File.CODEPAGE\_ISOLATIN1
* File.CODEPAGE\_ISOLATIN2
* File.CODEPAGE\_OEMLATIN1
* File.CODEPAGE\_OEMLATIN2
* File.CODEPAGE\_UTF7
* File.CODEPAGE\_UTF8
* File.CODEPAGE\_ISOLATIN9
* File.CODEPAGE\_OEMUS
* File.CODEPAGE\_SHIFTJIS
* File.CODEPAGE\_BIG5
* File.CODEPAGE\_CHINESE
* File.CODEPAGE\_EUCKOREAN
* File.CODEPAGE\_UTF16LE
* File.CODEPAGE\_UTF16BE

## 返回值

无。

## 备注

如果无法打开文件，则会引发异常。

## 功能

**类的方法：** [文件](c-file.md)

**可用位置：**

* 内容管理
* 投放属性
* 类型规则
* JSSP
* SOAP方法
* WebApp
* 工作流
