---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '56'
ht-degree: 35%
---
# 执行

同步执行作业（在此模式下，进度信息和取消不可用）。

```text
String id = job.Execute ( String methodName ) const
```

## 参数

**methodName**&#x200B;要在实体上调用的方法的名称

## 返回值

**id**&#x200B;已创建作业的标识符（如果在数据库中创建作业，即使该作业失败也会返回）

## 功能

**架构：** [xtk:job](s-xtk-job.md)

**静态：**

否

**常量：**

是

仅&#x200B;**键：**

否
