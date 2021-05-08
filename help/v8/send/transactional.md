---
solution: Campaign
product: Adobe Campaign
title: 活动 Transactional Messaging
description: 交易消息处理入门
feature: 概述
role: Data Engineer
level: Beginner
translation-type: tm+mt
source-git-commit: e068642c1bc5bf5f0329fc09f7ca6ddbd1683d6a
workflow-type: tm+mt
source-wordcount: '1480'
ht-degree: 1%

---

# Transactional messaging{#send-transactional-messages}入门

事务消息（消息中心）是用于管理触发消息的活动模块。 这些消息是从信息系统触发的事件生成的，可以是：例如，发票、订单确认、发运确认、密码更改、产品不可用通知、帐户对帐单或网站帐户创建。

:speech_balloon:作为“托管Cloud Services”用户，[联系Adobe](../start/support.md#support)以在您的环境中安装和配置活动事务消息。

事务性消息用于发送：

* 通知，例如订单确认或密码重置
* 对客户行为的个人实时响应
* 非促销内容

：灯泡：[本节](../config/transactional-msg-settings.md)中详细介绍了事务消息设置。

：灯泡：了解[本页](../dev/architecture.md)中的事务消息架构。

>[!CAUTION]
>
>交易消息传递需要特定许可证。 请检查您的许可协议。

## 定义事务性消息模板

每个事件都可触发个性化信息。 要实现此目的，您需要创建一个消息模板以匹配每个事件类型。 模板包含个性化事务性消息所需的信息。 您还可以使用模板来测试消息预览，并在传送到最终目标之前使用种子地址发送验证。

### 创建模板

要创建消息模板，请执行以下步骤：

1. 转到Adobe Campaign树中的&#x200B;**[!UICONTROL Message Center >Transactional message templates]**&#x200B;文件夹。
1. 在事务性消息模板列表中，右键单击并选择下拉菜单中的&#x200B;**[!UICONTROL New]** ，或单击事务性消息模板列表上方的&#x200B;**[!UICONTROL New]**&#x200B;按钮。

   ![](assets/messagecenter_create_model_001.png)

1. 在“投放”窗口中，选择适合要使用的渠道的投放模板。

   ![](assets/messagecenter_create_model_002.png)

1. 如有必要，更改其标签。
1. 选择与要发送的消息匹配的事件类型。

   ![](assets/messagecenter_create_model_003.png)

   事件类型必须在控制实例中由Adobe创建，以便Adobe Campaign处理。

   >[!NOTE]
   >
   >事件类型不应链接到多个模板。

1. 输入性质和说明，然后单击&#x200B;**[!UICONTROL Continue]**&#x200B;创建消息正文。 请参阅[创建消息内容](#create-message-content)。

   ![](assets/messagecenter_create_model_004.png)

### 创建内容{#create-message-content}

事务性消息内容的定义与Adobe Campaign中所有投放的定义相同。 例如，对于电子邮件投放，您可以创建HTML或文本格式的内容、添加附件或个性化投放对象。 如需详细信息，请参阅[此部分](../start/create-message.md)。

>[!CAUTION]
>
>邮件中包含的图像必须可以公开访问。 Adobe Campaign不为事务性消息提供任何图像上传机制。\
>与JSSP或webApp不同，`<%=`没有任何默认转义。
>
>您必须正确地从事件中逸出每个数据。 此转义取决于此字段的使用方式。 例如，在URL中，请使用encodeURIComponent。 要在HTML中显示，可以使用escapeXMLString。

定义消息内容后，您可以将事件信息集成到消息正文中并对其进行个性化设置。 事件信息通过个性化标记插入文本正文。

![](assets/messagecenter_create_content.png)

* 所有个性化字段都来自有效负荷。
* 可以在事务性消息中引用一个或多个个性化块。 块内容将在发布到投放期间添加到执行实例内容。

要在电子邮件正文中插入个性化标记，请应用以下步骤：

1. 在消息模板中，单击与电子邮件格式（HTML或文本）匹配的选项卡。
1. 输入消息的正文。
1. 在文本正文中，使用&#x200B;**[!UICONTROL Real time events>Event XML]**&#x200B;菜单插入标记。

   ![](assets/messagecenter_create_custo_1.png)

1. 使用以下语法填充标记：**元素名称**。如下所示，@**属性名称**。

   ![](assets/messagecenter_create_custo_2.png)

### 添加种子地址{#add-seeds}

种子地址允许您在发送消息之前显示消息的预览、发送验证和测试消息个性化。 种子地址链接到投放，不能用于其他投放。

1. 在事务性消息模板中，单击&#x200B;**[!UICONTROL Seed addresses]**&#x200B;选项卡。

   ![](assets/messagecenter_create_seed_1.png)

1. 为其分配一个标签，以便日后进行选择。

   ![](assets/messagecenter_create_seed_2.png)

1. 输入种子地址(根据通信渠道，使用电子邮件或移动电话)。

   ![](assets/messagecenter_create_seed_3.png)

1. 输入外部标识符:此可选字段允许您输入业务密钥（唯一ID、名称+电子邮件等） 这是您网站上所有用于识别您的用户档案的应用程序所通用的。 如果此字段也存在于Adobe Campaign营销数据库中，则您随后可以将事件与数据库中的用户档案进行协调。

   ![](assets/messagecenter_create_seed_4.png)

1. 插入测试数据。 请参阅[此小节](#personalization-data)。

   ![](assets/messagecenter_create_custo_3.png)

1. 单击&#x200B;**[!UICONTROL Add other seed addresses]**&#x200B;链接，然后单击&#x200B;**[!UICONTROL Add]**&#x200B;按钮。

   ![](assets/messagecenter_create_seed_5.png)

1. 重复此过程以创建所需数量的地址。

   ![](assets/messagecenter_create_seed_6.png)

创建地址后，您即可访问其预览和个性化。

### 添加个性化数据{#personalization-data}

您可以在消息模板中添加事务性消息以测试消息个性化。 这将允许您生成预览或发送验证。 如果安装&#x200B;**Deliverability**&#x200B;模块，则此数据允许您显示各种桌面、Web或移动客户端的消息呈现。

此数据的目的是在消息最终投放之前测试消息。 这些消息与消息中心要处理的实际数据不符。 但是，XML结构必须与存储在执行实例中的事件结构相同，如下所示。

![](assets/messagecenter_create_custo_4.png)

此信息使您能够使用个性化标记来个性化消息内容。

1. 在消息模板中，单击&#x200B;**[!UICONTROL Seed addresses]**&#x200B;选项卡。
1. 在事件内容中，输入XML格式的测试信息。

   ![](assets/messagecenter_create_custo_3.png)


### 查看事务性消息{#transactional-message-preview}

创建一个或多个种子地址和消息正文后，您可以预览消息并检查其个性化。

1. 在消息模板中，单击&#x200B;**[!UICONTROL Preview]**&#x200B;选项卡。

   ![](assets/messagecenter_preview_1.png)

1. 在下拉列表中选择&#x200B;**[!UICONTROL A seed address]**。

   ![](assets/messagecenter_preview_2.png)

1. 选择以前创建的种子地址以显示个性化消息。

   ![](assets/messagecenter_create_seed_7.png)

### 发送验证

可以通过将验证发送到先前创建的种子地址来测试消息投放。

发送验证与任何投放的过程相同。

:arrow_upper_right:了解有关[Campaign Classic文档]((https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html))中验证的更多信息

但是，要发送事务性消息的验证，您需要执行以下操作：

* 使用个性化测试数据创建一个或多个[种子地址](#add-seeds)
* 创建消息内容

要发送验证:

1. 单击“投放”窗口中的&#x200B;**[!UICONTROL Send a proof]**&#x200B;按钮。
1. 分析投放。
1. 更正所有错误并确认投放。

   ![](assets/messagecenter_send_proof_001.png)

1. 检查是否已将消息传送到种子地址，并且其内容符合您的配置。

   ![](assets/messagecenter_send_proof_002.png)

验证可通过&#x200B;**[!UICONTROL Audit]**&#x200B;选项卡在每个模板中访问。

![](assets/messagecenter_send_proof_003.png)

### 发布模板

在控制实例上创建的消息模板完成后，您可以发布该消息模板。 此过程还将发布到所有执行实例。

>[!NOTE]
>
>发布事务性消息模板时，类型规则也会自动发布到执行实例上。

“出版物”允许您在执行实例上自动创建两个消息模板，这允许您发送链接到实时消息和批次事件的消息。

>[!CAUTION]
>
>每次对模板进行任何更改时，请确保再次发布模板，以使这些更改在事务性消息投放期间生效。

1. 在控制实例上，转到树的&#x200B;**[!UICONTROL Message Center > Transactional message templates]**&#x200B;文件夹。
1. 选择要在执行实例上发布的模板。
1. 单击 **[!UICONTROL Publish]**。

   ![](assets/messagecenter_publish_template.png)

发布完成后，将在&#x200B;**[!UICONTROL Administration > Production > Message Center Execution> Default > Transactional message templates]**&#x200B;文件夹中生产实例树中创建要应用于批处理和实时类型事件的消息模板。

![](assets/messagecenter_deployed_model.png)

一旦发布了模板，如果触发了相应的事件,执行实例将接收事件，将其链接到事务模板，并将相应事务性消息发送到每个收件人。

>[!NOTE]
>
>如果将事务性消息模板的现有字段（如发送者地址）替换为空值，则执行实例上的相应字段在再次发布事务性消息后将不会更新。 它仍将包含上一个值。
>
>但是，如果添加非空值，则在下次发布后，将像往常一样更新相应的字段。


### 取消发布模板

在执行实例上发布消息模板后，即可取消发布该消息模板。

* 事实上，如果触发相应的事件，仍可以调用已发布的模板：如果您不再使用消息模板，建议取消发布该消息模板。 这是为了避免误发送不需要的事务性消息。

   例如，您发布了仅用于圣诞活动的消息模板。 在圣诞节结束后，您可能希望取消发布它，并在明年再次发布它。

* 此外，无法删除状态为&#x200B;**[!UICONTROL Published]**&#x200B;的事务性消息模板。 必须先取消发布。

要取消发布事务性消息模板，请执行以下步骤。

1. 在控制实例上，转到树的&#x200B;**[!UICONTROL Message Center > Transactional message templates]**&#x200B;文件夹。
1. 选择要取消发布的模板。
1. 单击 **[!UICONTROL Unpublish]**。
1. 单击 **[!UICONTROL Start]**。

![](assets/message-center-unpublish.png)

事务性消息模板状态从&#x200B;**[!UICONTROL Published]**&#x200B;变回&#x200B;**[!UICONTROL Being edited]**。

取消发布完成后：

* 这两个消息模板(应用于批处理和实时类型事件)都将从每个执行实例中删除。

   它们不再显示在&#x200B;**[!UICONTROL Administration > Production > Message Center Execution > Default > Transactional message templates]**&#x200B;文件夹中。

* 取消发布模板后，您可以从控制实例中删除它。

   要执行此操作，请从列表中选择它，然后单击屏幕右上方的&#x200B;**[!UICONTROL Delete]**&#x200B;按钮。
