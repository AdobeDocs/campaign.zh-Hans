---
title: 在Campaign中查看现有用户档案
description: 了解如何在Campaign中访问联系人数据
feature: Audiences, Profiles
role: Data Engineer
level: Beginner
exl-id: 03f7a736-e0b9-4216-9550-507f10e6fcf6
source-git-commit: d2f4e54b0c37cc019061dd3a7b7048cd80876ac0
workflow-type: tm+mt
source-wordcount: '567'
ht-degree: 16%

---

# 查看现有配置文件{#view-profiles}

浏览到 **[!UICONTROL Profiles and targets]** 访问存储在Adobe Campaign数据库中的收件人。

在此页面中，您可以 [创建新收件人](create-profiles.md)，编辑现有收件人并访问其配置文件详细信息。

![](assets/profiles-and-targets.png)

要进行更高级的用户档案操作，请访问 **[!UICONTROL Explorer]** Adobe Campaign主页上的链接。

![](assets/recipients-in-explorer.png)


>[!CAUTION]
>
>内置的“收件人”屏幕通过XML架构及其关联的表单进行定义。 XML架构存储在 **[!UICONTROL Administration > Configuration > Data schemas]** Adobe Campaign资源管理器树的节点。 只有专家用户才能改变这些模式。

## 编辑用户档案{#edit-a-profiles}

选择一个配置文件以在新选项卡中显示详细信息。

![](assets/edit-a-profile.png)

用户档案相关数据被分组放在多个选项卡中。这些选项卡及其内容取决于您的特定设置和已安装的包。

对于典型的内置收件人，您可以访问以下选项卡：

* **[!UICONTROL General]**，以获取所有一般用户档案数据。 其中特别包含姓氏、名字、电子邮件地址、电子邮件格式等。

   此选项卡还存储 **选择禁用** 配置文件的标记：当 **[!UICONTROL No longer contact (by any channel)]** 选项时，配置文件处于状阻止列表态。 例如，如果收件人单击了新闻稿中的退订链接，则会将此信息添加到联系数据中。 此类收件人不再是任何渠道（电子邮件、直邮等）的目标收件人。 有关详细信息，请参见[此页面](../send/quarantines.md)。

* **联系信息**，其中包含选定用户档案的直邮地址。

   您可以在此屏幕中查看地址的质量索引以及地址包含的错误数。 直邮提供商会根据在先前投放中发现的错误数直接使用此信息，且无法手动更改。

* **其他**，用于可以根据需要个性化和填充的特定字段。

   使用 **[!UICONTROL Field properties…]** 用于更改字段名称并定义其格式的上下文菜单。

   ![](assets/other-tab-field-properties.png)

   按如下方式输入新设置：

   ![](assets/change-field-properties.png)

   在UI中检查更新：

   ![](assets/other-tab-updated.png)


   >[!CAUTION]
   >更改适用于所有收件人。


* **订阅**，用于所有活跃的服务订阅。 使用 **历史** 选项卡，访问此联系人的订阅和取消订阅的详细信息。

   ![](assets/subscription-tab.png)

   了解有关订阅的更多信息 [在此部分中](../start/subscriptions.md).

* **投放**，用于选定用户档案的所有投放日志。 使用此选项卡访问联系人的营销历史：通过所有渠道发送给用户档案的所有投放操作的标签、日期和状态。


* **跟踪**，用于选定用户档案的所有跟踪日志。 此信息用于跟踪投放后用户档案的行为。此选项卡显示在投放中所有被跟踪的 URL 累积数目。该列表是可配置的，通常包含：点击的URL、点击日期和时间，以及包含该URL的文档

   了解有关跟踪的更多信息 [在此部分中](../start/tracking.md).


## 使用中的用户档案 {#active-profiles}

使用中的用户档案是指可计费开立账单的用户档案。

计费账单的开立仅会考虑&#x200B;**使用中**&#x200B;的用户档案。如果用户档案在过去 12 个月通过任何渠道被定位或进行了传输，则该用户档案被视为使用中。

已被多个投放定向的用户档案将仅计数一次。

活动用户档案计数可用于 **营销实例** 仅。 它不适用于执行实例，即MID（中间采购）和RT（消息中心/实时消息）实例。

>[!NOTE]
>
>您还可以直接从Campaign控制面板监控实例上的活动用户档案数。 有关更多信息，请参阅 [控制面板文档](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html).
