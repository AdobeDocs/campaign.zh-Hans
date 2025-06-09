---
title: Campaign中的隔离管理
description: 了解Adobe Campaign中的隔离管理
feature: Profiles, Monitoring
role: User, Data Engineer
level: Beginner
exl-id: 220b7a88-bd42-494b-b55b-b827b4971c9e
source-git-commit: e45799f0f3849d53d2c5f593bc02954b3a55fc28
workflow-type: tm+mt
source-wordcount: '1167'
ht-degree: 4%

---

# 隔离 {#quarantine-management}

Adobe Campaign可管理在线渠道（电子邮件、短信、推送通知）的隔离地址列表。 如果无效地址的比率过高，某些互联网访问提供商会自动将电子邮件视为垃圾邮件。 因此，隔离可让您避免被这些提供商添加到阻止列表。 此外，隔离还可避免向错误的电话号码投放短信，有助于降低短信发送成本。

隔离收件人的地址或电话号码后，在投放分析期间会将收件人从目标中排除：您将无法向这些联系人发送营销消息，包括自动工作流电子邮件。 如果隔离的地址也存在于列表中，则在将其发送到这些列表时将排除这些地址。 例如，当邮箱已满、地址不存在或电子邮件服务器不可用时，可以隔离电子邮件地址。

<!--For more on best practices to secure and optimize your deliveries, refer to [this page](delivery-best-practices.md).-->

**隔离**&#x200B;仅适用于&#x200B;**地址**、**电话号码**&#x200B;或&#x200B;**设备令牌**，而不适用于配置文件本身。 例如，其电子邮件地址被隔离的用户档案可以更新其用户档案并输入新地址，然后再次被投放操作定向。 同样，如果两个用户档案碰巧拥有相同的电话号码，那么隔离该号码将会同时影响这两个用户档案。 隔离的地址或电话号码显示在[排除日志](#delivery-quarantines)（针对投放）或[隔离列表](#non-deliverable-bounces)（针对整个平台）中。

另一方面，对于给定渠道，配置文件在退订（选择退出）后可以位于&#x200B;**阻止列表**&#x200B;上：这意味着它们不再为任何渠道所定向。 因此，如果电子邮件渠道阻止列表上的用户档案有两个电子邮件地址，则这两个地址都将排除在投放之外。 您可以在配置文件的&#x200B;**[!UICONTROL General]**&#x200B;选项卡的&#x200B;**[!UICONTROL No longer contact]**&#x200B;部分中检查配置文件是否正在阻止列表一个或多个渠道。 [了解详情](../audiences/view-profiles.md)

>[!NOTE]
>
>当收件人将您的邮件报告为垃圾邮件或使用“STOP”等关键字回复短信时，其地址或电话号码将被隔离为&#x200B;**[!UICONTROL Denylisted]**。 其用户档案会相应地更新。

<!--For the email channel, email addresses are quarantined. For the mobile app channel, device tokens are quarantined. For the SMS channel, phone numbers are quarantined.?-->

## 为何要向隔离区发送电子邮件、电话或设备 {#quarantine-reason}

