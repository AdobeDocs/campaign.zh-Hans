---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 2%
---
# 工作流

工作流定义

## 方法

| 方法 | 描述 |
| --- | --- |
| [清理](sm-workflow-cleanup.md) | 清除工作流历史记录。 |
| [DeleteResult](sm-workflow-deleteresult.md) | 擦除一个或多个活动的结果。 |
| [执行](sm-workflow-execute.md) | 立即执行工作流并等待它完成。 |
| [ExecuteInstance](sm-workflow-executeinstance.md) | 立即执行工作流并等待它完成。 |
| [GetLogin](sm-workflow-getlogin.md) | 从执行帐户返回信息。 |
| [GetValidationParameters](sm-workflow-getvalidationparameters.md) | 返回正在进行的工作流任务的参数。 |
| [终止](sm-workflow-kill.md) | 无条件停止工作流。 |
| [暂停](sm-workflow-pause.md) | 暂停执行正在进行的工作流。 |
| [PostEvent](sm-workflow-postevent.md) | 从任何类型的活动生成事件。 |
| [回复](sm-workflow-reply.md) | 响应正在进行的验证类型任务。 |
| [重新启动](sm-workflow-restart.md) | 将工作流停止和工作流启动链接在一起。 |
| [重新启动任务](sm-workflow-restarttask.md) | 强制重新启动一个或多个已完成的任务。 |
| [SetLogin](sm-workflow-setlogin.md) | 更改执行帐户。 |
| [模拟](sm-workflow-simulate.md) | 在模拟模式下启动工作流。 |
| [SimulateWithParameters](sm-workflow-simulatewithparameters.md) | 在模拟模式下启动工作流并提供参数。 |
| [派生](sm-workflow-spawn.md) | 从模板创建工作流实例，应用补丁然后启动此工作流。 |
| [SpawnWithParameters](sm-workflow-spawnwithparameters.md) | 从模板创建工作流实例，然后调用此实例上的[StartWithParameters](sm-workflow-startwithparameters.md)方法。 |
| [SpawnWithParametersEx](sm-workflow-spawnwithparametersex.md) | 从模型创建工作流实例，并在此实例上调用方法[StartWithParameters](sm-workflow-startwithparameters.md)或[SimulateWithParameters](sm-workflow-simulatewithparameters.md)。 |
| [开始](sm-workflow-start.md) | 开始或恢复工作流的执行。 |
| [StartWithParameters](sm-workflow-startwithparameters.md) | 启动工作流并为其提供参数。 |
| [停止](sm-workflow-stop.md) | 停止正在进行的工作流。 |
| [唤醒](sm-workflow-wakeup.md) | 强制提前处理所有待处理任务。 |
| [WakeupTask](sm-workflow-wakeuptask.md) | 强制提前处理一个或多个待处理任务。 |

## 常规方法

| 方法 | 描述 |
| --- | --- |
| [创建](f-create.md) | 创建与给定架构对应的新实体。 |
| [加载](f-load.md) | 加载并返回与给定架构和键对应的实体。 |
| [保存](m-entity-save.md) | 在数据库中保存实体。 |
