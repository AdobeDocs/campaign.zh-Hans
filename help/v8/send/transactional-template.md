---
title: 创建并发布事务型消息传递模板
description: 了解如何创建和发布事务型消息传送模板
feature: Transactional Messaging
role: User
level: Beginner, Intermediate
source-git-commit: c61f03252c7cae72ba0426d6edcb839950267c0a
workflow-type: tm+mt
source-wordcount: '1088'
ht-degree: 1%

---

# 创建并发布事务型消息传递模板{#template-transactional-messages}

每个事件都可触发个性化消息。 要实现此目的，您需要创建一个消息模板以匹配每个事件类型。 模板包含个性化事务型消息的必需信息。 您还可以使用模板来测试消息预览，并在将消息投放到最终目标之前使用种子地址发送校样。

## 创建模板{#create-message-template}

要创建消息模板，请执行以下步骤：

1. 转到 **[!UICONTROL Message Center >Transactional message templates]** 文件夹。
1. 在事务型消息模板列表中，右键单击并选择 **[!UICONTROL New]** 中，或单击 **[!UICONTROL New]** 按钮。

   ![](assets/messagecenter_create_model_001.png)

1. 在投放窗口中，选择适合您要使用的渠道的投放模板。

   ![](assets/messagecenter_create_model_002.png)

