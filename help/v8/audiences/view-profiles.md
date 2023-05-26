---
title: 查看Campaign中的现有用户档案
description: 了解如何在Campaign中访问联系数据
feature: Audiences, Profiles
role: User
level: Beginner
exl-id: 03f7a736-e0b9-4216-9550-507f10e6fcf6
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '567'
ht-degree: 16%

---

# 查看现有配置文件{#view-profiles}

浏览到 **[!UICONTROL Profiles and targets]** 访问存储在Adobe Campaign数据库中的收件人。

在此页面中，您可以 [创建新收件人](create-profiles.md)，编辑现有收件人并访问其用户档案详细信息。

![](assets/profiles-and-targets.png)

要获得更高级的配置文件操作，请从以下位置访问Campaign树： **[!UICONTROL Explorer]** Adobe Campaign主页上的链接。

![](assets/recipients-in-explorer.png)


>[!CAUTION]
>
>内置收件人屏幕是通过XML架构及其关联表单定义的。 XML架构存储在 **[!UICONTROL Administration > Configuration > Data schemas]** Adobe Campaign资源管理器树的节点。 只有专家用户才能改变这些模式。

## 编辑用户档案{#edit-a-profiles}

选择一个配置文件以在新选项卡中显示详细信息。

![](assets/edit-a-profile.png)

用户档案相关数据被分组放在多个选项卡中。这些选项卡及其内容取决于您的特定设置和已安装的包。

对于典型的内置收件人，您可以访问以下选项卡：

* **[!UICONTROL General]**，用于所有常规配置文件数据。 其中特别包含姓氏、名字、电子邮件地址、电子邮件格式等。

   此选项卡还存储 **选择退出** 配置文件的标记：当 **[!UICONTROL No longer contact (by any channel)]** 选项时，配置文件处于阻止列表状态。 例如，如果收件人单击了新闻稿中的退订链接，则此信息会添加到联系人数据中。 任何渠道（电子邮件、直邮等）不再定向此类收件人。 有关详细信息，请参见[此页面](../send/quarantines.md)。

* **联系信息**，其中包含所选用户档案的直邮地址。

   您可以在此屏幕中检查地址的质量索引，以及地址包含多少错误。 此信息由直邮提供商根据在以前的投放过程中发现的错误数直接使用，不能手动更改。

* **其他**，用于特定字段，这些字段可以根据您的需求进行个性化和填充。

   使用 **[!UICONTROL Field properties…]** 上下文菜单，用于更改字段名称并定义其格式。

   ![](assets/other-tab-field-properties.png)

   输入新设置，如下所示：

   ![](assets/change-field-properties.png)

   在UI中检查更新：

   ![](assets/other-tab-updated.png)


   >[!CAUTION]
   >更改适用于所有收件人。


* **订阅**，适用于所有活动的服务订阅。 使用 **历史记录** 选项卡访问该联系人的订阅和未订阅的详细信息。

   ![](assets/subscription-tab.png)

   了解有关订阅的更多信息 [在此部分中](../start/subscriptions.md).

* **投放**，用于选定用户档案的所有投放日志。 使用此选项卡可访问联系人的营销历史记录：通过所有渠道针对用户档案的所有投放操作的标签、日期和状态。


* **跟踪**，用于选定用户档案的所有跟踪日志。 此信息用于跟踪投放后用户档案的行为。此选项卡显示在投放中所有被跟踪的 URL 累积数目。该列表是可配置的，通常包含：点击的URL、点击的日期和时间，以及包含该URL的文档

   了解有关跟踪的更多信息 [在此部分中](../start/tracking.md).


## 使用中的用户档案 {#active-profiles}

使用中的用户档案是指可计费开立账单的用户档案。

计费账单的开立仅会考虑&#x200B;**使用中**&#x200B;的用户档案。如果用户档案在过去 12 个月通过任何渠道被定位或进行了传输，则该用户档案被视为使用中。

多次投放所定向的用户档案仅计数一次。

活动配置文件计数可用于 **营销实例** 仅此而已。 它不适用于执行实例，即MID （中间源）和RT （消息中心/实时消息传递）实例。

>[!NOTE]
>
>您还可以直接通过Campaign控制面板监控实例上的活动用户档案数。 有关详情，请参阅 [控制面板文档](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html).
