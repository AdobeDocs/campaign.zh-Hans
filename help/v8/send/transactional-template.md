---
title: 创建并发布事务性消息传递模板
description: 了解如何创建和发布事务性消息传递模板
feature: Transactional Messaging
role: User
level: Beginner, Intermediate
exl-id: 858c9216-c5a0-4bf9-b4b0-91e403293f73
source-git-commit: a05b1d7d9b35f8d9189046fd4288d0b80f30967a
workflow-type: tm+mt
source-wordcount: '1177'
ht-degree: 1%

---

# 创建并发布事务性消息传递模板{#template-transactional-messages}

每个事件都可以触发个性化消息。 要做到这一点，您需要创建一个消息模板以匹配每个事件类型。 模板包含个性化事务型消息的必需信息。 您还可以使用模板测试消息预览，并在将消息交付到最终目标之前使用种子地址发送校样。

## 创建模板{#create-message-template}

要创建消息模板，请执行以下步骤：

1. 转到Adobe Campaign树中的&#x200B;**[!UICONTROL Message Center >Transactional message templates]**&#x200B;文件夹。
1. 在事务性消息模板列表中，右键单击并在下拉菜单中选择&#x200B;**[!UICONTROL New]**，或单击事务性消息模板列表上方的&#x200B;**[!UICONTROL New]**&#x200B;按钮。

   ![](assets/messagecenter_create_model_001.png)

1. 在投放窗口中，选择适用于要使用的渠道的投放模板。

   ![](assets/messagecenter_create_model_002.png)

