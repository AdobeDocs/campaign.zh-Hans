---
title: 投放属性中的SMPP连接器
description: 关于投放中SMPP连接器的设置
feature: SMS
role: User
level: Beginner, Intermediate
exl-id: 704e151a-b863-46d0-b8a1-fca86abd88b9
source-git-commit: 6f29a7f157c167cae6d304f5d972e2e958a56ec8
workflow-type: tm+mt
source-wordcount: '1340'
ht-degree: 5%

---

# SMPP连接器描述 {#smpp-connector-desc}

>[!IMPORTANT]
>
>本文档适用于Adobe Campaign v8.7.2及更高版本。 要从旧版短信连接器切换到新版短信连接器，请参阅此[技术说明](https://experienceleague.adobe.com/docs/campaign/technotes-ac/tn-new/sms-migration){target="_blank"}。
>
>对于旧版本，请阅读[Campaign Classic v7文档](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up/sms-set-up){target="_blank"}。

## SMS连接器数据流 {#sms-data-flow}

本节介绍SMS流程如何处理数据。

这是一个概要框图，其中汇总了短信流程与其环境的交互方式。

![](assets/smsv2_highlevel.png){zoomable="yes"}

SMS流程托管2个重要组件：SMPP连接器本身，它处理与SMPP提供商的通信，以及SR协调的后台任务。

### SMPP帐户的数据流 {#sms-data-flow-smpp-accounts}

短信进程会轮询nms：extAccount并在其SMPP连接器中生成新连接，从而传递每个帐户的设置。 可以在&#x200B;*configRefreshMillis*&#x200B;设置的serverConf中调整轮询频率。

对于每个活动的SMPP帐户， SMPP连接器会尝试始终保持连接活动。 如果连接丢失，它将重新连接。

### 发送消息时的数据流 {#sms-data-flow-sending-msg}

* 短信进程通过扫描nms：delivery选择活动投放。 投放在以下情况下处于活动状态：
   * 其状态表示消息可以发送
   * 其有效期未届满
   * 它实际上是投放（例如，它不是模板，不会删除）
   * SMPP连接器可以为链接到投放的外部帐户打开至少一个连接
* 对于每个投放，短信流程都会加载投放部分。 如果投放部分已部分发送，则短信流程会通过检查广泛日志来检查已发送哪些消息。
* 短信流程使用投放部分的个性化数据扩展模板。
* smpp连接器会生成与内容和其他设置匹配的MT (SUBMIT_SM PDU)。
* SMPP连接器通过发射器（或收发器）连接发送MT。
* 提供商返回此MT的ID。 它会被插入到nms：providerMsgId中。
* 短信流程会将广泛日志更新为已发送状态。
* 在出现最终错误的情况下，短信流程会相应地更新广义日志，并且可能会在nms：broadLogMsg中创建一种新型错误。

### 接收SR时的数据流 {#sms-data-flow-sr}

* SMPP连接器接收并解码SR (DELIVER_SM PDU)。 它使用外部帐户中定义的正则表达式来获取消息ID和状态。
* 消息ID和状态已插入nms：providerMsgStatus
* 插入后，SMPP连接器会回复一个DELIVER_SM_RESP PDU。
* 如果在此过程中出现错误，SMPP连接器会发送一个否定的DELIVER_SM_RESP PDU并记录一条消息。

### 接收MO时的数据流 {#sms-data-flow-mo}

* SMPP连接器接收并解码MO (DELIVER_SM PDU)。
* 将从消息中提取关键字。 如果它与任何声明的关键字匹配，则执行相应的操作。 它可以写入nms：address以更新隔离。
* 如果声明了自定义TLV，则会根据其各自的设置对它们进行解码。
* 完全解码和处理的MO将插入nms：inSms表中。
* SMPP连接器使用DELIVER_SM_RESP PDU进行回复。 如果检测到任何错误，则会向提供程序返回错误代码。

### 协调MT和SR时的数据流 {#sms-reconciling-mt-sr}

* SR协调组件定期读取nms：providerMsgId和nms：providerMsgStatus。 来自两个表的数据被连接。
* 对于两个表中都有条目的所有消息，将更新匹配的nms：broadLog条目。
* 如果检测到新类型的错误，则可以在进程中更新nms：broadLogMsg表，或者更新未手动限定的错误的计数器。

## 匹配MT、SR和broadlog条目 {#sms-matching-entries}

下图描述了整个过程：

![](assets/message_processing.png){zoomable="yes"}

**阶段1**

* 扫描消息并进行格式化，然后将其传输到SMPP连接器。
* SMPP连接器将其格式化为SUBMIT_SM MT PDU。
* MT将发送到SMPP提供商。
* 提供程序使用SUBMIT_SM_RESP进行回复。 SUBMIT_SM和SUBMIT_SM_RESP按其序列号。
* SUBMIT_SM_RESP提供来自提供程序的ID。 此id与广义日志id一起插入nms：providerMsgId表中。

**阶段2**

* 提供程序发送DELIVER_SM SR PDU。
* 将解析SR以提取提供程序ID、状态和错误代码。 此步骤使用提取正则表达式。
* 提供程序ID及其相应状态将插入nms：providerMsgStatus。
* 将所有数据安全地插入数据库后，SMPP连接器会使用DELIVER_SM_RESP进行回复。 DELIVER_SM和DELIVER_SM_RESP通过它们的序列号匹配。

**阶段3**

* SMS进程的SR协调组件会定期扫描nms：providerMsgId和nms：providerMsgStatus表。
* 如果任意行在两个表中具有匹配的提供程序ID，则这2个条目将连接在一起。 这允许将广泛日志ID（存储在providerMsgId中）与状态（存储在providerMsgStatus中）匹配
* 广泛日志将更新为相应的状态。

## 亲和度和专用流程连接器 {#sms-affinities}

专用进程连接器会忽略相关性，它仅在短信进程中运行。

## serverConf选项 {#sms-serverconf-options}

某些设置可在serverConf.xml中调整。 与此文件中的任何其他设置一样，应在config-instance.xml文件中指定它。 所有设置都位于&lt; mta2 >元素中。

此表汇总了所有设置。 最小/最大合理值大致说明了在大多数情况下应考虑的范围。 调试值是在尝试查找与性能无关的问题时要选择的值。

| 设置 | 说明 | 默认 | 最小合理值 | 最大合理值 | 调试值 |
|:-:|:-:|:-:|:-:|:-:|:-:|
| batchUpdateSize | 更新微批次的大小 | 5000 | 100：极低延迟 | maxWaitingMessages/updateThreads：超过此值无用，因为maxWaitingMessages仍将限制缓冲 | 1：禁用微批次处理，逐个更新消息 |
| configRefreshMillis | 配置重新加载的周期（以毫秒为单位） | 10000 | pollPeriodMillis：低延迟 | 600000：重新加载速度不要太快，以免节省资源 | 500：低延迟允许更快地尝试新设置 |
| deliveryPartRetryCount | deliveryPart重试或延迟的最大次数。 注意：重新启动发送进程即计为重试，崩溃也计为重试。 | 20 | 1：禁用重试 | 50：使消息更持久以处理不稳定的提供程序 | 1：禁用重试。 1000：避免刷新失败的消息。 |
| deliveryPartRetryDelaySeconds | 重试 deliveryPart 之前的最小延迟。这是跨进程和跨容器的。延迟以秒为单位。 | 60 | 0：立即重试 | 3600：重试非常慢（每次重试间隔1小时） | 1：使重试在繁忙的日志中易于关注。 |
| logOut | 在主日志输出上发送监视和分析数据。 | 真 | false：可能会使吞吐量稍有增加。 气馁。 | true：启用日志记录。 | 真 |
| maxWaitingMessages | 随时处理的最大消息数 | 50000 | 256：足以容纳单个deliveryPart | 200000：受SQL查询长度限制(64k) | 1：逐个处理消息 |
| pollPeriodMillis | 用于检查新消息的数据库轮询频率（以毫秒为单位） | 2000 | 500：延迟非常低 | 10000：较大的批次 | 500：低延迟使调试更容易。 |
| prepareThreads | 消息准备的线程数 | 3 | 1：单线程 | CPU数。 RAM使用时要小心。 如果增加到6以上，可能需要增加maxSMSMemoryMb、maxProcessMemoryAlertMb和maxProcessMemoryWarningMb | 1：单线程生成更干净的日志。 |
| profDeliveryStat | 记录有关SMS进程内部的各种汇总统计信息 | 真 | false：可能会使吞吐量稍有增加。 气馁。 | true：低详细程度日志 | 真 |
| profLogPerMessage | 记录每个消息的每个处理步骤 | 假 | false：减少日志详细程度。 | true：详细程度日志非常高。 **仅在绝对必要时使用**。 对性能有巨大影响。 **收集到足够的数据后，请立即禁用此设置**。 | 真 |
| providerIdScanPeriod | 扫描要协调的新提供程序ID之间的时段（以秒为单位） | 10 | 1：低延迟 | 60：更大的批次，以获得更高的吞吐量 | 1：低延迟有助于调试消息处理。 |
| providerIdThreads | 提供程序 ID 协调的线程数。每个实例 1 个线程就足够了。设置为 0 可在此容器上禁用。 | 1 | 0：在此容器上禁用 | 1 | 1 |
| sendingThreads | 发送线程数 | 1 | 1：单线程 | CPU数。 线程过多通常会降低性能。 | 1：单线程生成更干净的日志。 |
| updatethreads | 用于更新数据库的线程数 | 1 | 1：单线程 | CPU数。 每个线程创建自己的数据库连接。 | 1：单线程生成更干净的日志。 |
| verifymode | 模拟发送消息。 消息实际上不会发送。 对调试很有用 | 假 | 假 | 真 | false：正常运行系统。 true：仅测试数据库访问和消息准备。 |
