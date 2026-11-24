---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 8%
---
# 执行

立即执行工作流并等待它完成。

```text
XML workflow = Execute ( String workflowId, Boolean simulationMode, Boolean keepResult, Boolean logSQL )
```

## 参数

**workflowId**&#x200B;工作流的标识符或内部名称。

**simulationMode**&#x200B;执行模拟。

**keepResult**&#x200B;保留中期结果。

**logSQL**&#x200B;是否需要保存SQL订单的跟踪？

## 返回值

**工作流**&#x200B;执行结果。

## 功能

**架构：** [xtk:workflow](s-xtk-workflow.md)

**静态：**

是