1. 根据需要更改其标签。
1. 选择与要发送的消息匹配的事件类型。 必须预先创建预定由Adobe Campaign处理的事件类型。 [了解详情](../send/transactional.md#create-event-types)

   ![](assets/messagecenter_create_model_003.png)

   >[!CAUTION]
   >
   >事件类型不得链接到多个模板。

1. 输入性质和说明，然后单击&#x200B;**[!UICONTROL Continue]**&#x200B;以创建邮件正文。

## 创建内容{#create-message-content}

事务型消息内容的定义与Adobe Campaign中所有投放的定义相同。 例如，对于电子邮件投放，您可以创建HTML或文本格式的内容、添加附件或个性化投放对象。 [了解详情](../start/create-message.md)。

>[!CAUTION]
>
>消息中包含的图像必须可公开访问。 Adobe Campaign没有为事务性消息提供任何图像上传机制。\
>与JSSP或webApp不同，`<%=`没有任何默认转义。
>
>您必须正确对来自事件的每个数据进行转义。 此转义取决于此字段的使用方式。 例如，在URL中，请使用encodeURIComponent。 要显示在HTML中，您可以使用escapeXMLString。

定义消息内容后，您可以将事件信息集成到消息正文中并对其进行个性化。 由于个性化标记，事件信息将插入到文本正文中。

![](assets/messagecenter_create_content.png)

* 所有个性化字段都来自有效负载。
* 可以在事务型消息中引用一个或多个个性化块。<!--The block content will be added to the delivery content during the publication to the execution instance.-->

要在电子邮件正文中插入个性化标记，请应用以下步骤：

1. 在消息模板中，单击与电子邮件格式(HTML或文本)匹配的选项卡。
1. 输入消息正文。
1. 在文本正文中，使用&#x200B;**[!UICONTROL Real time events>Event XML]**&#x200B;菜单插入标记。

   ![](assets/messagecenter_create_custo_1.png)

1. 使用以下语法填写标记： **element name**。@**属性名称**，如下所示。

   ![](assets/messagecenter_create_custo_2.png)

## 测试事务性消息模板 {#test-message-template}

### 添加种子地址{#add-seeds}

利用种子地址，可显示消息预览、发送校样并在发送消息之前测试消息个性化。 种子地址已链接到投放，并且无法用于其他投放。

1. 在事务性消息模板中，单击&#x200B;**[!UICONTROL Seed addresses]**&#x200B;选项卡，然后单击&#x200B;**[!UICONTROL Add]**&#x200B;按钮。

   ![](assets/messagecenter_create_seed_1.png)

1. 为其分配标签以便稍后轻松选择，然后输入种子地址（电子邮件或移动电话，具体取决于通信渠道）。

1. 输入外部标识符：利用此可选字段，可输入您的网站上所有应用程序通用的业务键（唯一ID、姓名+电子邮件等），用于标识您的配置文件。 如果此字段也出现在Adobe Campaign营销数据库中，则之后可以将事件与数据库中的用户档案进行协调。

   ![](assets/messagecenter_create_seed_2.png)

1. 插入测试数据。 [请参阅Campaign Classic v7文档以了解有关个性化数据的更多信息](https://experienceleague.adobe.com/en/docs/campaign-classic/using/transactional-messaging/message-templates/testing-message-templates#personalization-datal){target="_blank"}

   ![](assets/messagecenter_create_custo_3.png)

1. 单击&#x200B;**[!UICONTROL Ok]**&#x200B;以确认创建种子地址。

1. 重复此过程，根据需要创建所需数量的地址。

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

创建一个或多个种子地址和消息正文后，您可以预览消息并检查其个性化。

1. 在消息模板中，单击&#x200B;**[!UICONTROL Preview]**&#x200B;选项卡，然后在下拉列表中选择&#x200B;**[!UICONTROL A seed address]**。

   ![](assets/messagecenter_preview_1.png)

1. 选择之前创建的种子地址以显示个性化消息。

   ![](assets/messagecenter_create_seed_7.png)

### 发送校样 {#send-proof}

您可以通过向之前创建的种子地址发送校样来测试消息投放。

发送验证的过程与发送任何投放的过程相同。

在[本节](../send/preview-and-proof.md#proofs-send)中了解有关校样的更多信息。

但是，要发送事务型消息的验证，您需要执行以下操作：

* 使用个性化测试数据创建一个或多个[种子地址](#add-seeds)
* 创建消息内容

要发送证明：

1. 单击投放窗口中的&#x200B;**[!UICONTROL Send a proof]**&#x200B;按钮。
1. 分析投放。
1. 更正任何错误并确认投放。

   ![](assets/messagecenter_send_proof_001.png)

1. 检查邮件是否已发送到种子地址，以及邮件内容是否符合您的配置。

   ![](assets/messagecenter_send_proof_002.png)

可通过&#x200B;**[!UICONTROL Audit]**&#x200B;选项卡访问每个模板中的验证。

![](assets/messagecenter_send_proof_003.png)

#### 从[!DNL Campaign Classic] v7过渡 {#transition-from-v7}

如果您[要从Campaign Classic v7](../start/v7-to-v8.md)进行过渡，则所有投放都将通过中间源(MID)服务器。

但是，在创建事务性消息模板时，成功使用该模板所需的路由是&#x200B;**内部电子邮件投放**。 此路由会阻止您发送校样。

因此，要为事务性消息模板发送验证，必须将路由从内部电子邮件投放更改为&#x200B;**中间源路由帐户**。

![](assets/messagecenter_send_proof_004.png)

发送校样后，必须先将路由更改回内部电子邮件投放，然后再发布事务型消息模板。

## 发布模板 {#publish-message-template}

创建消息模板<!-- on the control instance-->完成后，您可以发布该模板，从而发送链接到实时事件和批量事件的消息。

<!--This process will also publish it on all execution instances.

NOTE: When publishing transactional message templates, typology rules are also automatically published on the execution instances.

Publication lets you automatically create two message templates on the execution instances, which will allow you to send messages linked to real-time and batch events.-->

>[!CAUTION]
>
>无论何时对模板进行更改，请确保再次发布模板，以便这些更改在事务型消息投放期间生效。

1. 转到树的&#x200B;**[!UICONTROL Message Center > Transactional message templates]**&#x200B;文件夹。
1. 选择要发布的模板<!--on your execution instances-->。
1. 单击 **[!UICONTROL Publish]**。

   ![](assets/messagecenter_publish_template.png)

发布完成后，将在&#x200B;**[!UICONTROL Administration > Production > Message Center Execution> Default > Transactional message templates]**&#x200B;文件夹中创建要应用于批次和实时类型事件的消息模板。

![](assets/messagecenter_deployed_model.png)

发布模板后，如果触发了相应的事件，Adobe Campaign<!--execution instance-->将收到该事件，将其链接到事务型模板，并将相应的事务型消息发送给每个收件人。

<!--
>[!NOTE]
>
>If you replace an existing field of the transactional message template, such as the sender address, with an empty value, the corresponding field on the execution instance(s) will not be updated once the transactional message is published again. It will still contain the previous value.
>
>However, if you add a non-empty value, the corresponding field will be updated as usual after the next publication.
-->

## 取消发布模板

发布消息模板<!--on the execution instances-->后，可以取消发布该模板。

* 事实上，如果触发了相应的事件，仍可调用已发布的模板：如果您不再使用消息模板，则建议取消发布该模板。 这是为了避免错误地发送不需要的事务型消息。

  例如，您发布了一个消息模板，该模板仅用于圣诞节促销活动。 您可能需要在圣诞节结束后取消发布它，并在明年再次发布。

* 此外，您无法删除状态为&#x200B;**[!UICONTROL Published]**&#x200B;的事务性消息模板。 必须先取消发布它。

要取消发布事务型消息模板，请执行以下步骤。

1. 浏览到&#x200B;**[!UICONTROL Message Center > Transactional message templates]**&#x200B;文件夹。
1. 选择要取消发布的模板。
1. 单击 **[!UICONTROL Unpublish]**。
1. 单击 **[!UICONTROL Start]**。

![](assets/message-center-unpublish.png)

事务性消息模板状态从&#x200B;**[!UICONTROL Published]**&#x200B;变回&#x200B;**[!UICONTROL Being edited]**。

取消发布完成后：

* 两个消息模板（应用于批处理事件和实时类型事件）都已被删除<!-- from each execution instance-->。

  它们不再出现在&#x200B;**[!UICONTROL Administration > Production > Message Center Execution > Default > Transactional message templates]**&#x200B;文件夹中。

* 取消发布模板后，您可以将其删除<!-- from the control instance-->。

  要执行此操作，请从列表中选择它，然后单击屏幕右上角的&#x200B;**[!UICONTROL Delete]**&#x200B;按钮。
