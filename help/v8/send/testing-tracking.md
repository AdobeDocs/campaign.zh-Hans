---
title: 测试消息跟踪
description: 了解如何在发送投放之前测试消息跟踪
feature: Monitoring
role: User
level: Beginner
exl-id: 16ad36b7-c13e-4b77-86ca-41c9ef174172
source-git-commit: edbe7ab49a628436dfb4d27ae17122917d7371e9
workflow-type: tm+mt
source-wordcount: '626'
ht-degree: 1%

---

# 测试消息跟踪 {#testing-tracking}

在将投放发送到整个受众之前，必须测试跟踪功能，以确保所有链接正确工作并正确捕获跟踪数据。 此验证流程可帮助您在营销活动正式推出之前识别并修复任何跟踪问题，防止出现链接重定向、跟踪像素加载或数据收集的潜在问题。

测试跟踪允许您：

* 验证消息中的所有链接是否受到正确跟踪并正确重定向
* 确认镜像页面链接有效并已跟踪
* 请确保为打开跟踪正确加载跟踪像素
* 检查是否准确捕获URL中的个性化参数
* 验证跟踪技术工作流是否正确处理数据

您可以按照以下步骤测试对镜像页面、电子邮件日志和链接的跟踪：

## 步骤1：创建测试投放 {#create-test-delivery}

1. 创建新的电子邮件投放以用于测试。 [了解如何创建投放](../start/create-message.md)
1. 设计包含要跟踪的链接的电子邮件内容。 [了解电子邮件内容设计](defining-the-email-content.md)
1. 在电子邮件内容中添加镜像页面个性化块。 [了解个性化块](personalization-blocks.md)

   ![](assets/mirror-page-insert.png)

1. 指定将接收电子邮件的用户。 由于此用户必须打开电子邮件并单击它包含的链接，因此请确保选择您控制的测试收件人地址。 [了解测试用户档案](../audiences/test-profiles.md)

## 步骤2：发送测试投放 {#send-test}

1. 确认在投放设置中启用了跟踪：
   * 打开投放的&#x200B;**[!UICONTROL Properties]**
   * 转到&#x200B;**[!UICONTROL Tracking & Images]**&#x200B;部分
   * 确保选中&#x200B;**[!UICONTROL Activate tracking]**
   * 如果要跟踪打开次数，请确保已选中&#x200B;**[!UICONTROL Opens tracking]**

   ![](assets/s_ncs_user_email_del_tracking_param.png)

[了解有关URL跟踪选项的更多信息](url-tracking.md)

1. 将投放发送给测试收件人。 [了解如何发送投放](configure-and-send.md)

## 步骤3：验证跟踪功能 {#verify-tracking}

1. 收到电子邮件后，打开它并单击镜像页面链接。 [了解镜像页面](mirror-page.md)
1. 单击电子邮件中的各种链接以生成跟踪数据。
1. 正确重定向到镜像页面后，访问&#x200B;**[!UICONTROL Administration > Production > Technical workflows]**&#x200B;文件夹。 [了解工作流](../config/workflows.md)
1. 打开&#x200B;**[!UICONTROL Tracking]**&#x200B;工作流。
1. 启动工作流，或右键单击&#x200B;**[!UICONTROL Scheduler]**&#x200B;活动并选择&#x200B;**[!UICONTROL Execute pending task now]**。
1. 请等待大约30秒，工作流才能处理跟踪日志。
1. 选择工作流的&#x200B;**[!UICONTROL Audit]**&#x200B;选项卡。 确保至少找到一个跟踪日志记录。 如果您没有看到任何新日志，请单击&#x200B;**[!UICONTROL Refresh]**。

1. 验证投放中的跟踪日志：
   * 返回您的投放
   * 选择&#x200B;**[!UICONTROL Tracking]**&#x200B;选项卡
   * 检查跟踪日志的列表是否随单击URL和其他跟踪事件一起显示

   ![](assets/s_ncs_user_delivery_tracking_tab.png)

## 步骤4：检查收件人跟踪选项卡 {#check-recipient-tracking}

1. 转到用于测试的收件人的用户档案页面。 [了解查看用户档案](../audiences/view-profiles.md)
   * 默认情况下，收件人的配置文件页面位于&#x200B;**[!UICONTROL Profiles and Targets > Recipients]**&#x200B;文件夹中。

1. 选择 **[!UICONTROL Tracking]** 选项卡。[了解有关跟踪日志的详细信息](tracking-logs.md)

   ![](assets/s_ncs_user_select_tracking_tab_from_recipient.png)

1. 验证跟踪记录是否与以下内容一起显示：
   * **[!UICONTROL Mirror Page]**&#x200B;列中的&#x200B;**[!UICONTROL Type]**&#x200B;值
   * 电子邮件打开次数的&#x200B;**[!UICONTROL Open]**&#x200B;列中的&#x200B;**[!UICONTROL Type]**&#x200B;值
   * **[!UICONTROL Email click]**&#x200B;列中的&#x200B;**[!UICONTROL Type]**&#x200B;值表示链接点击次数

## 跟踪测试疑难解答 {#troubleshooting-tracking-test}

如果未显示跟踪日志：

1. **检查投放设置**：转到投放并访问其&#x200B;**[!UICONTROL Properties]**&#x200B;以确保同时选中&#x200B;**[!UICONTROL Activate tracking]**&#x200B;和&#x200B;**[!UICONTROL Opens tracking]**&#x200B;选项。 [了解有关URL跟踪选项的更多信息](url-tracking.md)

1. **验证跟踪工作流**：确保&#x200B;**[!UICONTROL Tracking]**&#x200B;技术工作流运行无错误。 [了解跟踪工作流疑难解答](tracking-logs.md#check-tracking-workflow)

1. **检查URL格式**：验证URL的格式是否正确，是否用分隔符括起来。 [了解有关配置跟踪链接的更多信息](tracked-links.md)

1. **查看电子邮件客户端行为**：某些电子邮件客户端可能会阻止跟踪像素或修改链接。 尝试使用不同的电子邮件客户端进行测试。 [了解投放最佳实践](../start/delivery-best-practices.md)

1. **等待处理**：默认情况下，跟踪工作流每小时运行一次。 如果手动触发，请在检查结果之前留出足够的处理时间。 [了解有关跟踪日志的详细信息](tracking-logs.md)

## 相关主题 {#related-topics}

* [了解如何配置跟踪的链接](tracked-links.md)
* [了解如何访问跟踪日志](tracking-logs.md)
* [了解跟踪报表](../reporting/delivery-reports.md#tracking-indicators)