Adobe Campaign根据投放失败的类型及其原因管理隔离。 这些在错误消息鉴别期间分配。 在此页面](delivery-failures.md)上了解有关投放失败管理[的更多信息。

可以捕获两种类型或错误：

* **硬错误**：将立即将电子邮件地址、电话号码或设备添加到隔离。
* **软错误**：软错误会增加错误计数，并可能隔离电子邮件、电话号码或设备令牌。 Campaign执行[重试](delivery-failures.md#retries)：当错误计数器达到限制阈值时，将隔离地址、电话号码或设备令牌。 [了解详情](delivery-failures.md#retries)。

在隔离地址列表中，**[!UICONTROL Error reason]**&#x200B;字段指示将选定地址置于隔离状态的原因。 [了解详情](#identifying-quarantined-addresses-for-the-entire-platform)。


如果用户将电子邮件标记为垃圾邮件，则该邮件会自动重定向到由Adobe管理的技术邮箱。 随后，该用户的电子邮件地址会自动添加到隔离，并附加 **[!UICONTROL Denylisted]** 状态。此状态仅适用于地址，用户档案不在阻止列表上，因此用户可继续接收短信和推送通知。 在[投放最佳实践指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#feedback-loops){target="_blank"}中了解有关反馈循环的更多信息。

>[!NOTE]
>
>Adobe Campaign 中的隔离会区分大小写字母。请确保以小写方式导入电子邮件地址，这样以后就不会重新定向这些地址。

## 访问隔离的地址 {#access-quarantined-addresses}

可以为特定投放或整个平台显示隔离的地址。

### 投放隔离{#delivery-quarantines}

在投放准备阶段期间，投放仪表板的投放日志中会列出隔离地址。

对于每次投放，您还可以检查&#x200B;**[!UICONTROL Delivery summary]**&#x200B;报告：其中显示投放目标中隔离的地址数并显示：

* 投放分析期间被隔离的地址数，
* 投放操作后放置到隔离区的地址数。

### 无法投放地址和退回地址{#non-deliverable-bounces}

要查看整个平台&#x200B;**的隔离地址**&#x200B;列表，Campaign管理员可以浏览到&#x200B;**[!UICONTROL Administration > Campaign Management > Non deliverables Management > Non deliverables and addresses]**。 此部分列出了&#x200B;**电子邮件**、**短信**&#x200B;和&#x200B;**推送通知**&#x200B;渠道的隔离元素。

![](assets/tech-quarantine.png)

>[!NOTE]
>
>隔离的数量会随时间而增加。 例如，如果将电子邮件地址的生命周期视为三年，并且收件人表每年增加50%，则隔离的增加可以按如下方式计算：
>
>第1年年末： (1&#42;0.33)/(1+0.5)=22%。
>
第2年年末：((1.22&#42;0.33)+0.33)/(1.5+0.75)=32.5%。

此外，可从主页的&#x200B;**报告**&#x200B;部分找到的&#x200B;**[!UICONTROL Non-deliverables and bounces]**&#x200B;内置报告显示有关隔离地址、遇到的错误类型以及按域划分的失败的信息。 您可以过滤特定投放的数据，或根据需要自定义此报表。

在[可投放性最佳实践指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html){target="_blank"}中了解有关退回地址的更多信息。

### 隔离的电子邮件地址 {#quarantined-recipient}

您可以查找任何收件人的电子邮件地址的状态。

为此，请选择收件人配置文件，然后单击&#x200B;**[!UICONTROL Deliveries]**&#x200B;选项卡。 对于发送给该收件人的所有投放，您可以查明地址是否出现故障，在分析期间是否被隔离等。

对于每个文件夹，您只能显示其电子邮件地址处于隔离状态的收件人，并具有&#x200B;**[!UICONTROL Quarantined email address]**&#x200B;内置过滤器，如下所示：

![](assets/quarantine-filter.png)


## 删除隔离的地址 {#remove-a-quarantined-address}

符合特定条件的地址会由&#x200B;**数据库清理**&#x200B;内置工作流自动从隔离列表中删除。

在以下情况下，地址会自动从隔离列表中删除：

* 成功投放后，将从隔离列表中删除处于&#x200B;**[!UICONTROL With errors]**&#x200B;状态的地址。
* 如果最后一次软退回发生在10天之前，则会从隔离列表中删除处于&#x200B;**[!UICONTROL With errors]**&#x200B;状态的地址。 有关软错误管理的详细信息，请参阅[此部分](#soft-error-management)。
* 状态为&#x200B;**[!UICONTROL With errors]**&#x200B;且出现&#x200B;**[!UICONTROL Mailbox full]**&#x200B;错误退回的地址将在30天后从隔离列表中删除。

其状态随后更改为&#x200B;**[!UICONTROL Valid]**。

>[!CAUTION]
>
永远不会移除地址处于&#x200B;**[!UICONTROL Quarantine]**&#x200B;或&#x200B;**[!UICONTROL Denylisted]**&#x200B;状态的收件人，即使他们收到电子邮件也是如此。

您也可以从隔离列表中手动删除地址。 要从隔离中删除地址，您可以：

* 从&#x200B;**[!UICONTROL Administration > Campaign Management > Non deliverables Management > Non deliverables and addresses]**&#x200B;节点将其状态更改为&#x200B;**[!UICONTROL Valid]**。

  ![](assets/tech-quarantine-status.png)

您可能需要对隔离列表执行批量更新，例如，在ISP中断的情况下，电子邮件被错误地标记为退回，因为它们无法成功传递给收件人。

要执行此操作，请创建一个工作流并在您的隔离表上添加查询，以筛选掉所有受影响的收件人，以便将这些收件人从隔离列表中删除，并将其包含在将来的Campaign电子邮件投放中。

以下是此查询的建议准则：

* **错误文本（隔离文本）**&#x200B;包含“Momen_Code10_InvalidRecipient”
* **电子邮件域(@domain)**&#x200B;等于domain1.com或&#x200B;**电子邮件域(@domain)**&#x200B;等于domain2.com或&#x200B;**电子邮件域(@domain)**&#x200B;等于domain3.com
* **更新状态(@lastModified)**&#x200B;在`MM/DD/YYYY HH:MM:SS AM`或之后
* **在`MM/DD/YYYY HH:MM:SS PM`或之前更新状态(@lastModified)**

获得受影响的收件人列表后，添加&#x200B;**[!UICONTROL Update data]**&#x200B;活动以将其状态设置为&#x200B;**[!UICONTROL Valid]**，以便&#x200B;**[!UICONTROL Database cleanup]**&#x200B;工作流将其从隔离列表中删除。 也可以直接从隔离表中删除它们。

