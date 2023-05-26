---
title: Campaign中的投放失败
description: 了解使用Adobe Campaign发送消息时可能发生的故障
feature: Profiles, Monitoring
role: User
level: Beginner, Intermediate
exl-id: 9c83ebeb-e923-4d09-9d95-0e86e0b80dcc
source-git-commit: 46be0379610a6a4a3491d49ce096c64270ed8016
workflow-type: tm+mt
source-wordcount: '3005'
ht-degree: 12%

---

# 了解投放失败 {#delivery-failures}

退回是ISP提供返回故障通知的投放尝试和失败的结果。 退回处理是列表安全机制的关键部分。 在给定的电子邮件已连续多次退回后，此过程会将其标记以进行抑制。

此过程可防止系统继续发送无效的电子邮件地址。 退回是ISP用于确定IP信誉的关键数据之一。 关注此指标很重要。 “已投放”与“已退回”可能是衡量营销消息投放的最常见方式：投放百分比越高越好。

如果消息无法发送到配置文件，则远程服务器会自动向Adobe Campaign发送错误消息。 此错误可用于确定是否应隔离电子邮件地址、电话号码或设备。 参见 [退回邮件管理](#bounce-mail-qualification).

发送消息后，您可以在投放日志中查看每个用户档案的投放状态以及相关失败的类型和原因。

隔离电子邮件地址后，或用户档案阻止列表时，收件人将在投放准备步骤中排除。 排除的消息会列在投放仪表板中。

## 消息投放失败的原因 {#delivery-failure-reasons}

当消息失败时，有两种类型的错误。 每个投放失败类型都确定地址是否发送至 [隔离](quarantines.md#quarantine-reason) 还是不行。

* **硬退回**
硬退回是在ISP将对用户地址的邮寄尝试确定为不可投放后生成的永久失败。 在Adobe Campaign中，分类为无法投放的硬退回会添加到隔离列表，这意味着不会重新尝试此类退回。 在某些情况下，如果故障原因未知，则会忽略硬退回。

   以下是硬退回的一些常见示例：地址不存在、帐户已禁用、语法错误、域错误

* **软退回**
软退回是ISP在难以投放邮件时生成的临时故障。 软故障将 [重试](#retries) 多次（根据使用自定义或现成投放设置而异），以尝试成功投放。 在尝试最大重试次数之前（重试次数同样因设置而异），不会将持续软退回的地址添加到隔离。

   软退回的一些常见原因包括：邮箱已满、接收电子邮件服务器关闭、发件人信誉问题

此  **已忽略** 错误类型已知为临时错误，如“外出”，或技术错误，例如，如果发件人类型为“邮递员”。

反馈循环的运行方式与退回电子邮件类似：当用户将电子邮件标记为垃圾邮件时，您可以在Adobe Campaign中配置电子邮件规则以阻止向该用户的所有投放。 即使这些用户未单击退订链接，也会对其地址进行列入阻止列表。 地址将添加到(**NmsAddress**)隔离表而非(**NmsRecipient**)收件人表，使用 **[!UICONTROL Denylisted]** 状态。 要了解有关反馈循环机制的更多信息，请参阅 [Adobe可投放性最佳实践指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#feedback-loops).

## 同步和异步错误 {#synchronous-and-asynchronous-errors}

消息投放可能会立即失败，在这种情况下，我们将其定性为同步错误。 如果消息发送失败或稍后发送，则在发送后，错误是异步的。

这些类型的错误按如下方式管理：

* **同步错误**：Adobe Campaign投放服务器联系的远程服务器立即返回错误消息。 不允许将投放发送到用户档案的服务器。 邮件传输代理(MTA)可确定退回类型并鉴别错误，然后将该信息发送回Campaign，以确定是否应隔离相关电子邮件地址。 请参阅[退回邮件鉴别](#bounce-mail-qualification)。

* **异步错误**：接收服务器稍后会重新发送退回邮件或SR。 使用与该错误相关的标签限定此错误。 最晚的异步错误，可能发生在发送投放的一周之后。

>[!NOTE]
>
>作为托管Cloud Services用户，Adobe会执行退回邮箱的配置。

## 退回邮件鉴别 {#bounce-mail-qualification}

<!--NO LONGER WITH MOMENTUM - Rules used by Campaign to qualify delivery failures are listed in the **[!UICONTROL Administration > Campaign Management > Non deliverables Management > Delivery log qualification]** node. It is non-exhaustive, and is regularly updated by Adobe Campaign and can also be managed by the user.

![](assets/delivery-log-qualification.png)-->

在Adobe Campaign中处理退回邮件鉴别的方式取决于错误类型：

* **同步错误**：MTA确定退回类型和鉴别，并将该信息发送回Campaign。 中的跳出资格 **[!UICONTROL Delivery log qualification]** 表不用于 **同步** 投放失败错误消息。

* **异步错误**：Campaign用于鉴别异步投放失败的规则列在 **[!UICONTROL Administration > Campaign Management > Non deliverables Management > Delivery log qualification]** 节点。 异步退回由inMail流程通过 **[!UICONTROL Inbound email]** 规则。 有关更多信息，请参阅 [Adobe Campaign Classic v7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html#bounce-mail-qualification){target="_blank"}.

<!--NO LONGER WITH MOMENTUM - The message returned by the remote server on the first occurrence of this error type is displayed in the **[!UICONTROL First text]** column of the **[!UICONTROL Audit]** tab.

![](assets/delivery-log-first-txt.png)

Adobe Campaign filters this message to delete the variable content (such as IDs, dates, email addresses, phone numbers, etc.) and displays the filtered result in the **[!UICONTROL Text]** column. The variables are replaced with **`#xxx#`**, except addresses that are replaced with **`*`**.

This process allows to bring together all failures of the same type and avoid multiple entries for similar errors in the Delivery log qualification table.
  
>[!NOTE]
>
>The **[!UICONTROL Number of occurrences]** field displays the number of occurrences of the message in the list. It is limited to 100 000 occurrences. You can edit the field, if you want, for example, to reset it.

Bounce mails can have the following qualification status:

* **[!UICONTROL To qualify]** : the bounce mail could not be qualified. Qualification must be assigned to the Deliverability team to guarantee efficient platform deliverability. As long as it is not qualified, the bounce mail is not used to enrich the list of email management rules.
* **[!UICONTROL Keep]** : the bounce mail was qualified and will be used by the **Refresh for deliverability** workflow to be compared to existing email management rules and enrich the list.
* **[!UICONTROL Ignore]** : the bounce mail is ignored, meaning that this bounce will never cause the recipient's address to be quarantined. It will not be used by the **Refresh for deliverability** workflow and it will not be sent to client instances.

![](assets/delivery-log-status.png)

>[!NOTE]
>
>In case of an outage of an ISP, emails sent through Campaign will be wrongly marked as bounces. To correct this, you need to update bounce qualification.-->


## 重试管理 {#retries}

如果消息投放因临时错误而失败(**柔和** 或 **已忽略**)，Campaign重试发送。 可以执行这些重试，直到投放持续时间结束。

软退回重试次数以及它们之间的时间长度由MTA根据从消息的电子邮件域返回的退回响应的类型和严重性确定。

>[!NOTE]
>
>Campaign未使用投放属性中的重试设置。

## 有效期

Campaign投放中的有效期设置限制为 **3.5天或以下**. 对于投放，如果您在Campaign中定义的值超过3.5天，则不会考虑该值。

例如，如果在Campaign中将有效期设置为默认值5天，则软退回消息将进入MTA重试队列，并从该消息到达MTA时开始最多重试3.5天。 在这种情况下，将不使用Campaign中设置的值。

消息在 MTA 队列中停留 3.5 天且投放失败后，该消息将超时，在投放日志中的状态将从 **[!UICONTROL Sent]** 更新为 **[!UICONTROL Failed]**。

有关有效期的更多信息，请参见 [Adobe Campaign Classic v7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#defining-validity-period){target="_blank"}.


## 电子邮件错误类型 {#email-error-types}

对于电子邮件渠道，下面列出了投放失败的可能原因。

<table> 
 <tbody> 
  <tr> 
   <td> 错误标签 </td> 
   <td> 错误类型 </td> 
   <td> 技术价值 </td> 
   <td> 说明 </td> 
  </tr> 
  <tr> 
   <td> 帐户被禁用 </td> 
   <td> 软/硬 </td> 
   <td> 4 </td> 
   <td> 链接到地址的帐户不再处于活动状态。 当互联网访问提供商(IAP)检测到长时间不活动时，它可以关闭用户的帐户。 随后，将无法投放到用户的地址。 如果帐户因6个月不活动而被暂时禁用，并且仍可激活，则将分配状态有错误，并再次尝试该帐户，直到错误计数达到5。 如果错误信号表明帐户已永久停用，则会直接将其设置为隔离。<br /> </td> 
  </tr> 
  <tr> 
   <td> 隔离地址 </td> 
   <td> 硬 </td> 
   <td> 9 </td> 
   <td> 地址被隔离。<br /> </td> 
  </tr> 
  <tr> 
   <td> 未指定地址 </td> 
   <td> 硬 </td> 
   <td> 7 </td> 
   <td> 没有给收件人地址。<br /> </td> 
  </tr> 
  <tr> 
   <td> 低质量地址 </td> 
   <td> 已忽略 </td> 
   <td> 14 </td> 
   <td> 此地址的质量等级太低。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已列入阻止列表的地址 </td> 
   <td> 硬 </td> 
   <td> 8 </td> 
   <td> 阻止列表地址在发送时添加到。 此状态用于将外部列表和外部系统的数据导入Adobe Campaign隔离列表。<br /> </td> 
  </tr> 
  <tr> 
   <td> 对照地址 </td> 
   <td> 已忽略 </td> 
   <td> 127 </td> 
   <td> 收件人的地址是控制组的一部分。<br /> </td> 
  </tr> 
  <tr> 
   <td> 双精度型 </td> 
   <td> 已忽略 </td> 
   <td> 10 </td> 
   <td> 收件人的地址已在此投放中。<br /> </td> 
  </tr> 
  <tr> 
   <td> 错误已忽略 </td> 
   <td> 已忽略 </td> 
   <td> 25 </td> 
   <td> 地址在允许列表上。 因此，该错误将被忽略，并且将会发送电子邮件。<br /> </td> 
  </tr> 
  <tr> 
   <td> 仲裁后排除 </td> 
   <td> 已忽略 </td> 
   <td> 12 </td> 
   <td> 收件人已由“仲裁”类型营销活动类型规则排除。<br /> </td> 
  </tr> 
  <tr> 
   <td> 由 SQL 规则排除 </td> 
   <td> 已忽略 </td> 
   <td> 11 </td> 
   <td> 收件人已被“SQL”类型营销活动类型规则排除。<br /> </td> 
  </tr> 
  <tr> 
   <td> 无效域 </td> 
   <td> 柔和 </td> 
   <td> 2 </td> 
   <td> 电子邮件地址的域不正确或不再存在。 此用户档案将被重新定向，直到错误计数达到 5 为止。此后，该记录将设置为隔离状态，并且以后不会再进行重试。<br /> </td> 
  </tr> 
  <tr> 
   <td> 邮箱已满 </td> 
   <td> 柔和 </td> 
   <td> 5 </td> 
   <td> 此用户的邮箱已满，无法接受更多邮件。 此用户档案将被重新定向，直到错误计数达到 5 为止。此后，该记录将设置为隔离状态，并且以后不会再进行重试。<br /> 此类错误由清理进程管理，地址在30天后设置为有效状态。<br /> 警告：对于要从隔离地址列表中自动删除的地址，必须启动数据库清理技术工作流。<br /> </td> 
  </tr> 
  <tr> 
   <td> 未连接 </td> 
   <td> 已忽略 </td> 
   <td> 6 </td> 
   <td> 发送消息时，收件人的手机已关闭或未连接到网络。<br /> </td> 
  </tr> 
  <tr> 
   <td> 未定义 </td> 
   <td> 未定义 </td> 
   <td> 0 </td> 
   <td> 地址正在进行鉴别，因为错误尚未递增。 当服务器发送新的错误消息时，会发生此类错误： 这可能是一个孤立的错误，但如果再次发生，则错误计数会增加，从而提醒技术团队。然后，他们可以通过 <span class="uicontrol">管理</span> / <span class="uicontrol">Campaign Management</span> / <span class="uicontrol">不可交付结果管理</span> 树结构中的节点。<br /> </td> 
  </tr> 
  <tr> 
   <td> 不符合优惠资格 </td> 
   <td> 已忽略 </td> 
   <td> 16 </td> 
   <td> 收件人不符合投放中的优惠条件。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已拒绝 </td> 
   <td> 软/硬 </td> 
   <td> 20 </td> 
   <td> 由于安全反馈为垃圾邮件报告，该地址已被隔离。 根据错误，将再次尝试该地址，直到错误计数达到5，否则将直接将其发送到隔离。<br /> </td> 
  </tr> 
  <tr> 
   <td> 目标大小受限 </td> 
   <td> 已忽略 </td> 
   <td> 17 </td> 
   <td> 已达到收件人的最大投放大小。<br /> </td> 
  </tr> 
  <tr> 
   <td> 不合格地址 </td> 
   <td> 已忽略 </td> 
   <td> 15 </td> 
   <td> 邮寄地址不合格.<br /> </td> 
  </tr> 
  <tr> 
   <td> 不可到达 </td> 
   <td> 软/硬 </td> 
   <td> 3 </td> 
   <td> 消息投放链中发生错误。 可能是SMTP中继上的事件、暂时无法访问的域等。 根据错误，将再次尝试该地址，直到错误计数达到5，否则将直接将其发送到隔离。<br /> </td> 
  </tr> 
  <tr> 
   <td> 用户未知 </td> 
   <td> 硬 </td> 
   <td> 1 </td> 
   <td> 地址不存在。 不再尝试对该用户档案进行投放。<br /> </td> 
  </tr> 
 </tbody> 
</table>



## 推送通知错误类型 {#push-error-types}

对于移动设备应用程序渠道，下面列出了投放失败的可能原因。

### iOS隔离 {#ios-quarantine}

HTTP/V2协议允许直接反馈每个推送投放的状态。 如果使用HTTP/V2协议连接器，则反馈服务不再由 **[!UICONTROL mobileAppOptOutMgt]** 工作流。 卸载或重新安装移动应用程序时，令牌被视为已注销。

同时，如果APN为消息返回“未注册”状态，则目标令牌将立即被隔离。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>方案</strong><br /> </td> 
   <td> <strong>状态</strong><br /> </td> 
   <td> <strong>错误消息</strong><br /> </td> 
   <td> <strong>失败类型</strong><br /> </td> 
   <td> <strong>失败原因</strong><br /> </td> 
   <td> <strong>重试</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> 目标设备已通电<br /> </td> 
   <td> 确定<br /> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 目标设备已关闭<br /> </td> 
   <td> 确定<br /> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 用户禁用应用程序的通知<br /> </td> 
   <td> 确定<br /> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 报文创建/分析阶段 — 有效负载太大<br /> </td> 
   <td> 失败<br /> </td> 
   <td> 有效负载过长<br /> </td> 
   <td> 柔和<br /> </td> 
   <td> 已拒绝<br /> </td> 
   <td> 否<br /> </td> 
  </tr> 
  <tr> 
   <td> 报文创建/分析阶段 — 意外的内容格式问题<br /> </td> 
   <td> 失败<br /> </td> 
   <td> 根据错误显示的各种错误消息<br /> </td> 
   <td> 柔和<br /> </td> 
   <td> 未定义<br /> </td> 
   <td> 否<br /> </td> 
  </tr> 
  <tr> 
   <td> 证书问题（密码、损坏等） 和测试与APNs问题的连接<br /> </td> 
   <td> 失败<br /> </td> 
   <td> 根据错误显示的各种错误消息<br /> </td> 
   <td> 柔和<br /> </td> 
   <td> 已拒绝<br /> </td> 
   <td> 否<br /> </td> 
  </tr> 
  <tr> 
   <td> 发送期间网络连接丢失<br /> </td> 
   <td> 失败<br /> </td> 
   <td> 连接错误<br /> </td> 
   <td> 未定义<br /> </td> 
   <td> 不可到达<br /> </td> 
   <td> 是<br /> </td> 
  </tr> 
  <tr> 
   <td> APNs消息拒绝：取消注册<br /> 用户已删除应用程序或令牌已过期<br /> </td> 
   <td> 失败<br /> </td> 
   <td> 未注册<br /> </td> 
   <td> 硬<br /> </td> 
   <td> 用户未知<br /> </td> 
   <td> 否<br /> </td> 
  </tr> 
  <tr> 
   <td> APNs消息拒绝：所有其他错误<br /> </td> 
   <td> 失败<br /> </td> 
   <td> 错误消息中将显示错误拒绝原因<br /> </td> 
   <td> 柔和<br /> </td> 
   <td> 已拒绝<br /> </td> 
   <td> 否<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Android隔离 {#android-quarantine}

**适用于Android V1**

对于每个通知，Adobe Campaign都会直接从FCM服务器接收同步错误。 Adobe Campaign会动态处理它们，并根据错误的严重性生成硬错误或软错误，并且可以执行重试：

* 已超出有效负载长度，连接问题，服务可用性问题：已执行重试，软错误，失败原因为 **[!UICONTROL Refused]**.
* 超出设备配额：无重试、软错误、失败原因是 **[!UICONTROL Refused]**.
* 无效或未注册的令牌，意外错误，发件人帐户问题：无重试，硬错误，失败原因是 **[!UICONTROL Refused]**.

此 **[!UICONTROL mobileAppOptOutMgt]** 工作流每6小时运行一次，以更新 **AppSubscriptionRcp** 表格。 对于声明为未注册或不再有效的令牌，字段 **已禁用** 设置为 **True** 并且将来投放时将自动排除链接到该设备令牌的订阅。

在投放分析期间，从目标中排除的所有设备会自动添加到 **excludeLogAppSubRcp** 表格。

>[!NOTE]
>
>对于使用百度连接器的客户，以下是不同类型的错误：
>
>* 投放开始时的连接问题：故障类型 **[!UICONTROL Undefined]**，失败原因 **[!UICONTROL Unreachable]**，将执行重试。
>* 投放期间连接丢失：软错误、失败原因 **[!UICONTROL Refused]**，将执行重试。
>* 百度在发送过程中返回的同步错误：硬错误、失败原因 **[!UICONTROL Refused]**，则不执行重试。
>
>Adobe Campaign每10分钟联系百度服务器一次，以检索发送消息的状态，并更新broadlog。 如果消息被声明为已发送，则broadlogs中消息的状态将设置为 **[!UICONTROL Received]**. 如果百度宣布错误，则状态设置为 **[!UICONTROL Failed]**.

**适用于Android V2**

Android V2隔离机制使用与Android V1相同的过程，同样适用于订阅和排除项更新。 欲知详情，请参阅 [Android V1](#android-quarantine) 部分。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>方案</strong><br /> </td> 
   <td> <strong>状态</strong><br /> </td> 
   <td> <strong>错误消息</strong><br /> </td> 
   <td> <strong>失败类型</strong><br /> </td> 
   <td> <strong>失败原因</strong><br /> </td> 
   <td> <strong>重试</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> 报文创建/分析阶段：自定义字段中使用的关键字不合法<br /> </td> 
   <td> 失败<br /> </td> 
   <td> 不能使用以下关键字： {1}<br /> </td> 
   <td> 柔和<br /> </td> 
   <td> </td> 
   <td> 否<br /> </td> 
  </tr> 
  <tr> 
   <td> 消息创建/分析阶段：有效负载太大<br /> </td> 
   <td> 失败<br /> </td> 
   <td> 通知过重： {1}位，而只有{2}位被授权<br /> </td> 
   <td> 柔和<br /> </td> 
   <td> 已拒绝<br /> </td> 
   <td> 否<br /> </td> 
  </tr> 
  <tr> 
   <td> 发送期间网络连接丢失<br /> </td> 
   <td> 失败<br /> </td> 
   <td> 地址上的Firebase Cloud Messaging服务没有响应： {1}<br /> </td> 
   <td> 柔和<br /> </td> 
   <td> 不可到达<br /> </td> 
   <td> 是<br /> </td> 
  </tr> 
  <tr> 
   <td> FCM消息拒绝： FCM服务器暂时不可用（例如，超时）。 <br /> </td> 
   <td> 失败<br /> </td> 
   <td> Firebase云消息服务暂时不可用<br /> </td> 
   <td> 柔和<br /> </td> 
   <td> 不可到达<br /> </td> 
   <td> 是<br /> </td> 
  </tr> 
  <tr> 
   <td> FCM消息拒绝：验证发件人帐户时出错<br /> </td> 
   <td> 失败<br /> </td> 
   <td> 无法识别开发人员帐户，请检查您的ID和密码<br /> </td> 
   <td> 柔和<br /> </td> 
   <td> 已拒绝<br /> </td> 
   <td> 否<br /> </td> 
  </tr> 
  <tr> 
   <td> FCM消息拒绝：超出设备配额<br /> </td> 
   <td> 失败<br /> </td> 
   <td> </td> 
   <td> 柔和<br /> </td> 
   <td> 已拒绝<br /> </td> 
   <td> 是<br /> </td> 
  </tr> 
  <tr> 
   <td> FCM消息拒绝：注册无效/未注册<br /> </td> 
   <td> 失败<br /> </td> 
   <td> </td> 
   <td> 硬<br /> </td> 
   <td> 用户未知<br /> </td> 
   <td> 否<br /> </td> 
  </tr> 
  <tr> 
   <td> FCM消息拒绝：所有其他错误<br /> </td> 
   <td> 失败<br /> </td> 
   <td> Firebase Cloud Messaging Server返回了意外错误代码： {1} </td> 
   <td> </td> 
   <td> 已拒绝<br /> </td> 
   <td> 否<br /> </td> 
  </tr> 
    <tr> 
   <td> FCM消息拒绝：参数无效<br /> </td> 
   <td> 失败<br /> </td> 
   <td> INVALID_ARGUMENT </td> 
   <td> 已忽略</td> 
   <td> 未定义<br /> </td> 
   <td> 否<br /> </td> 
  </tr>
    <tr> 
   <td> FCM消息拒绝：第三方身份验证错误<br /> </td> 
   <td> 失败<br /> </td> 
   <td> THIRD_PARTY_AUTH_ERROR </td> 
   <td> 已忽略</td>
   <td> 已拒绝<br /> </td> 
   <td> 是<br /> </td> 
  </tr>
    <tr> 
   <td> FCM消息拒绝：发件人ID不匹配<br /> </td> 
   <td> 失败<br /> </td> 
   <td> SENDER_ID_MISMATCH </td> 
   <td> 柔和</td>
   <td> 用户未知<br /> </td> 
   <td> 否<br /> </td> 
  </tr>
    <tr> 
   <td> FCM消息拒绝：未注册<br /> </td> 
   <td> 失败<br /> </td>
   <td> 未注册 </td> 
   <td> 硬</td> 
   <td> 用户未知<br /> </td> 
   <td> 否<br /> </td> 
  </tr>
    <tr> 
   <td> FCM消息拒绝：内部<br /> </td> 
   <td> 失败<br /> </td> 
   <td> 内部 </td> 
   <td> 已忽略</td> 
   <td> 已拒绝<br /> </td> 
   <td> 是<br /> </td> 
  </tr>
    <tr> 
   <td> FCM消息拒绝：不可用<br /> </td> 
   <td> 失败<br /> </td> 
   <td> 不可用</td> 
   <td> 已忽略</td> 
   <td> 已拒绝<br /> </td> 
   <td> 是<br /> </td> 
  </tr>
    <tr> 
   <td> FCM消息拒绝：意外错误代码<br /> </td> 
   <td> 失败<br /> </td> 
   <td> 意外错误代码</td> 
   <td> 已忽略</td> 
   <td> 已拒绝<br /> </td> 
   <td> 否<br /> </td> 
  </tr>
  <tr> 
   <td> 身份验证：连接问题<br /> </td> 
   <td> 失败<br /> </td> 
   <td> 无法连接到身份验证服务器 </td> 
   <td> 已忽略</td>
   <td> 已拒绝<br /> </td> 
   <td> 是<br /> </td> 
  </tr>
    <tr> 
   <td> 身份验证：请求中有未经授权的客户端或范围。<br /> </td> 
   <td> 失败<br /> </td> 
   <td> unauthorized_client </td> 
   <td> 已忽略</td>
   <td> 已拒绝<br /> </td> 
   <td> 否<br /> </td> 
  </tr>
    <tr> 
   <td> 身份验证：客户端无权使用此方法检索访问令牌，或者客户端无权使用请求的任何作用域。<br /> </td> 
   <td> 失败<br /> </td> 
   <td> unauthorized_client </td> 
   <td> 已忽略</td>
   <td> 已拒绝<br /> </td> 
   <td> 否<br /> </td> 
  </tr>
    <tr> 
   <td> 身份验证：访问被拒绝<br /> </td> 
   <td> 失败<br /> </td>
   <td> access_denied</td> 
   <td> 已忽略</td>
   <td> 已拒绝<br /> </td> 
   <td> 否<br /> </td> 
  </tr>
    <tr> 
   <td> 身份验证：无效的电子邮件<br /> </td> 
   <td> 失败<br /> </td> 
   <td> invalid_grant </td> 
   <td> 已忽略</td> 
   <td> 已拒绝<br /> </td> 
   <td> 否<br /> </td> 
  </tr>
    <tr> 
   <td> 身份验证：无效的JWT<br /> </td> 
   <td> 失败<br /> </td> 
   <td> invalid_grant </td> 
   <td> 已忽略</td> 
   <td> 已拒绝<br /> </td> 
   <td> 否<br /> </td> 
  </tr>
    <tr> 
   <td> 身份验证：JWT签名无效<br /> </td> 
   <td> 失败<br /> </td> 
   <td> invalid_grant </td> 
   <td> 已忽略</td> 
   <td> 已拒绝<br /> </td> 
   <td> 否<br /> </td> 
  </tr>
    <tr> 
   <td> 身份验证：提供的OAuth范围或ID令牌受众无效<br /> </td> 
   <td> 失败<br /> </td> 
   <td> unauthorized_client</td> 
   <td> 已忽略</td> 
   <td> 已拒绝<br /> </td> 
   <td> 否<br /> </td> 
  </tr>
    <tr> 
   <td> 身份验证：已禁用OAuth客户端<br /> </td> 
   <td> 失败<br /> </td> 
   <td> disabled_client</td> 
   <td> 已忽略</td> 
   <td> 已拒绝<br /> </td> 
   <td> 否<br /> </td> 
  </tr>
 </tbody> 
</table>

## 短信隔离 {#sms-quarantines}

**对于标准连接器**

短信渠道的特定性如下所列。

>[!NOTE]
>
>此 **[!UICONTROL Delivery log qualification]** 表不适用于 **扩展的通用SMPP** 连接器。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>方案</strong><br /> </td> 
   <td> <strong>状态</strong><br /> </td> 
   <td> <strong>错误消息</strong><br /> </td> 
   <td> <strong>失败类型</strong><br /> </td> 
   <td> <strong>失败原因</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> 已发送给提供商<br /> </td> 
   <td> 已发送<br /> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 已在移动设备上接收<br /> </td> 
   <td> 已接收<br /> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 提供程序返回的错误<br /> </td> 
   <td> 失败<br /> </td> 
   <td> 接收数据时出错（SR或MO）<br /> </td> 
   <td> 柔和<br /> </td> 
   <td> 不可到达<br /> </td> 
  </tr> 
  <tr> 
   <td> MT确认无效<br /> </td> 
   <td> 失败<br /> </td> 
   <td> 处理发送查询的确认帧时出错“{1}”<br /> </td> 
   <td> 柔和<br /> </td> 
   <td> 不可到达<br /> </td> 
  </tr> 
  <tr> 
   <td> 发送报文时出错<br /> </td> 
   <td> 失败<br /> </td> 
   <td> 发送消息时出错<br /> </td> 
   <td> 柔和<br /> </td> 
   <td> 不可到达<br /> </td> 
  </tr> 
 </tbody> 
</table>

**对于扩展的通用SMPP连接器**

使用SMPP协议发送短信消息时，错误管理的处理方式不同。

SMPP连接器从使用正则表达式（正则表达式）返回的SR（状态报告）消息中检索数据，以筛选其内容。 然后，将此数据与 **[!UICONTROL Delivery log qualification]** 表格(可通过以下网站获取： **[!UICONTROL Administration]** > **[!UICONTROL Campaign Management]** > **[!UICONTROL Non deliverables Management]** 菜单)。

在限定新类型的错误之前，失败原因始终设置为 **已拒绝** 默认情况下。

>[!NOTE]
>
>失败类型和失败原因与电子邮件相同。
>
>请向提供商索取状态和错误代码列表，以便在投放日志鉴别表中设置正确的失败类型和失败原因。

生成的消息示例：

```
SR Generic DELIVRD 000|#MESSAGE#
```

* 所有错误消息都以开头 **SR** 以区分短信错误代码和电子邮件错误代码。
* 第二部分(**通用** 在此示例中，错误消息将引用SMSC实施的名称，如中定义的 **[!UICONTROL SMSC implementation name]** 短信外部帐户的字段。

   由于相同的错误代码对每个提供程序可能有不同的含义，因此此字段允许您知道是哪个提供程序生成了错误代码。 然后，您可以在相关提供商的文档中查找错误。

* 第三部分(**DELIVRD** 在此示例中)的错误消息对应于使用在SMS外部帐户中定义的状态提取正则表达式从SR检索到的状态代码。

   此正则表达式在 **[!UICONTROL SMSC specificities]** 外部帐户的选项卡。
默认情况下，正则表达式会提取 **stat：** 由定义的字段 **附录B** 部分 **SMPP 3.4规范**.

* 第四部分(**000** 在此示例中)的错误消息对应于使用在SMS外部帐户中定义的错误代码提取正则表达式从SR提取的错误代码。

   此正则表达式在 **[!UICONTROL SMSC specificities]** 外部帐户的选项卡。

   默认情况下，正则表达式会提取 **错误：** 由定义的字段 **附录B** 部分 **SMPP 3.4规范**.

* 管道符号(|)后面的所有内容仅显示在 **[!UICONTROL First text]** 列 **[!UICONTROL Delivery log qualification]** 表格。 此内容始终替换为 **#MESSAGE#** 在消息规范化之后。 此过程可避免因类似错误而出现多个条目，并且与电子邮件的条目相同。

扩展通用SMPP连接器应用启发式来查找合理的默认值：如果状态以开头 **DELIV**，它被视为成功，因为它与常见状态匹配 **DELIVRD** 或 **已投放** 供大多数提供商使用。 任何其他状态都会导致硬故障。
