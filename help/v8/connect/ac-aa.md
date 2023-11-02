---
title: 使用Campaign和Adobe Analytics
description: 了解如何集成Campaign和Analytics
feature: Analytics Integration, Reporting
role: Admin, User
level: Beginner
exl-id: 11370fb6-e192-4626-944e-b80a7496e50d
source-git-commit: f577ee6d303bab9bb07350b60cf0fa6fc9d3a163
workflow-type: tm+mt
source-wordcount: '1075'
ht-degree: 71%

---

# 使用Campaign和Adobe Analytics {#ac-aa}

您可以配置Adobe Analytics以集成Campaign和Analytics。

此集成允许Adobe Campaign和Adobe Analytics通过 **网站分析连接器** 加载项。 此集成将Adobe Campaign投放的电子邮件营销活动的指标和属性发送到Adobe Analytics。

![](../assets/do-not-localize/speech.png)  作为托管Cloud Service用户， [联系人Adobe](../start/campaign-faq.md#support) 将Campaign与Adobe Experience Cloud服务和解决方案配合使用。 必须通过专用软件包在您的环境中安装Web Analytics连接器加载项。

使用 Adobe Analytics Connector，Adobe Campaign 可以对互联网受众进行评测（网站分析）。利用Web分析工具，Adobe Campaign可将指标和营销活动属性转发到Analytics。

每个工具的操作周边如下所示：

* **Adobe Analytics** 标记通过Adobe Campaign启动的电子邮件营销活动

* **Adobe Campaign** 将指标和营销活动属性发送到连接器，连接器将它们转发到网站分析工具


>[!CAUTION]
>
>Adobe Analytics Connector 与事务性消息传递（消息中心）不兼容。

要设置Campaign-Analytics连接，必须执行以下操作：

1. [在 Adobe Analytics 中创建报表包](#report-suite-analytics)
1. [配置转化变量和成功事件](#configure-conversion-success)
1. [在 Adobe Campaign 中配置外部帐户](#external-account-ac)

## 创建Analytics报表包 {#report-suite-analytics}

要创建您的 **[!UICONTROL Report suite]** 在 [!DNL Adobe Analytics]，请按照以下步骤操作：

1. 在 [!DNL Adobe Analytics] 中，选择 **[!UICONTROL Admin tab]**，然后单击 **[!UICONTROL All admin]**。

   ![](assets/analytics_connnector_1.png)

1. 单击 **[!UICONTROL Report suites]**。

   ![](assets/analytics_connnector_2.png)

1. 在 **[!UICONTROL Report suite manager]** 页面中，依次单击 **[!UICONTROL Create new]** 和 **[!UICONTROL Report suite]**。

   有关创建 **[!UICONTROL Report suite]** 的详细过程，请参阅此[部分](https://experienceleague.adobe.com/docs/analytics/admin/manage-report-suites/new-report-suite/t-create-a-report-suite.html#prerequisites)。

   ![](assets/analytics_connnector_3.png)

1. 选择模板。

1. 使用以下信息配置新报表包：

   * **[!UICONTROL Report Suite ID]**
   * **[!UICONTROL Site Title]**
   * **[!UICONTROL Time Zone]**
   * **[!UICONTROL Go Live Date]**
   * **[!UICONTROL Estimated Page Views Per Day]**

   ![](assets/analytics_connnector_4.png)

1. 配置后，单击 **[!UICONTROL Create report suite]**。

## 配置转化变量和成功事件 {#configure-conversion-success}

创建 **[!UICONTROL Report suite]** 后，您需要按如下方式配置 **[!UICONTROL Conversion variables]** 和 **[!UICONTROL Success events]**：

1. 选择您之前配置的 **[!UICONTROL Report suite]**。

1. 在 **[!UICONTROL Edit settings]** 按钮中，选择 **[!UICONTROL Conversion]** > **[!UICONTROL Conversion variables]**。

   ![](assets/analytics_connnector_5.png)

1. 单击 **[!UICONTROL Add new]** 以创建评测电子邮件营销活动影响所需的标识符，即内部营销活动名称 (cid) 和 iNmsBroadlog (bid) 表 ID。

   如需了解如何编辑 **[!UICONTROL Conversion variables]**，请参阅此[部分](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/t-conversion-variables-admin.html#admin-tools)。

   ![](assets/analytics_connnector_6.png)

1. 完成后单击 **[!UICONTROL Save]**。

1. 然后，要创建 **[!UICONTROL Success events]**，请在 **[!UICONTROL Edit settings]** 按钮中选择 **[!UICONTROL Conversion]** > **[!UICONTROL Success events]**。

   ![](assets/analytics_connnector_7.png)

1. 单击 **[!UICONTROL Add new]** 以配置以下 **[!UICONTROL Success events]**：

   * **[!UICONTROL Clicked]**
   * **[!UICONTROL Opened]**
   * **[!UICONTROL Person clicks]**
   * **[!UICONTROL Processed]**
   * **[!UICONTROL Scheduled]**
   * **[!UICONTROL Sent]**
   * **[!UICONTROL Total bounces]**
   * **[!UICONTROL Unique Clicks]**
   * **[!UICONTROL Unique Opens]**
   * **[!UICONTROL Unsubscribed]**

   要了解如何配置 **[!UICONTROL Success events]**，请参阅此[部分](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/success-events/t-success-events.html#admin-tools)

   ![](assets/analytics_connnector_8.png)

1. 完成后单击 **[!UICONTROL Save]**。

配置报表包后，您需要配置 **[!UICONTROL External accounts]** 在Adobe Campaign中。

## 配置Campaign外部帐户 {#external-account-ac}

现在，您需要在 Adobe Campaign 中配置 **[!UICONTROL Web Analytics]** 外部帐户，以启用两种解决方案之间的同步。

请注意，如果在配置外部帐户时，您的 **[!UICONTROL Report suite]**、**[!UICONTROL Conversion variables]** 或 **[!UICONTROL Success events]** 不可见，这意味着您在与用户关联的 **[!UICONTROL Product profile]** 中缺少对此新创建组件的权限。

有关此内容的更多信息，请参阅 [Adobe Analytics 的产品配置文件](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/product-profile.html#product-profile-admins)页面。

1. 转到 Adobe Campaign 树的 **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL External accounts]** 文件夹，然后单击 **[!UICONTROL New]**。

   ![](assets/analytics_connnector_9.png)

1. 使用下拉列表从 **[!UICONTROL Integration]** 下拉列表中选择 **[!UICONTROL Web Analytics]** 类型和 **[!UICONTROL Adobe Analytics]**。

   ![](assets/analytics_connnector_10.png)

1. 单击 **[!UICONTROL Integration]** 下拉列表旁边的 **[!UICONTROL Configure]**。

1. 从 **[!UICONTROL Configure Analytics integration]** 窗口中，将外部帐户映射到之前创建的报表包，并提供以下信息：

   * **[!UICONTROL E-Mail]**
   * **[!UICONTROL IMS Org]**
   * **[!UICONTROL Analytics Company]**
   * **[!UICONTROL Report Suite]**


1. 在 **[!UICONTROL eVars]** 类别中，映射在 [!DNL Adobe Analytics] 中配置的两个 **[!UICONTROL Conversion variables]**。

   ![](assets/analytics_connnector_11.png)

1. 在 **[!UICONTROL Events]** 类别中，映射在 [!DNL Adobe Analytics] 中配置的十个 **[!UICONTROL Success events]**。

1. 完成后单击 **[!UICONTROL Submit]**。Adobe Campaign 将在映射的 Analytics **[!UICONTROL Report Suite]** 中创建 **[!UICONTROL Data source]**、**[!UICONTROL Calculated metrics]**、**[!UICONTROL Remarketing segments]** 和 **[!UICONTROL Classifications]**。

   在 [!DNL Adobe Analytics] 和 Adobe Campaign 之间完成同步后，您可以关闭此窗口。

1. 可以从 **[!UICONTROL Configure Analytics integration]** 窗口的 **[!UICONTROL Data Settings]** 选项卡中查看设置。

   使用 **[!UICONTROL Sync]** 按钮，[!DNL Adobe Campaign] 将会同步在 [!DNL Adobe Analytics] 中完成的名称变更。如果组件在 [!DNL Adobe Analytics] 中被删除，则将在 [!DNL Adobe Campaign] 中删除该组件，或显示&#x200B;**未找到**&#x200B;消息。

   ![](assets/analytics_connnector_12.png)

   >[!NOTE]
   >
   > 您无法在此版本的Campaign v8中添加或删除区段。

1. 在 **[!UICONTROL External account]** 中，单击 **[!UICONTROL Enrich the formula...]** 链接以更改 URL 计算公式，以指定网站分析工具集成信息（活动 ID）以及必须跟踪其活动的网站域名。

   ![](assets/analytics_connnector_13.png)

1. 指明网站的域名。

   ![](assets/analytics_connnector_14.png)

1. 单击 **[!UICONTROL Next]** 并确保域名已保存。

   ![](assets/analytics_connnector_15.png)

1. 如有必要，您可以让计算公式过载运行。要实现此目的，请勾选方框并直接在窗口中编辑公式。

   >[!IMPORTANT]
   >
   >此配置模式为专家用户而设：公式中的任何错误都可能导致电子邮件投放停止。

1. **[!UICONTROL Advanced]** 选项卡可让您配置或修改更多技术设置。

   * **[!UICONTROL Lifespan]**：可让您指定延迟（以天为单位），在此之后技术工作流会在 Adobe Campaign 中恢复网站事件。默认值：180 天。
   * **[!UICONTROL Persistence]**：可让您指定将所有网站事件（例如购买）归因到再营销活动的时段，默认值：7 天。

>[!NOTE]
>
>如果您使用多个受众衡量工具，则在创建外部帐户时，可以在 **[!UICONTROL Partners]** 下拉列表中选择 **[!UICONTROL Other]**。您只能在投放属性中引用一个外部帐户：因此，您需要通过添加 Adobe 以及使用的所有其他衡量工具预期的参数来调整跟踪 URL 的公式。

## 网站分析流程的技术工作流 {#technical-workflows-of-web-analytics-processes}

Adobe Campaign和Adobe Analytics之间的数据交换由作为后台任务运行的技术工作流处理。

此工作流可从Campaign Explorer树的 **[!UICONTROL Administration]** > **[!UICONTROL Production]** > **[!UICONTROL Technical workflows]** > **[!UICONTROL Web analytics process]** 文件夹。

![](assets/webanalytics_workflows.png)

此 **[!UICONTROL Sending of indicators and campaign attributes]** 工作流可让您使用Adobe Analytics Connector通过Adobe Campaign将电子邮件营销活动指标发送到Adobe Experience Cloud。 此工作流在每天凌晨 4 点触发，可能需要 24 小时才能将数据发送到 Analytics。

请注意，切勿重新启动此工作流，否则它将重新发送所有先前数据，可能会影响 Analytics 结果的准确性。

所涉指标包括：

* **[!UICONTROL Messages to deliver]** (@toDeliver)
* **[!UICONTROL Processed]** (@processed)
* **[!UICONTROL Success]** (@success)
* **[!UICONTROL Total count of opens]** (@totalRecipientOpen)
* **[!UICONTROL Recipients who have opened]** (@recipientOpen)
* **[!UICONTROL Total number of recipients who clicked]** (@totalRecipientClick)
* **[!UICONTROL People who clicked]** (@personClick)
* **[!UICONTROL Number of distinct clicks]** (@recipientClick)
* **[!UICONTROL Opt-Out]** (@optOut)
* **[!UICONTROL Errors]** (@error)

>[!NOTE]
>
>发送的数据是基于上次快照的 delta 值，可能会导致量度数据中出现负值。

发送的属性如下所示：

* **[!UICONTROL Internal name]** (@internalName)
* **[!UICONTROL Label]** (@label)
* **[!UICONTROL Label]** (operation/@label)：仅当安装了 **Campaign** 软件包时
* **[!UICONTROL Nature]** (operation/@nature)：仅当安装了 **Campaign** 软件包时
* **[!UICONTROL Tag 1]** (webAnalytics/@tag1)
* **[!UICONTROL Tag 2]** (webAnalytics/@tag2)
* **[!UICONTROL Tag 3]** (webAnalytics/@tag3)
* **[!UICONTROL Contact date]** (scheduling/@contactDate)

## 跟踪投放 {#tracking-deliveries-in-adobe-campaign}

为了让 Adobe Experience Cloud 能够在 Adobe Campaign 发送投放后跟踪网站上的活动，您需要在投放属性中引用匹配的连接器。要执行此操作，请应用以下步骤：

1. 打开要跟踪的营销活动的投放。

   ![](assets/webanalytics_delivery_properties_003.png)

1. 打开投放属性。
1. 转到 **[!UICONTROL Web Analytics]** 选项卡，然后选择之前创建的外部帐户。请参阅[在 Adobe Campaign 中配置外部帐户](#external-account-ac)。

   ![](assets/webanalytics_delivery_properties_002.png)

1. 您现在可以发送投放，并在 Adobe Analytics 中访问其报表。


**相关主题**

* [Campaign - Experience Cloud Triggers集成](ac-triggers.md)