1. 如有必要，请更改其标签。
1. 选择与要发送的消息匹配的事件类型。 必须事先创建要由Adobe Campaign处理的事件类型。 [了解详情](#create-event-types)

   ![](assets/messagecenter_create_model_003.png)

   >[!CAUTION]
   >
   >事件类型绝不应链接到多个模板。

1. 输入性质和描述，然后单击 **[!UICONTROL Continue]** 创建消息正文。

## 创建内容{#create-message-content}

事务型消息内容的定义与Adobe Campaign中所有投放的定义相同。 例如，对于电子邮件投放，您可以创建HTML或文本格式的内容、添加附件或个性化投放对象。 [了解详情](../start/create-message.md)。

>[!CAUTION]
>
>消息中包含的图像必须可以公开访问。 Adobe Campaign不为事务型消息提供任何图像上传机制。\
>与JSSP或webApp不同， `<%=` 没有任何默认转义。
>
>您必须正确转义来自事件的每个数据。 此转义取决于此字段的使用方式。 例如，在URL中，请使用encodeURIComponent。 要在HTML中显示，可以使用escXMLString。

定义消息内容后，您可以将事件信息集成到消息正文中并对其进行个性化。 由于个性化标记，事件信息会插入到文本正文中。

![](assets/messagecenter_create_content.png)

* 所有个性化字段都来自有效负载。
* 可以在事务型消息中引用一个或多个个性化块。 <!--The block content will be added to the delivery content during the publication to the execution instance.-->

要将个性化标记插入电子邮件正文，请应用以下步骤：

1. 在消息模板中，单击与电子邮件格式(HTML或文本)匹配的选项卡。
1. 输入消息的正文。
1. 在文本的正文中，使用 **[!UICONTROL Real time events>Event XML]** 菜单。

   ![](assets/messagecenter_create_custo_1.png)

1. 使用以下语法填写标记： **元素名称**.@**属性名称** 如下所示。

   ![](assets/messagecenter_create_custo_2.png)

## 测试事务型消息模板 {#test-message-template}

### 添加种子地址{#add-seeds}

种子地址允许您在发送消息之前显示消息预览、发送校样并测试消息个性化。 种子地址已链接到投放，无法用于其他投放。

1. 在事务型消息模板中，单击 **[!UICONTROL Seed addresses]** ，然后单击 **[!UICONTROL Add]** 按钮。

   ![](assets/messagecenter_create_seed_1.png)

1. 为其分配标签以供稍后选择，然后输入种子地址（电子邮件或手机，具体取决于通信渠道）。

1. 输入外部标识符：此可选字段允许您输入业务键（唯一ID、名称+电子邮件等） 网站上所有用于标识用户档案的应用程序都通用的配置文件。 如果此字段也存在于Adobe Campaign营销数据库中，则可以将事件与数据库中的用户档案进行协调。

   ![](assets/messagecenter_create_seed_2.png)

1. 插入测试数据。 请参阅[此小节](#personalization-data)。

   ![](assets/messagecenter_create_custo_3.png)

1. 单击 **[!UICONTROL Ok]** 确认创建种子地址。

1. 重复该过程以根据需要创建任意数量的地址。

   ![](assets/messagecenter_create_seed_6.png)

创建地址后，即可访问其预览和个性化。

<!--

### Add personalization data{#personalization-data}

You can add data in the message template to test transactional message personalization. This will allow you to generate a preview or send a proof. If you install the **Deliverability** module, this data allows you to display a rendering of the messages for various desktop, web or mobile clients.

The purpose of this data is to test your messages before their final delivery. These messages do not coincide with actual data to be processed by Message Center.

However, the XML structure must be identical to that of the event stored in the execution instance, as shown below. 

![](assets/messagecenter_create_custo_4.png)

This information enables you to personalize message content using personalization tags.

1. In the message template, click the **[!UICONTROL Seed addresses]** tab.
1. In the event content, enter the test information in XML format.

   ![](assets/messagecenter_create_custo_3.png)
-->

### 预览事务型消息{#transactional-message-preview}

创建一个或多个种子地址和消息正文后，即可预览消息并检查其个性化。

1. 在消息模板中，单击 **[!UICONTROL Preview]** 选项卡，然后选择 **[!UICONTROL A seed address]** 中。

   ![](assets/messagecenter_preview_1.png)

1. 选择之前创建的种子地址以显示个性化消息。

   ![](assets/messagecenter_create_seed_7.png)

### 发送验证

您可以通过向之前创建的种子地址发送校样来测试消息投放。

发送校样的过程与任何投放的过程相同。

![](../assets/do-not-localize/book.png) 在中了解有关校样的更多信息 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html#sending-a-proof){target="_blank"}

但是，要发送事务型消息的校样，您需要执行以下操作：

* 创建一个或多个 [种子地址](#add-seeds) 使用个性化测试数据
* 创建消息内容

要发送校样，请执行以下操作：

1. 单击 **[!UICONTROL Send a proof]** 按钮。
1. 分析投放。
1. 更正任何错误并确认投放。

   ![](assets/messagecenter_send_proof_001.png)

1. 检查消息是否已发送到种子地址，且其内容符合您的配置。

   ![](assets/messagecenter_send_proof_002.png)

可通过 **[!UICONTROL Audit]** 选项卡。

![](assets/messagecenter_send_proof_003.png)

## 发布模板 {#publish-message-template}

创建消息模板时<!-- on the control instance--> 完成后，您可以发布它，以便发送链接到实时事件和批量事件的消息。

<!--This process will also publish it on all execution instances.

NOTE: When publishing transactional message templates, typology rules are also automatically published on the execution instances.

Publication lets you automatically create two message templates on the execution instances, which will allow you to send messages linked to real-time and batch events.-->

>[!CAUTION]
>
>每当对模板进行任何更改时，请确保再次发布该模板，以便这些更改在事务型消息投放期间生效。

1. 转到 **[!UICONTROL Message Center > Transactional message templates]** 文件夹。
1. 选择要发布的模板<!--on your execution instances-->.
1. 单击 **[!UICONTROL Publish]**。

   ![](assets/messagecenter_publish_template.png)

发布完成后，将在 **[!UICONTROL Administration > Production > Message Center Execution> Default > Transactional message templates]** 文件夹。

![](assets/messagecenter_deployed_model.png)

发布模板后，如果触发了相应的事件，则Adobe Campaign<!--execution instance--> 将接收事件，将其链接到事务型模板，并向每个收件人发送相应的事务型消息。

<!--
>[!NOTE]
>
>If you replace an existing field of the transactional message template, such as the sender address, with an empty value, the corresponding field on the execution instance(s) will not be updated once the transactional message is published again. It will still contain the previous value.
>
>However, if you add a non-empty value, the corresponding field will be updated as usual after the next publication.
-->

## 取消发布模板

发布消息模板后 <!--on the execution instances-->，则可以取消发布该内容。

* 事实上，如果触发了相应的事件，则仍可以调用已发布的模板：如果您不再使用消息模板，建议取消发布该模板。 这是为了避免错误地发送不需要的事务型消息。

   例如，您发布了一个仅用于圣诞促销活动的消息模板。 在圣诞节结束后，您可能想要取消发布它，并在明年再次发布它。

* 此外，您还无法删除具有 **[!UICONTROL Published]** 状态。 必须先取消发布它。

要取消发布事务型消息模板，请执行以下步骤。

1. 浏览到 **[!UICONTROL Message Center > Transactional message templates]** 文件夹。
1. 选择要取消发布的模板。
1. 单击 **[!UICONTROL Unpublish]**。
1. 单击 **[!UICONTROL Start]**。

![](assets/message-center-unpublish.png)

事务型消息模板状态从 **[!UICONTROL Published]** to **[!UICONTROL Being edited]**.

取消发布完成后：

* 消息模板（应用于批处理和实时类型事件）都将被删除<!-- from each execution instance-->.

   它们不再显示在 **[!UICONTROL Administration > Production > Message Center Execution > Default > Transactional message templates]** 文件夹。

* 取消发布模板后，您可以将其删除<!-- from the control instance-->.

   要执行此操作，请从列表中选择它，然后单击 **[!UICONTROL Delete]** 按钮。