---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 57%
---
# 作业

在应用程序服务器上执行的批处理作业

## 方法

| 方法 | 描述 |
| --- | --- |
| [取消](sm-job-cancel.md) | 取消任务 |
| [CheckIfJobInProcess](sm-job-checkifjobinprocess.md) | 检查作业是否仍在运行 |
| [执行](sm-job-execute.md) | 同步执行作业（在此模式下，进度信息和取消不可用）。 |
| [文件存在](sm-job-filesexist.md) | 检查文件是否已存在于服务器上（作为文件或在资源表中）。 |
| [GetJobsInProcess](sm-job-getjobsinprocess.md) | 返回当前运行的非外部作业 |
| [GetStatus](sm-job-getstatus.md) | 获取作业处理进度信息。 警告：此API不保证返回唯一日志条目的列表（调用方必须使用其ID删除重复项）。 |
| [HasWarning](sm-job-haswarning.md) | 查询是否已为此作业生成警告或错误 |
| [暂停](sm-job-pause.md) | 暂停作业 |
| [提交](sm-job-submit.md) | 提交作业以进行异步处理 |
| [SubmitFromModel](sm-job-submitfrommodel.md) | 从模板提交作业 |
| [SubmitSoapCall](sm-job-submitsoapcall.md) | 提交作业以进行异步处理 |
| [WaitJobCanceled](sm-job-waitjobcancelled.md) | 等待作业被取消 |

## 常规方法

| 方法 | 描述 |
| --- | --- |
| [创建](f-create.md) | 创建与给定架构对应的新实体。 |
| [加载](f-load.md) | 加载并返回与给定架构和键对应的实体。 |
| [保存](m-entity-save.md) | 在数据库中保存实体。 |
