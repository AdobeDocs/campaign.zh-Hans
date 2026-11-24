---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 77%
---
# 投放

此架构表示投放操作或模板。

模板是包含所有必要参数的投放模板。 投放模板可以从客户端控制台手动执行，也可以在事件发生时执行（从调度程序启动，或从SOAP调用以编程方式启动）。

## 方法

| 方法 | 描述 |
| --- | --- |
| [AppendDeliveryPart](sm-delivery-appenddeliverypart.md) | 将一个部分添加到正在准备的投放中。 |
| [BuildForward](sm-delivery-buildforward.md) | 构建 HTML 页面。 |
| [BuildMirror](sm-delivery-buildmirror.md) | 构建 HTML 镜像页面。 |
| [BuildMirrorEx](sm-delivery-buildmirrorex.md) | 构建 HTML 镜像页面。 |
| [生成预览](sm-delivery-buildpreview.md) | 构建要投放的内容或输出文件行的预览（在外部模式下）。 |
| [BuildPreviewFromId](sm-delivery-buildpreviewfromid.md) | 构建要投放的内容或输出文件行的预览（在外部模式下）。 |
| [BuildTargetDataSchema](sm-delivery-buildtargetdataschema.md) |  |
| [CleanupDeliveries](sm-delivery-cleanupdeliveries.md) | 指定中间源服务器应删除某些投放。 |
| [CollectLogs](sm-delivery-collectlogs.md) | 为投放列表创建一个包含所有投放日志消息的表 |
| [CreateFromModel](sm-delivery-createfrommodel.md) | 从模板（从其内部名称）创建投放。 |
| [DeployTriggerMessageSingle](sm-delivery-deploytriggermessagesingle.md) | 在执行实例上发布事务性消息。 如果发布成功，则返回真，否则返回假。 |
| [DeployTriggerMessage](sm-delivery-deploytriggermessages.md) | 在执行实例上发布选定的交易型消息 |
| [诊断HTML](sm-delivery-diagnosehtml.md) | 启动 HTML 内容诊断 |
| [派单图像](sm-delivery-dispatchimages.md) | 告诉应用程序服务器将图像发送到中间源服务器。 |
| [ExecCommand](sm-delivery-execcommand.md) | 在投放时执行命令。 |
| [ExecuteJob](sm-delivery-executejob.md) | 对投放执行同步过程。 |
| [FinalizeMidPreparation](sm-delivery-finalizemidpreparation.md) | 在中间源模式下完成对投放的分析。 |
| [GetDeviceList](sm-delivery-getdevicelist.md) |  |
| [GetDlStatusAndLogs](sm-delivery-getdlstatusandlogs.md) | 从日志中检索最后的日志和投放状态。 |
| [GetFilesToDownload](sm-delivery-getfilestodownload.md) | 返回在与投放关联的服务器上找到的文件列表。 |
| [GetMidBroadLogs](sm-delivery-getmidbroadlogs.md) | 检索在中间源模式下最后修改的投放日志。 |
| [GetMidDeliveries](sm-delivery-getmiddeliveries.md) | 检索在中间源模式下最后修改的投放状态。 |
| [GetMidXtkKey](sm-delivery-getmidxtkkey.md) | 返回中间服务器的 Xtk 密钥 |
| [GetMirrorURL](sm-delivery-getmirrorurl.md) | 获取 HTML 镜像页面的 URL。 |
| [GetSeedList](sm-delivery-getseedlist.md) |  |
| [HtmlToText](sm-delivery-htmltotext.md) | 将 HTML 内容转换为纯文本 |
| [图像发布](sm-delivery-imagepublishing.md) | 执行后期处理：将图像移动到指定文件夹并使其在线可用 |
| [InstallTransactiveMessage](sm-delivery-installtransactionalmessage.md) | 在执行实例上安装交易型消息模板。 |
| [InvalidateDeliveryCache](sm-delivery-invalidatedeliverycache.md) | 必须在消息准备结束时调用，除了中间源（私有方法）。 |
| [LaunchFCP](sm-delivery-launchfcp.md) | 开始投放的校样副本 |
| [加载扩展的内容](sm-delivery-loadexpandedcontents.md) | 加载组件列表以进行具有依赖关系的预处理（个性化块、选项、附加脚本对象等）。 |
| [暂停](sm-delivery-pause.md) | 暂停投放。 |
| [播放](sm-delivery-play.md) | 开始投放。 |
| [准备](sm-delivery-prepare.md) | 投放分析：目标选择和个性化 |
| [PrepareAndStart](sm-delivery-prepareandstart.md) | 分析投放并在没有遇到错误的情况下立即执行投放 |
| [PrepareFromId](sm-delivery-preparefromid.md) | 分析投放。 |
| [PrepareMessage](sm-delivery-preparemessage.md) | 消息个性化 |
| [PrepareMessageImpl](sm-delivery-preparemessageimpl.md) | 消息个性化 |
| [PrepareMultipartRelated](sm-delivery-preparemultipartrelated.md) | 保存图像以包含在数据库中的电子邮件中 |
| [PrepareNotification](sm-delivery-preparenotification.md) | 分析添加到现有投放操作的通知 |
| [PrepareProof](sm-delivery-prepareproof.md) | 基于生成校样的投放分析 |
| [PrepareTarget](sm-delivery-preparetarget.md) | 投放目标计数和仲裁 |
| [PrepareTargetImpl](sm-delivery-preparetargetimpl.md) | 投放目标计数和仲裁 |
| [PreviewExtraction](sm-delivery-previewextraction.md) | 提取文件预览 |
| [优先级日志](sm-delivery-prioritizelogs.md) | 优先考虑投放日志以获取投放列表 |
| [优先目标](sm-delivery-prioritizetarget.md) | 投放目标仲裁 |
| [队列通知](sm-delivery-queuenotification.md) | 请求对引用投放模板的通知进行排队。 |
| [重新计算统计信息](sm-delivery-recomputestats.md) | 重新计算投放操作的投放和跟踪统计信息。 |
| [SaveUrlInfo](sm-delivery-saveurlinfo.md) | 将此投放的 URL 另存为 URL 模板。 |
| [停止](sm-delivery-stop.md) | 停止正在进行的投放。 |
| [StoreMirrorPageInfo](sm-delivery-storemirrorpageinfo.md) | 添加信息以生成一组投放部分的镜像页面。 |
| [StoreMirrorPageInfoEx](sm-delivery-storemirrorpageinfoex.md) | 添加信息以生成一组投放部分的镜像页面。 |
| [SubmitDelivery](sm-delivery-submitdelivery.md) | 从场景创建和提交投放（来自其内部名称）。 |
| [SubmitDeliveryById](sm-delivery-submitdeliverybyid.md) | 从场景创建并提交投放（由其内部名称标识）。 |
| [提交作业](sm-delivery-submitjob.md) | 提交投放作业以进行异步处理 |
| [SubmitMidSourcing](sm-delivery-submitmidsourcing.md) | 以中间源模式提交投放。 |
| [SubmitNotification](sm-delivery-submitnotification.md) | 从场景创建并提交通知。 |
| [UpdateBroadLogs](sm-delivery-updatebroadlogs.md) | 更新投放日志的状态，执行错误处理并更新投放计数器。 |
| [UpdateCachedDelivery](sm-delivery-updatecacheddelivery.md) | 每次在内存中修改投放时都必须调用，以便其他会话可以访问最新版本（私有方法）。 |
| [UpdateImageConfig](sm-delivery-updateimageconfig.md) | 修改 imageConfig 节点以考虑服务器上已有的图像。 |
| [ValidateWavesDefinition](sm-delivery-validatewavesdefinition.md) | 检查批次定义中使用的信息的一致性。 |

## 常规方法

| 方法 | 描述 |
| --- | --- |
| [创建](f-create.md) | 创建与给定架构对应的新实体。 |
| [加载](f-load.md) | 加载并返回与给定架构和键对应的实体。 |
| [保存](m-entity-save.md) | 在数据库中保存实体。 |
