---
product: campaign
title: 读取列表
description: 了解有关读取列表工作流活动的更多信息
feature: Workflows, Targeting Activity
role: User, Data Engineer
exl-id: 91c87f8f-bdd2-4ca1-94c2-ec9e7affc1a0
source-git-commit: 28742db06b9ca78a4e952fcb0e066aa5ec344416
workflow-type: tm+mt
source-wordcount: '488'
ht-degree: 0%

---

# 读取列表{#read-list}

在工作流中处理的数据可以来自事先准备或结构化数据的列表（在之前分段或文件上传之后）。

此 **[!UICONTROL Read list]** 通过活动，您可以从工作流工作表中的列表复制数据，例如来自查询的数据。 然后，即可在整个工作流中访问它。

要处理的列表可以显式指定、由脚本计算或根据所选选项和中定义的参数进行动态本地化。 **[!UICONTROL Read list]** 活动。

![](assets/list_edit_select_option_01.png)

如果未显式指定该列表，则必须提供一个列表以用作模板来查找其结构。

![](assets/s_advuser_list_template_select.png)

配置列表选择后，您可以使用 **[!UICONTROL Edit query]** 用于为下一个工作流保留一部分群体的选项。

![](assets/wf_readlist_1.png)

>[!CAUTION]
>
>要在读取列表活动中创建过滤器，相关列表必须是“文件”类型。

可通过以下方式直接在Adobe Campaign中创建列表 **[!UICONTROL Profiles and Targets > Lists]** 主页的链接。 还可以在工作流中使用 **[!UICONTROL List update]** 活动。

**示例：排除发送地址列表**

以下示例允许您使用要从电子邮件投放目标中排除的电子邮件地址列表。

![](assets/s_advuser_list_read_sample_1.png)

中包含的配置文件 **新建联系人** 文件夹必须由投放操作定向。 要从目标中排除的电子邮件地址存储在外部列表中。 在我们的示例中，只有电子邮件地址上的信息才需要被排除。

1. 此 **新建联系人** 文件夹选择查询必须允许您加载所选用户档案的电子邮件地址，以便与列表中的信息保持一致。

   ![](assets/s_advuser_list_read_sample_0.png)

1. 在此，该列表存储在 **列表** 计算文件夹及其标签。

   ![](assets/s_advuser_list_read_sample_2.png)

1. 要从主目标中排除外部列表的电子邮件地址，必须配置排除活动并指定 **新建联系人** 文件夹中包含要保留的数据。 将从目标中删除此集与排除活动中任何其他集客集的联合数据。

   ![](assets/s_advuser_list_read_sample_3.png)

   排除规则在编辑工具的中心部分中配置。 单击 **[!UICONTROL Add]** 按钮来定义要应用的排除类型。

   您可以根据活动的传入过渡数量定义多个排除项。

1. 在 **[!UICONTROL Exclusion set]** 字段中，选择 **[!UICONTROL Read list]** 活动：将从主集中排除此活动中的数据。

   在本例中，我们在连接上有一个排除项：列表中包含的数据将通过包含电子邮件地址的字段与主集的数据进行协调。 要配置连接，请选择 **[!UICONTROL Joins]** 在 **[!UICONTROL Change dimension]** 字段。

   ![](assets/s_advuser_list_read_sample_4.png)

1. 然后，选择与两组（“源”和“目标”）中的电子邮件地址对应的字段。 随后将链接各列，并从目标中排除其电子邮件地址位于导入地址列表中的收件人。
