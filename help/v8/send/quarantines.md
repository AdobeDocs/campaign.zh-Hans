---
title: Campaign中的隔离管理
description: 了解Adobe Campaign中的隔离管理
feature: Audiences, Profiles
role: Data Engineer
level: Beginner
exl-id: 220b7a88-bd42-494b-b55b-b827b4971c9e
source-git-commit: 5c1ced7972295e79418ac7ff14a6f0888e5ed39a
workflow-type: tm+mt
source-wordcount: '1097'
ht-degree: 5%

---

# 隔离 {#quarantine-management}

Adobe Campaign管理了在线渠道（电子邮件、短信、推送通知）的隔离地址列表。 如果无效地址率过高，某些互联网访问提供商会自动将电子邮件视为垃圾邮件。 因此，隔离可让您避免被这些提阻止列表供商添加到。 此外，隔离还可避免向错误的电话号码投放短信，有助于降低短信发送成本。

隔离收件人的地址或电话号码后，投放分析期间会将收件人从目标中排除：您将无法向这些联系人发送营销消息（包括自动工作流电子邮件）。 如果这些隔离的地址也存在于列表中，则在发送到这些列表时，会将其排除。 例如，当邮箱已满、地址不存在或电子邮件服务器不可用时，可以隔离某个电子邮件地址。

<!--For more on best practices to secure and optimize your deliveries, refer to [this page](delivery-best-practices.md).-->

**隔离** 仅应用于 **地址**, a **电话号码**&#x200B;或 **设备令牌**，但对用户档案本身不是。 例如，其电子邮件地址已被隔离的用户档案可以更新其用户档案并输入新地址，然后可以再次通过投放操作定向该用户档案。 同样，如果两个用户档案的电话号码恰巧相同，那么隔离该号码后，这两个用户档案都将受到影响。 隔离的地址或电话号码显示在 [排除日志](#delivery-quarantines) （用于投放）或 [隔离列表](#non-deliverable-bounces) （适用于整个平台）。

另一方面，用户档案可以位于 **阻止列表** 与退订（选择退出）后的给定渠道一样：这意味着它们不再为任何目标。 因此，如果电子邮件渠道上的用阻止列表户档案具有两个电子邮件地址，则这两个地址都将被排除在投放之外。 您可以检查用户档案是否位阻止列表于上，查看 **[!UICONTROL No longer contact]** 部分 **[!UICONTROL General]** 选项卡。 [了解详情](../audiences/view-profiles.md)

>[!NOTE]
>
>当收件人将您的消息报告为垃圾邮件或通过“STOP”之类的关键字回复短信消息时，其地址或电话号码将被隔离为 **[!UICONTROL Denylisted]**. 他们的用户档案会相应地更新。

<!--For the email channel, email addresses are quarantined. For the mobile app channel, device tokens are quarantined. For the SMS channel, phone numbers are quarantined.?-->

## 为什么要将电子邮件、电话或设备添加到隔离 {#quarantine-reason}

Adobe Campaign根据投放失败类型及其原因管理隔离。 在错误消息鉴别期间会分配这些值。 了解有关投放失败管理的更多信息 [本页](delivery-failures.md).

可以捕获两种类型或错误：

