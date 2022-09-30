---
title: Campaign中的投放失败
description: 了解使用Adobe Campaign发送消息时可能出现的故障
feature: Profiles, Monitoring
role: User
level: Beginner, Intermediate
exl-id: 9c83ebeb-e923-4d09-9d95-0e86e0b80dcc
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '3008'
ht-degree: 11%

---

# 了解投放失败 {#delivery-failures}

退回是ISP提供回发失败通知的投放尝试和失败的结果。 跳出处理是列表卫生的关键部分。 给定电子邮件已连续多次弹回后，此过程会标记其以抑制。

此过程可阻止系统继续发送无效的电子邮件地址。 退回量是ISP用来确定IP信誉的关键数据之一。 关注此量度很重要。 “已投放”与“已退回”可能是衡量营销消息投放情况的最常用方法：交付百分比越高，越好。

如果消息无法发送到用户档案，远程服务器会自动向Adobe Campaign发送错误消息。 确定此错误是为了确定是否应隔离电子邮件地址、电话号码或设备。 请参阅 [退回邮件管理](#bounce-mail-qualification).

发送消息后，您可以在投放日志中查看每个用户档案的投放状态以及相关失败类型和原因。

隔离电子邮件地址时，或者如果某个用户档案处于状阻止列表态，则投放准备步骤中将排除收件人。 排除的消息列在投放仪表板中。

## 消息投放失败的原因 {#delivery-failure-reasons}

消息失败时有两种类型的错误。 每个投放失败类型均确定地址是否被发送到 [隔离](quarantines.md#quarantine-reason) 或不。

* **硬退回**
硬退回是在ISP确定对订户地址的邮件尝试为无法发送后生成的永久故障。 在Adobe Campaign中，分类为不可交付的硬退回会添加到隔离列表，这意味着不会重新尝试这些退回。 在某些情况下，如果失败原因未知，则会忽略硬退回。

   以下是一些常见的硬退回示例：地址不存在、帐户已禁用、语法错误、域错误

* **软退回**
软退回是ISP在发送邮件时遇到困难时产生的临时故障。 软故障将 [重试](#retries) 多次（具有差异，具体取决于使用自定义或现成投放设置）以尝试成功投放。 在尝试重试的最大次数（这又因设置而异）之前，不会将持续软退回的地址添加到隔离。

   软退回的一些常见原因包括：邮箱已满，正在接收电子邮件服务器关闭，发件人信誉问题

的  **已忽略** 错误类型已知为临时错误（如“不在办公室”），或技术错误（例如，如果发件人类型为“邮递员”）。

反馈循环的工作方式类似于退回电子邮件：当用户将电子邮件标记为垃圾邮件时，您可以在Adobe Campaign中配置电子邮件规则，以阻止向此用户发送所有邮件。 即使用户未单击退列入阻止列表订链接，其地址也会被。 地址会添加到(**NmsAddress**)隔离表，而不是(**NmsRecipient**)收件人表 **[!UICONTROL Denylisted]** 状态。 了解有关 [Adobe投放能力最佳实践指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#feedback-loops).

## 同步和异步错误 {#synchronous-and-asynchronous-errors}

消息投放可能会立即失败，在这种情况下，我们会将其视为同步错误。 如果消息发送失败或稍后失败，则在发送后，将出现异步错误。

这些类型的错误按如下方式管理：

* **同步错误**:Adobe Campaign投放服务器联系的远程服务器会立即返回错误消息。 不允许将投放发送到用户档案的服务器。 邮件传输代理(MTA)确定退件类型并确定错误的条件，并将该信息发送回Campaign，以确定是否应隔离相关的电子邮件地址。 请参阅[退回邮件鉴别](#bounce-mail-qualification)。

* **异步错误**:接收服务器会在稍后重新发送退回邮件或重新发送SR。 此错误由与错误相关的标签限定。 最晚的异步错误，可能发生在发送投放的一周之后。

>[!NOTE]
>
>作为Managed Services用户，跳出邮箱的配置由Adobe执行。

## 退回邮件鉴别 {#bounce-mail-qualification}

<!--NO LONGER WITH MOMENTUM - Rules used by Campaign to qualify delivery failures are listed in the **[!UICONTROL Administration > Campaign Management > Non deliverables Management > Delivery log qualification]** node. It is non-exhaustive, and is regularly updated by Adobe Campaign and can also be managed by the user.

![](assets/delivery-log-qualification.png)-->

在Adobe Campaign中处理退回邮件鉴别的方式取决于错误类型：

* **同步错误**:MTA可确定退件类型和资格条件，并将该信息发回至Campaign。 中的退回资格 **[!UICONTROL Delivery log qualification]** 表未用于 **同步** 投放失败错误消息。

* **异步错误**:Campaign用于确定异步投放失败的规则列在 **[!UICONTROL Administration > Campaign Management > Non deliverables Management > Delivery log qualification]** 节点。 异步退回由inMail流程通过 **[!UICONTROL Inbound email]** 规则。 有关更多信息，请参阅 [Adobe Campaign Classic v7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html#bounce-mail-qualification){target=&quot;_blank&quot;}。

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

如果消息投放在出现临时错误后失败(**柔和** 或 **已忽略**),Campaign重试发送。 这些重试可一直执行到投放持续时间结束为止。

软退件重试次数及其间隔时间由MTA根据从消息电子邮件域返回的退回响应的类型和严重性确定。

>[!NOTE]
>
>Campaign不使用投放属性中的重试设置。

## 有效期

Campaign投放中的有效期设置限制为 **3.5天或以下**. 对于投放，如果您在Campaign中定义的值超过3.5天，则不会将其考虑在内。

例如，如果在Campaign中将有效期设置为默认值5天，则软跳出消息将进入MTA重试队列，并从该消息到达MTA后仅重试3.5天。 在这种情况下，将不使用Campaign中设置的值。

消息在 MTA 队列中停留 3.5 天且投放失败后，该消息将超时，在投放日志中的状态将从 **[!UICONTROL Sent]** 更新为 **[!UICONTROL Failed]**。

有关有效期的更多信息，请参阅 [Adobe Campaign Classic v7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#defining-validity-period){target=&quot;_blank&quot;}。


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
   <td> 链接到地址的帐户不再处于活动状态。 当互联网访问提供商(IAP)检测到长时间不活动时，它可以关闭用户的帐户。 然后，将无法投放到用户地址。 如果帐户因6个月不活动而暂时禁用，并且仍可以激活，则将分配状态“有错误”，并将重试该帐户，直到错误计数达到5为止。 如果错误表示该帐户已永久停用，则会直接将其设置为隔离。<br /> </td> 
  </tr> 
  <tr> 
   <td> 隔离中的地址 </td> 
   <td> 硬 </td> 
   <td> 9 </td> 
   <td> 地址被隔离。<br /> </td> 
  </tr> 
  <tr> 
   <td> 未指定地址 </td> 
   <td> 硬 </td> 
   <td> 7 </td> 
   <td> 收件人的地址未提供。<br /> </td> 
  </tr> 
  <tr> 
   <td> 质量差的地址 </td> 
   <td> 已忽略 </td> 
   <td> 14 </td> 
   <td> 此地址的质量评级过低。<br /> </td> 
  </tr> 
  <tr> 
   <td> 列入阻止列表地址 </td> 
   <td> 硬 </td> 
   <td> 8 </td> 
   <td> 发送时已将地阻止列表址添加到。 此状态用于将数据从外部列表和外部系统导入Adobe Campaign隔离列表。<br /> </td> 
  </tr> 
  <tr> 
   <td> 控制地址 </td> 
   <td> 已忽略 </td> 
   <td> 127 </td> 
   <td> 收件人的地址是控制组的一部分。<br /> </td> 
  </tr> 
  <tr> 
   <td> 两次 </td> 
   <td> 已忽略 </td> 
   <td> 10 </td> 
   <td> 此投放中已包含收件人的地址。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已忽略错误 </td> 
   <td> 已忽略 </td> 
   <td> 25 </td> 
   <td> 地址在允许列表上。 因此，该错误会被忽略，并将发送电子邮件。<br /> </td> 
  </tr> 
  <tr> 
   <td> 仲裁后排除 </td> 
   <td> 已忽略 </td> 
   <td> 12 </td> 
   <td> 收件人被“仲裁”类型的活动类型规则排除。<br /> </td> 
  </tr> 
  <tr> 
   <td> 由SQL规则排除 </td> 
   <td> 已忽略 </td> 
   <td> 11 </td> 
   <td> 收件人被“SQL”类型的营销活动分类规则排除。<br /> </td> 
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
   <td> 此用户的邮箱已满，无法接受更多邮件。 此用户档案将被重新定向，直到错误计数达到 5 为止。此后，该记录将设置为隔离状态，并且以后不会再进行重试。<br /> 此类错误由清理过程管理，地址在30天后将设置为有效状态。<br /> 警告：对于要自动从隔离地址列表中移除的地址，必须启动数据库清理技术工作流。<br /> </td> 
  </tr> 
  <tr> 
   <td> 未连接 </td> 
   <td> 已忽略 </td> 
   <td> 6 </td> 
   <td> 在发送消息时，收件人的移动电话关闭或未连接到网络。<br /> </td> 
  </tr> 
  <tr> 
   <td> 未定义 </td> 
   <td> 未定义 </td> 
   <td> 0 </td> 
   <td> 该地址正在进行鉴别，因为错误数尚未递增。 当服务器发送新的错误消息时，会发生此类错误： 这可能是一个孤立的错误，但如果再次发生，则错误计数会增加，从而提醒技术团队。然后，他们可以执行消息分析，并通过 <span class="uicontrol">管理</span> / <span class="uicontrol">Campaign Management</span> / <span class="uicontrol">无法交付项管理</span> 树结构中的节点。<br /> </td> 
  </tr> 
  <tr> 
   <td> 不符合选件的资格 </td> 
   <td> 已忽略 </td> 
   <td> 16 </td> 
   <td> 收件人不符合投放中选件的条件。<br /> </td> 
  </tr> 
  <tr> 
   <td> 拒绝 </td> 
   <td> 软/硬 </td> 
   <td> 20 </td> 
   <td> 由于安全反馈为垃圾邮件报告，该地址已置于隔离中。 根据错误，将重试该地址，直到错误计数达到5为止，或直接将其发送到隔离。<br /> </td> 
  </tr> 
  <tr> 
   <td> Target大小有限 </td> 
   <td> 已忽略 </td> 
   <td> 17 </td> 
   <td> 已达到收件人的最大投放大小。<br /> </td> 
  </tr> 
  <tr> 
   <td> 不合格地址 </td> 
   <td> 已忽略 </td> 
   <td> 15 </td> 
   <td> 邮政地址不符合条件。<br /> </td> 
  </tr> 
  <tr> 
   <td> 不可到达 </td> 
   <td> 软/硬 </td> 
   <td> 3 </td> 
   <td> 消息投放链中发生错误。 可能是SMTP中继上的事件、临时不可访问的域等。 根据错误，将重试该地址，直到错误计数达到5为止，或直接将其发送到隔离。<br /> </td> 
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

HTTP/V2协议允许对每次推送交付进行直接反馈和状态。 如果使用HTTP/V2协议连接器，则不再由 **[!UICONTROL mobileAppOptOutMgt]** 工作流。 在卸载或重新安装移动应用程序时，令牌会被视为未注册。

同步，如果APNs为消息返回“未注册”状态，则目标令牌将立即被隔离。

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
   <td> 启用目标设备<br /> </td> 
   <td> 确定<br /> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 关闭目标设备<br /> </td> 
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
   <td> 消息创建/分析阶段 — 负载过大<br /> </td> 
   <td> 失败<br /> </td> 
   <td> 负载过长<br /> </td> 
   <td> 柔和<br /> </td> 
   <td> 拒绝<br /> </td> 
   <td> 否<br /> </td> 
  </tr> 
  <tr> 
   <td> 消息创建/分析阶段 — 意外的内容格式问题<br /> </td> 
   <td> 失败<br /> </td> 
   <td> 根据错误显示的各种错误消息<br /> </td> 
   <td> 柔和<br /> </td> 
   <td> 未定义<br /> </td> 
   <td> 否<br /> </td> 
  </tr> 
  <tr> 
   <td> 证书问题（密码、损坏等） 并测试与APNs问题的连接<br /> </td> 
   <td> 失败<br /> </td> 
   <td> 根据错误显示的各种错误消息<br /> </td> 
   <td> 柔和<br /> </td> 
   <td> 拒绝<br /> </td> 
   <td> 否<br /> </td> 
  </tr> 
  <tr> 
   <td> 发送过程中网络连接丢失<br /> </td> 
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
   <td> 错误消息中将存在错误拒绝原因<br /> </td> 
   <td> 柔和<br /> </td> 
   <td> 拒绝<br /> </td> 
   <td> 否<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Android隔离 {#android-quarantine}

**对于Android V1**

对于每个通知，Adobe Campaign会直接从FCM服务器接收同步错误。 Adobe Campaign会即时处理这些错误，并根据错误的严重性生成硬错误或软错误，并可以执行重试：

* 超出负载长度、连接问题、服务可用性问题：重试，软错误，失败原因 **[!UICONTROL Refused]**.
* 超出设备配额：无重试，软错误，失败原因 **[!UICONTROL Refused]**.
* 无效或未注册的令牌、意外错误、发件人帐户问题：无重试，硬错误，失败原因 **[!UICONTROL Refused]**.

的 **[!UICONTROL mobileAppOptOutMgt]** 工作流每6小时运行一次，以更新 **AppSubscriptionRcp** 表。 对于声明为未注册或不再有效的令牌，该字段 **已禁用** 设置为 **True** 且链接到该设备令牌的订阅将自动从将来投放中排除。

在投放分析过程中，从目标中排除的所有设备都会自动添加到 **excludeLogAppSubRcp** 表。

>[!NOTE]
>
>对于使用百度连接器的客户，以下是不同类型的错误：
>
>* 投放开始时出现连接问题：失败类型 **[!UICONTROL Undefined]**，失败原因 **[!UICONTROL Unreachable]**，则执行重试。
>* 投放期间连接丢失：软错误，失败原因 **[!UICONTROL Refused]**，则执行重试。
>* 百度在发送过程中返回的同步错误：硬错误，失败原因 **[!UICONTROL Refused]**，则不执行重试。
>
>Adobe Campaign每10分钟联系百度服务器以检索已发送消息的状态并更新广告。 如果消息声明为已发送，则广播中消息的状态将设置为 **[!UICONTROL Received]**. 如果百度声明错误，则状态将设置为 **[!UICONTROL Failed]**.

**对于Android V2**

Android V2隔离机制使用与Android V1相同的流程，这同样适用于订阅和排除项更新。 有关更多信息，请参阅 [Android V1](#android-quarantine) 中。

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
   <td> 消息创建/分析阶段：自定义字段中使用的非法关键词<br /> </td> 
   <td> 失败<br /> </td> 
   <td> 不能使用以下关键词：{1}<br /> </td> 
   <td> 柔和<br /> </td> 
   <td> </td> 
   <td> 否<br /> </td> 
  </tr> 
  <tr> 
   <td> 消息创建/分析阶段：负载太大<br /> </td> 
   <td> 失败<br /> </td> 
   <td> 通知过重：{1}位，而只有{2}位已授权<br /> </td> 
   <td> 柔和<br /> </td> 
   <td> 拒绝<br /> </td> 
   <td> 否<br /> </td> 
  </tr> 
  <tr> 
   <td> 发送过程中网络连接丢失<br /> </td> 
   <td> 失败<br /> </td> 
   <td> 地址上没有来自Firebase Cloud Messaging服务的响应：{1}<br /> </td> 
   <td> 柔和<br /> </td> 
   <td> 不可到达<br /> </td> 
   <td> 是<br /> </td> 
  </tr> 
  <tr> 
   <td> FCM报文拒绝：FCM服务器暂时不可用（例如超时）。 <br /> </td> 
   <td> 失败<br /> </td> 
   <td> Firebase Cloud Messaging服务暂时不可用<br /> </td> 
   <td> 柔和<br /> </td> 
   <td> 不可到达<br /> </td> 
   <td> 是<br /> </td> 
  </tr> 
  <tr> 
   <td> FCM报文拒绝：验证发件人帐户时出错<br /> </td> 
   <td> 失败<br /> </td> 
   <td> 无法识别开发人员帐户，请检查您的ID和密码<br /> </td> 
   <td> 柔和<br /> </td> 
   <td> 拒绝<br /> </td> 
   <td> 否<br /> </td> 
  </tr> 
  <tr> 
   <td> FCM报文拒绝：超出设备配额<br /> </td> 
   <td> 失败<br /> </td> 
   <td> </td> 
   <td> 柔和<br /> </td> 
   <td> 拒绝<br /> </td> 
   <td> 是<br /> </td> 
  </tr> 
  <tr> 
   <td> FCM报文拒绝：注册无效/未注册<br /> </td> 
   <td> 失败<br /> </td> 
   <td> </td> 
   <td> 硬<br /> </td> 
   <td> 用户未知<br /> </td> 
   <td> 否<br /> </td> 
  </tr> 
  <tr> 
   <td> FCM报文拒绝：所有其他错误<br /> </td> 
   <td> 失败<br /> </td> 
   <td> Firebase Cloud Messaging服务器返回了意外的错误代码：{1} </td> 
   <td> </td> 
   <td> 拒绝<br /> </td> 
   <td> 否<br /> </td> 
  </tr> 
    <tr> 
   <td> FCM报文拒绝：参数无效<br /> </td> 
   <td> 失败<br /> </td> 
   <td> INVALID_ARGUMENT </td> 
   <td> 已忽略</td> 
   <td> 未定义<br /> </td> 
   <td> 否<br /> </td> 
  </tr>
    <tr> 
   <td> FCM报文拒绝：第三方身份验证错误<br /> </td> 
   <td> 失败<br /> </td> 
   <td> THIRD_PARTY_AUTH_ERROR </td> 
   <td> 已忽略</td>
   <td> 拒绝<br /> </td> 
   <td> 是<br /> </td> 
  </tr>
    <tr> 
   <td> FCM报文拒绝：发件人ID不匹配<br /> </td> 
   <td> 失败<br /> </td> 
   <td> SENDER_ID_MISMATCH </td> 
   <td> 柔和</td>
   <td> 用户未知<br /> </td> 
   <td> 否<br /> </td> 
  </tr>
    <tr> 
   <td> FCM报文拒绝：未注册<br /> </td> 
   <td> 失败<br /> </td>
   <td> 未注册 </td> 
   <td> 硬</td> 
   <td> 用户未知<br /> </td> 
   <td> 否<br /> </td> 
  </tr>
    <tr> 
   <td> FCM报文拒绝：内部<br /> </td> 
   <td> 失败<br /> </td> 
   <td> 内部 </td> 
   <td> 已忽略</td> 
   <td> 拒绝<br /> </td> 
   <td> 是<br /> </td> 
  </tr>
    <tr> 
   <td> FCM报文拒绝：不可用<br /> </td> 
   <td> 失败<br /> </td> 
   <td> 不可用</td> 
   <td> 已忽略</td> 
   <td> 拒绝<br /> </td> 
   <td> 是<br /> </td> 
  </tr>
    <tr> 
   <td> FCM报文拒绝：意外错误代码<br /> </td> 
   <td> 失败<br /> </td> 
   <td> 意外错误代码</td> 
   <td> 已忽略</td> 
   <td> 拒绝<br /> </td> 
   <td> 否<br /> </td> 
  </tr>
  <tr> 
   <td> 身份验证：连接问题<br /> </td> 
   <td> 失败<br /> </td> 
   <td> 无法连接到身份验证服务器 </td> 
   <td> 已忽略</td>
   <td> 拒绝<br /> </td> 
   <td> 是<br /> </td> 
  </tr>
    <tr> 
   <td> 身份验证：请求中的未授权客户端或范围。<br /> </td> 
   <td> 失败<br /> </td> 
   <td> unauthorized_client </td> 
   <td> 已忽略</td>
   <td> 拒绝<br /> </td> 
   <td> 否<br /> </td> 
  </tr>
    <tr> 
   <td> 身份验证：客户端未授权使用此方法检索访问令牌，或者客户端未授权任何请求的作用域。<br /> </td> 
   <td> 失败<br /> </td> 
   <td> unauthorized_client </td> 
   <td> 已忽略</td>
   <td> 拒绝<br /> </td> 
   <td> 否<br /> </td> 
  </tr>
    <tr> 
   <td> 身份验证：拒绝访问<br /> </td> 
   <td> 失败<br /> </td>
   <td> access_denied</td> 
   <td> 已忽略</td>
   <td> 拒绝<br /> </td> 
   <td> 否<br /> </td> 
  </tr>
    <tr> 
   <td> 身份验证：无效电子邮件<br /> </td> 
   <td> 失败<br /> </td> 
   <td> invalid_grant </td> 
   <td> 已忽略</td> 
   <td> 拒绝<br /> </td> 
   <td> 否<br /> </td> 
  </tr>
    <tr> 
   <td> 身份验证：JWT无效<br /> </td> 
   <td> 失败<br /> </td> 
   <td> invalid_grant </td> 
   <td> 已忽略</td> 
   <td> 拒绝<br /> </td> 
   <td> 否<br /> </td> 
  </tr>
    <tr> 
   <td> 身份验证：JWT签名无效<br /> </td> 
   <td> 失败<br /> </td> 
   <td> invalid_grant </td> 
   <td> 已忽略</td> 
   <td> 拒绝<br /> </td> 
   <td> 否<br /> </td> 
  </tr>
    <tr> 
   <td> 身份验证：提供的OAuth范围或ID令牌受众无效<br /> </td> 
   <td> 失败<br /> </td> 
   <td> unauthorized_client</td> 
   <td> 已忽略</td> 
   <td> 拒绝<br /> </td> 
   <td> 否<br /> </td> 
  </tr>
    <tr> 
   <td> 身份验证：已禁用OAuth客户端<br /> </td> 
   <td> 失败<br /> </td> 
   <td> disabled_client</td> 
   <td> 已忽略</td> 
   <td> 拒绝<br /> </td> 
   <td> 否<br /> </td> 
  </tr>
 </tbody> 
</table>

## 短信隔离 {#sms-quarantines}

**对于标准连接器**

短信渠道的特性如下所示。

>[!NOTE]
>
>的 **[!UICONTROL Delivery log qualification]** 表不适用于 **扩展通用SMPP** 连接器。

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
   <td> 发送给提供商<br /> </td> 
   <td> 已发送<br /> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 在移动设备上接收<br /> </td> 
   <td> 已接收<br /> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 提供程序返回的错误<br /> </td> 
   <td> 失败<br /> </td> 
   <td> 接收数据（SR或MO）时出错<br /> </td> 
   <td> 柔和<br /> </td> 
   <td> 不可到达<br /> </td> 
  </tr> 
  <tr> 
   <td> 无效的MT确认<br /> </td> 
   <td> 失败<br /> </td> 
   <td> 处理用于发送查询的确认帧时出错“{1}”<br /> </td> 
   <td> 柔和<br /> </td> 
   <td> 不可到达<br /> </td> 
  </tr> 
  <tr> 
   <td> 发送MT时出错<br /> </td> 
   <td> 失败<br /> </td> 
   <td> 发送消息时出错<br /> </td> 
   <td> 柔和<br /> </td> 
   <td> 不可到达<br /> </td> 
  </tr> 
 </tbody> 
</table>

**对于扩展的通用SMPP连接器**

使用SMPP协议发送短信消息时，错误管理的处理方式不同。

SMPP连接器从SR（状态报告）消息中检索数据，该消息使用正则表达式(regex)返回以过滤其内容。 然后，将此数据与 **[!UICONTROL Delivery log qualification]** 表格(可通过 **[!UICONTROL Administration]** > **[!UICONTROL Campaign Management]** > **[!UICONTROL Non deliverables Management]** 菜单)。

在鉴定新类型的错误之前，失败原因始终设置为 **已拒绝** 默认情况下。

>[!NOTE]
>
>失败类型和失败原因与电子邮件相同。
>
>请向提供商提供状态和错误代码列表，以在投放日志鉴别表中设置正确的失败类型和失败原因。

生成的消息示例：

```
SR Generic DELIVRD 000|#MESSAGE#
```

* 所有错误消息均以 **SR** 以区分短信错误代码和电子邮件错误代码。
* 第二部分(**通用** 在本示例中)的错误消息引用SMSC实施的名称，如 **[!UICONTROL SMSC implementation name]** 短信外部帐户的字段。

   由于同一错误代码对每个提供程序可能具有不同的含义，因此通过此字段，您可以了解哪个提供程序生成了错误代码。 然后，您可以在相关提供商的文档中找到该错误。

* 第三部分(**DELIVRD** 在此示例中)的错误消息对应于从SR中检索的状态代码，该代码使用SMS外部帐户中定义的状态提取正则表达式。

   此正则表达式在 **[!UICONTROL SMSC specificities]** 选项卡。
默认情况下，正则表达式会提取 **stat:** 字段 **附录B** 部分 **SMPP 3.4规范**.

* 第四部分(**000** 在本例中)，错误消息对应于使用短信外部帐户中定义的错误代码提取正则表达式从SR提取的错误代码。

   此正则表达式在 **[!UICONTROL SMSC specificities]** 选项卡。

   默认情况下，正则表达式会提取 **错误：** 字段 **附录B** 部分 **SMPP 3.4规范**.

* 管道符号(|)之后的所有内容仅在 **[!UICONTROL First text]** 列 **[!UICONTROL Delivery log qualification]** 表。 此内容始终由 **#MESSAGE#** 在消息被标准化后。 此过程可避免因类似错误而包含多个条目，且与电子邮件相同。

扩展的通用SMPP连接器应用启发式来查找合理的默认值：如果状态以 **DELIV**，则会被视为成功，因为它与常用状态匹配 **DELIVRD** 或 **已交付** 由大多数提供商使用。 任何其他状态都会导致硬失败。
