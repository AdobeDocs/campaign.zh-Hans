---
title: 短信选择受众
description: 了解如何设置短信投放的受众
feature: SMS
role: User
level: Beginner, Intermediate
version: Campaign v8, Campaign Classic v7
exl-id: e0603a4d-cde1-4199-a164-bf0c992ba937
source-git-commit: a2efad26232cd380eea850a589b22b23928253e8
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 7%

---

# 选择短信投放的受众 {#sms-audience}

在选择受众之前，[请在此处](../../audiences/gs-audiences.md)了解有关受众的更多信息。

在大多数情况下，投放的主要目标会从Adobe Campaign数据库（默认模式）中提取。 但是，受众也可以存储在外部文件中。 [在此章节中了解详情](#external-audience)。

## Adobe Campaign中的受众

要选择投放的受众，请执行以下步骤：

1. 在投放编辑器中，单击&#x200B;**[!UICONTROL To]**&#x200B;链接。 您将打开一个&#x200B;**[!UICONTROL Select target]**&#x200B;窗口

1. 由于受众存储在Adobe Campaign数据库中，因此请在&#x200B;**[!UICONTROL Main target]**&#x200B;选项卡中选择&#x200B;**[!UICONTROL Defined in the database]**&#x200B;选项。

   ![](assets/audience_to.png){zoomable="yes"}

1. 在下拉列表中选择&#x200B;**[!UICONTROL Target mapping]**。 Adobe Campaign默认目标映射为收件人，基于&#x200B;**[!UICONTROL nms:recipient]**&#x200B;架构。

   可以使用其他目标映射，其中一些映射可能与您的特定配置相关。 有关目标映射的详细信息，请参阅[使用目标映射](../../audiences/target-mappings.md)。

1. 单击 **[!UICONTROL Add]** 按钮以定义限制筛选条件。

   然后，您可以选择要应用的筛选类型：

   ![](assets/audience_filters.png){zoomable="yes"}

   若要使用目标类型，请选择它并单击&#x200B;**[!UICONTROL Next]**&#x200B;按钮。

   以下是默认提供的目标类型：

   * **[!UICONTROL Filtering conditions]**：用于定义查询并显示结果。
   * **[!UICONTROL A list of recipients]**：允许您选择已准备的包含受众的列表
   * **[!UICONTROL A recipient]**：允许您在表中直接选择收件人。
   * **[!UICONTROL Recipients included in a folder]**：允许您在资源管理器导航树中选择文件夹
   * **[!UICONTROL Recipients of a delivery]**：允许您选择上次投放的受众
   * **[!UICONTROL Recipients of deliveries belonging to a folder]**：允许您选择给定文件夹中所有投放的受众
   * **[!UICONTROL Subscribers of an information service]**：通过此选项，可选择新闻稿，收件人必须订阅新闻稿才能成为所创建投放的目标。
   * **[!UICONTROL User filters]**：允许您使用预定义过滤器。

   利用选项&#x200B;**[!UICONTROL Exclude recipients from this segment]**，可定向不符合所定义的目标条件的收件人。 要使用此选项，请选择相应的框，然后按照之前所述应用目标选择，以排除生成的用户档案。

1. 在标签字段中输入受众的名称，然后单击&#x200B;**[!UICONTROL Finish]**&#x200B;按钮以验证受众。

   ![](assets/audience_finish.png){zoomable="yes"}

   再次单击&#x200B;**[!UICONTROL Add]**&#x200B;按钮后，您可以根据需要添加任意数量的目标群体。 您也可以通过单击标签后面的十字来删除某些标签。

## 外部文件中的受众 {#external-audience}

您可以使用Adobe Campaign对数据库中没有但在外部文件中存在的受众发送投放。

以下是相应的步骤：

1. 在投放编辑器中，单击&#x200B;**[!UICONTROL To]**&#x200B;链接。 您将打开一个&#x200B;**[!UICONTROL Select target]**&#x200B;窗口

1. 选择 **[!UICONTROL Defined in an external file]** 选项。

   ![](assets/audience_externalfile.png){zoomable="yes"}

1. 默认情况下，会在数据库中导入收件人。 在这种情况下，您需要选择&#x200B;**[!UICONTROL Target mapping]**。 有关目标映射的详细信息，请参阅[使用目标映射](../../audiences/target-mappings.md)。

   否则，您还可以选择&#x200B;**[!UICONTROL Do not import the recipients into the database]**。

1. 导入文件时，单击&#x200B;**[!UICONTROL File format definition…]**&#x200B;链接以选择和配置外部文件。

1. 单击&#x200B;**[!UICONTROL Finish]**&#x200B;按钮验证受众。
