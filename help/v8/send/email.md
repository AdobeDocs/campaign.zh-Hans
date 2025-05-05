---
title: 使用Adobe Campaign发送电子邮件
description: 在 Adobe Campaign 中开始使用电子邮件。将个性化的电子邮件发给目标人群。
feature: Email
role: User
level: Beginner
exl-id: 97dcd0e0-db5b-45a4-96af-817e49f6cb64
source-git-commit: 693b9d9d50d5e60061bd952090380382ebaf8df8
workflow-type: tm+mt
source-wordcount: '565'
ht-degree: 9%

---

# 设计和发送电子邮件

使用Adobe Campaign创建电子邮件投放，向目标群体发送个性化电子邮件。 [了解详情](../send/send.md)

>[!NOTE]
>
>若要创建引人入胜的单独定制电子邮件，请浏览至[Web用户界面](../start/campaign-ui.md#campaign-web-user-interface-ac-web-ui)。 Adobe Campaign附带电子邮件Designer，它是一个直观的拖放界面，允许您设计和优化每封电子邮件的所有内容。


了解在[此页面](../start/create-message.md)中创建和配置投放的关键步骤。

## 创建电子邮件投放

创建上下文相关的个性化电子邮件，使它们提供的体验与客户的其他体验保持一致。

![](assets/new-email-content.png)


在以下示例中，您将了解在Adobe Campaign中设计电子邮件投放的步骤，其中包含个性化数据、指向外部URL的链接以及指向镜像页面的链接。

1. **创建投放**

   要创建新投放，请浏览到&#x200B;**营销活动**&#x200B;选项卡，单击&#x200B;**投放**，然后单击现有投放列表上方的&#x200B;**创建**&#x200B;按钮。

   ![](assets/delivery_step_1.png)

1. **选择模板**

   选择投放模板，然后命名您的投放。 此名称仅对Adobe Campaign控制台的用户可见，收件人不可见，不过此标题将显示在投放列表中。 单击 **[!UICONTROL Continue]**。

   ![](assets/dce_delivery_model.png)

1. **导入您的内容**

   单击&#x200B;**Source**&#x200B;选项卡以粘贴您的HTML内容。

   ![](assets/paste-content.png)

   >[!NOTE]
   >
   >为避免性能问题，电子邮件中包含的图像不能超过100 KB。

1. **个性化您的消息**

   * 添加收件人的名字和姓氏

     要在消息内容中插入目标用户档案的名字和姓氏，请将光标置于要插入它们的位置，单击工具栏中的最后一个图标，然后单击&#x200B;**[!UICONTROL Include]**&#x200B;并选择&#x200B;**[!UICONTROL Greetings]**。

     ![](assets/include-greetings.png)

     浏览到预览选项卡，通过选择收件人来检查个性化。

     ![](assets/perso-check.png)

     在[本节](personalize.md)中了解有关个性化选项的更多信息。

   * 插入跟踪链接

     要通过图像或文本将投放收件人转至外部地址，请选择该地址并单击工具栏中的&#x200B;**[!UICONTROL Add a link]**&#x200B;图标。

     使用以下格式&#x200B;**https://www.myURL.com**&#x200B;在&#x200B;**URL**&#x200B;字段中输入链接的URL，然后确认。

     ![](assets/add-a-link.png)

   * 添加镜像页面

     若要允许收件人在Web浏览器中查看投放内容，请添加指向邮件的[镜像页面](mirror-page.md)的链接。

     将光标放在要插入此链接的位置，单击工具栏中的最后一个图标，然后单击&#x200B;**[!UICONTROL Include]**&#x200B;并选择&#x200B;**[!UICONTROL link to mirror page]**。

     在[本节](mirror-page.md#link-to-mirror-page)中了解有关管理镜像页面的更多信息。

1. 您可以为电子邮件定义其他参数，如将邮件副本发送到BBC地址、更改邮件格式、设置特定编码等。 可在[此部分](email-parameters.md)中了解详情。

1. 内容准备就绪后，单击&#x200B;**保存**：该内容现在将显示在&#x200B;**[!UICONTROL Campaigns > Deliveries]**&#x200B;选项卡的投放列表中。

您的第一个电子邮件投放已准备就绪。 您现在需要定义受众、验证投放并发送它。

在此[用例](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/load-delivery-content.html?lang=zh-Hans){target="_blank"}中了解如何创建工作流以导入电子邮件内容。

>[!MORELIKETHIS]
>
>* [创建投放](../start/create-message.md)
>* [创建并使用电子邮件模板](create-templates.md)
>* [选择电子邮件的受众](../audiences/gs-audiences.md)
>* [验证投放并发送校样](preview-and-proof.md)
>* [配置并发送投放](configure-and-send.md)
>* [投放最佳实践](../start/delivery-best-practices.md)

## 测试和验证电子邮件

Campaign提供了多种方法，可在将电子邮件发送给受众之前测试和验证电子邮件。 在[本节](../send/preview-and-proof.md)中了解如何预览和测试您的电子邮件内容。

您可以：

* [发送校样](preview-and-proof.md)
* [添加种子地址](../audiences/test-profiles.md)
* [检查投放分析日志](delivery-analysis.md)

