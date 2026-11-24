---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '69'
ht-degree: 13%
---
# 导出

生成并导出报告

```text
Export ( String reportName, XML context, String exportFormat, String fileName, Boolean isAdHoc )
```

## 参数

**reportName**&#x200B;报告的内部名称

**上下文**&#x200B;执行上下文。

**exportFormat**&#x200B;可能的值为：XLS、OOXML\_SS、ODF\_SS、PDF

XLS生成Excel 94-2003文档\
 OOXML\_SS生成一个Excel 2007文档\
 ODF\_SS生成Open文档

**文件名**&#x200B;输出文件名

**isAdHoc**&#x200B;指定导出是否涉及临时报告

## 返回值

无。

## 功能

**架构：** [xtk:report](s-xtk-report.md)

**静态：**

是
