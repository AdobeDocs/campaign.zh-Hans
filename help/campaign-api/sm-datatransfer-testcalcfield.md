---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '55'
ht-degree: 27%
---
# TestCalcField

使用脚本中存储的样本行测试计算字段。

```text
XML calcFieldValues = TestCalcField ( XML dataTransferStep, String calcFieldName )
```

## 参数

定义了计算字段的&#x200B;**dataTransferStep**&#x200B;数据传输步骤

**calcFieldName**&#x200B;要测试的计算字段

## 返回值

**calcFieldValues**&#x200B;返回每个示例行的值列表(calcFieldValues/line)和字段名称(calcFieldValues/@name)

## 功能

**架构：** [xtk:dataTransfer](s-xtk-datatransfer.md)

**静态：**

是
