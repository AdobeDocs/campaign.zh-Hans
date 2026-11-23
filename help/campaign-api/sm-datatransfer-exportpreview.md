---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 16%
---
# 导出预览

计算查询第一行的输出文件列预览

```text
[ XML resultColumns, XML resultXML, String resultSQLRequest ] = ExportPreview ( XML dataTransferStep, Number lineCount, Boolean countMode, String calcFieldName )
```

## 参数

定义了计算字段的&#x200B;**dataTransferStep**&#x200B;传输步骤。

**lineCount**&#x200B;要返回的行数

**countMode**&#x200B;行计数模式

**calcFieldName**&#x200B;观察到的计算字段的名称。 如果为空，则为输出文件的全局预览。

## 返回值

**resultColumns**&#x200B;返回导出文件列的值(line/col/val、line/col/errors)。

**resultXML**&#x200B;返回查询的输出XML文档。

**resultSQLRequest**&#x200B;返回执行的SQL查询。

## 功能

**架构：** [xtk:dataTransfer](s-xtk-datatransfer.md)

**静态：**

是