* **硬错误**:电子邮件地址、电话号码或设备会立即添加到隔离。
* **软错误**:软错误会增加错误计数，并可能会隔离电子邮件、电话号码或设备令牌。 Campaign执行 [重试](delivery-failures.md#retries):当错误计数达到限制阈值时，将隔离地址、电话号码或设备令牌。 [了解详情](delivery-failures.md#retries)。

隔离地址列表中， **[!UICONTROL Error reason]** 字段指示将选定地址置于隔离中的原因。 [了解详情](#identifying-quarantined-addresses-for-the-entire-platform)。


如果用户将电子邮件标记为垃圾邮件，则该邮件会自动重定向到由Adobe管理的技术邮箱。 随后，该用户的电子邮件地址会自动添加到隔离，并附加 **[!UICONTROL Denylisted]** 状态。此状态仅指地址，用户档案不在阻止列表上，因此用户可继续接收短信消息和推送通知。 详细了解 [投放最佳实践指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#feedback-loops){target=&quot;_blank&quot;}。

>[!NOTE]
>
>Adobe Campaign 中的隔离会区分大小写字母。请确保以小写方式导入电子邮件地址，这样以后就不会重新定向这些地址。

## 访问隔离的地址 {#access-quarantined-addresses}

可以为特定投放或整个平台显示隔离的地址。

### 投放的隔离{#delivery-quarantines}

在投放准备阶段期间，投放仪表板的投放日志中会列出隔离地址。

对于每个投放，您还可以检查 **[!UICONTROL Delivery summary]** 报表：它显示投放目标中隔离的地址数，并显示：

* 在投放分析期间隔离的地址数，
* 在投放操作后置于隔离中的地址数。

### 不可交付和退回地址{#non-deliverable-bounces}

查看隔离地址列表 **整个平台**, Campaign管理员可以浏览  **[!UICONTROL Administration > Campaign Management > Non deliverables Management > Non deliverables and addresses]**. 此部分列出了 **电子邮件**, **短信** 和 **推送通知** 渠道。

![](assets/tech-quarantine.png)

>[!NOTE]
>
>隔离数量会随着时间的推移而增加。 例如，如果将电子邮件地址的生命周期视为三年，而收件人表每年增加50%，则隔离的增加可以按如下方式计算：
>
>年末1:(1)&#42;0.33)/(1+0.5)=22%。
>
>年末2年：(1.22)&#42;0.33)+0.33)/(1.5+0.75)=32.5%。

此外， **[!UICONTROL Non-deliverables and bounces]** 内置报告，可从 **报表** 部分，按域显示有关隔离中地址、遇到的错误类型和失败划分的信息。 您可以过滤特定投放的数据，或根据需要自定义此报表。

了解有关 [投放能力最佳实践指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html){target=&quot;_blank&quot;}。

### 隔离的电子邮件地址 {#quarantined-recipient}

您可以查找任何收件人的电子邮件地址状态。

要执行此操作，请选择收件人用户档案，然后单击 **[!UICONTROL Deliveries]** 选项卡。 对于发送给该收件人的所有投放，您可以了解地址是否失败、在分析期间是否被隔离等。

对于每个文件夹，您只能显示电子邮件地址处于隔离状态的收件人，并且 **[!UICONTROL Quarantined email address]** 内置过滤器，如下所示：

![](assets/quarantine-filter.png)


## 删除隔离地址 {#remove-a-quarantined-address}

符合特定条件的地址将由 **数据库清理** 内置工作流。

在以下情况下，地址会自动从隔离列表中删除：

* 中的地址 **[!UICONTROL With errors]** 成功投放后，状态将从隔离列表中删除。
* 中的地址 **[!UICONTROL With errors]** 如果上次软退件发生在10天以前，则会从隔离列表中删除状态。 有关软错误管理的更多信息，请参阅 [此部分](#soft-error-management).
* 中的地址 **[!UICONTROL With errors]** 状态 **[!UICONTROL Mailbox full]** 30天后将从隔离列表中删除错误。

其状态随后更改为 **[!UICONTROL Valid]**.

>[!CAUTION]
>
>地址在 **[!UICONTROL Quarantine]** 或 **[!UICONTROL Denylisted]** 即使收到电子邮件，状态也永远不会被删除。

您还可以从隔离列表中手动删除地址。 要从隔离中删除地址，您可以：

* 将其状态更改为 **[!UICONTROL Valid]** 从 **[!UICONTROL Administration > Campaign Management > Non deliverables Management > Non deliverables and addresses]** 节点。

   ![](assets/tech-quarantine-status.png)

* 将其状态更改为 **[!UICONTROL Allowlisted]**:在这种情况下，地址仍保留在隔离列表中，但会系统地定位该地址，即使遇到错误也是如此。

>[!CAUTION]
>
>如果从隔离列表中删除某个地址，则将再次向此地址发送。 这可能会对您的投放能力和IP信誉造成严重影响，最终可能会导致您的IP地址或发送域被阻止。 考虑从隔离中删除任何地址时，请格外小心。 如果您需要帮助，请联系Adobe支持。
