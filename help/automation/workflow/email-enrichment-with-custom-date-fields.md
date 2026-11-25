---
product: campaign
title: 具有自定义日期字段的电子邮件扩充
description: 了解如何使用自定义日期字段丰富电子邮件
feature: Workflows
role: User, Developer
version: Campaign v8, Campaign Classic v7
exl-id: 2bb3443c-37d8-4d49-9be1-81217f56823c
TQID: 'https://experienceleague.adobe.com/Mgo8JMtAXLW86GgkEsoVTtMSfUUKPsp-G9lL0p9JBg8'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
source-git-commit: e13b3537d149f2bdad7e9dd66768837e5c4b595b
workflow-type: tm+mt
source-wordcount: '790'
ht-degree: 2%
---
# 具有自定义日期字段的电子邮件扩充{#email-enrichment-with-custom-date-fields}



在本例中，我们希望向本月即将过生日的收件人发送一封包含自定义数据字段的电子邮件。 电子邮件将包含优惠券，有效期限为他们生日前后一周。

我们需要通过&#x200B;**[!UICONTROL Split]**&#x200B;活动定位本月将庆祝其生日的列表中的收件人。 然后，使用&#x200B;**[!UICONTROL Enrichment]**&#x200B;活动，自定义数据字段将用作客户特殊优惠的电子邮件中的有效日期。

![工作流：列表读取，拆分为子集后进行扩充，然后进行电子邮件发送，最后进行补充以结束。](assets/uc_enrichment.png)

要创建此示例，请应用以下步骤：

1. 在营销活动的&#x200B;**[!UICONTROL Targeting and workflows]**&#x200B;选项卡中，拖放&#x200B;**[!UICONTROL Read list]**&#x200B;活动以定向收件人列表。
1. 要处理的列表可以显式指定、由脚本计算或根据此处定义的选项和参数进行动态本地化。

   ![读取具有显式指定的列表和Source筛选节的列表活动。](assets/uc_enrichment_1.png)

1. 添加&#x200B;**[!UICONTROL Split]**&#x200B;活动以将本月即将过生日的收件人与其他收件人区分开来。
1. 要拆分列表，请在&#x200B;**[!UICONTROL Filtering of selected records]**&#x200B;类别中选择&#x200B;**[!UICONTROL Add a filtering condition on the inbound population]**。 然后，单击&#x200B;**[!UICONTROL Edit]**。

   ![拆分子集选项卡，其中对集客群体添加筛选条件并突出显示编辑链接。](assets/uc_enrichment_2.png)

1. 然后，Select **[!UICONTROL Filtering conditions]**&#x200B;单击“**[!UICONTROL Edit expression]**”按钮以筛选收件人生日的月份。

   ![在“表达式”字段旁边高亮显示“编辑表达式”按钮的目标元素窗口。](assets/uc_enrichment_3.png)

1. 单击&#x200B;**[!UICONTROL Advanced Selection]**，然后单击&#x200B;**[!UICONTROL Edit the formula using an expression]**&#x200B;并添加以下表达式： Month(@birthDate)。
1. 在&#x200B;**[!UICONTROL Operator]**&#x200B;列中选择&#x200B;**[!UICONTROL equal to]**。
1. 通过添加当前日期的&#x200B;**[!UICONTROL Value]**&#x200B;个月进一步筛选条件： Month(GetDate())。

   这将查询其生日月份对应于当月的收件人。

   ![目标元素条件：出生日期月份等于当前日期月份加14天。](assets/uc_enrichment_4.png)

1. 单击 **[!UICONTROL Finish]**。 然后，在&#x200B;**[!UICONTROL Split]**&#x200B;活动的&#x200B;**[!UICONTROL General]**&#x200B;选项卡中，单击&#x200B;**[!UICONTROL Results]**&#x200B;类别中的&#x200B;**[!UICONTROL Generate complement]**。

   利用&#x200B;**[!UICONTROL Complement]**&#x200B;结果，您可以添加投放活动或更新列表。 此处，我们刚刚添加了一个&#x200B;**[!UICONTROL End]**&#x200B;活动。

   ![在“结果”节中选中“生成补码”选项的情况下拆分“常规”选项卡。](assets/uc_enrichment_6.png)

您现在需要配置&#x200B;**[!UICONTROL Enrichment]**&#x200B;活动：

1. 在子集后添加&#x200B;**[!UICONTROL Enrichment]**&#x200B;活动以添加自定义日期字段。

   ![具有扩充活动的工作流已添加到拆分活动的子集过渡中。](assets/uc_enrichment_7.png)

1. 打开您的&#x200B;**[!UICONTROL Enrichment]**&#x200B;活动。 在&#x200B;**[!UICONTROL Complementary information]**&#x200B;类别中，单击&#x200B;**[!UICONTROL Add data]**。

   ![在“补充信息”部分中突出显示“添加数据”链接的扩充活动。](assets/uc_enrichment_8.png)

1. Select **[!UICONTROL Data linked to the filtering dimension]**，然后&#x200B;**[!UICONTROL Data of the filtering dimension]**。
1. 单击 **[!UICONTROL Add]** 按钮。

   ![要添加的数据，该窗口在“输出列”列表旁边突出显示“添加”按钮。](assets/uc_enrichment_9.png)

1. 添加&#x200B;**[!UICONTROL Label]**。 然后，在&#x200B;**[!UICONTROL Expression]**&#x200B;列中单击&#x200B;**[!UICONTROL Edit expression]**。

   ![输出在“表达式”列中突出显示Birthdate标签和“编辑表达式”按钮的列。](assets/uc_enrichment_10.png)

1. 首先，我们需要将出生日期之前的一周作为&#x200B;**有效开始日期**，并设置以下&#x200B;**[!UICONTROL Expression]**： `SubDays([target/@birthDate], 7)`。

   ![输出带有Birthdate标签和表达式Date of birth (target/@birthDate)的列。](assets/uc_enrichment_11.png)

1. 然后，要创建以出生日期后的一周为目标的自定义日期字段&#x200B;**有效期结束日期**，您需要添加&#x200B;**[!UICONTROL Expression]**： `AddDays([target/@birthDate], 7)`。

   您可以在表达式中添加标签。

   ![输出列有Birthdate和Validity start date列及其表达式和别名的列。](assets/uc_enrichment_12.png)

1. 单击 **[!UICONTROL Ok]**。 您的扩充现已准备就绪。

在您的&#x200B;**[!UICONTROL Enrichment]**&#x200B;活动后，您可以添加投放。 在本例中，我们添加了电子邮件投放，以向收件人发送包含有效日期的特殊优惠，供本月庆祝其生日的客户使用。

1. 将&#x200B;**[!UICONTROL Email delivery]**&#x200B;活动拖放到您的&#x200B;**[!UICONTROL Enrichment]**&#x200B;活动之后。

   ![在扩充活动后添加了电子邮件投放活动的工作流。](assets/uc_enrichment_15.png)

1. 双击您的&#x200B;**[!UICONTROL Email delivery]**&#x200B;活动以开始个性化您的投放。
1. 向投放添加&#x200B;**[!UICONTROL Label]**&#x200B;并单击&#x200B;**[!UICONTROL Continue]**。
1. 单击&#x200B;**[!UICONTROL Save]**&#x200B;以创建您的电子邮件投放。
1. 在电子邮件投放&#x200B;**[!UICONTROL Properties]**&#x200B;的&#x200B;**[!UICONTROL Approval]**&#x200B;选项卡中签入&#x200B;**[!UICONTROL Confirm delivery before sending option]**&#x200B;是否已选中。

   然后，启动工作流以使用定向信息扩充叫客过渡。

   ![发送前检查传递的“传递属性审批”选项卡。](assets/uc_enrichment_18.png)

您现在可以使用在&#x200B;**[!UICONTROL Enrichment]**&#x200B;活动中创建的自定义日期字段开始设计电子邮件投放。

1. 双击您的&#x200B;**[!UICONTROL Email delivery]**&#x200B;活动。
1. 将您的Target扩展添加到电子邮件中。 它应位于以下表达式内，以便配置有效日期的格式：

   ```
   <%=
           formatDate(targetData.alias of your expression,"%2D.%2M")  %>
   ```

1. 单击带有下拉箭头的![Personalization工具栏按钮。](assets/uc_enrichment_16.png)。Select **[!UICONTROL Target extension]**&#x200B;将先前创建的自定义有效期与&#x200B;**[!UICONTROL Enrichment]**&#x200B;活动一起使用，以将您的扩展添加到formatDate表达式中。

   ![Personalization菜单Target扩展子菜单，其中列出了有效期开始日期和有效期结束日期。](assets/uc_enrichment_19.png)

1. 根据需要配置电子邮件内容。

   ![使用targetData字段发送带有formatDate表达式且有效期为](assets/uc_enrichment_17.png)的HTML内容的电子邮件。

1. 预览电子邮件以检查自定义日期字段是否已正确配置

   ![电子邮件预览选项卡显示填写了有效期为12/20到01/03的生日消息。](assets/uc_enrichment_20.png)

您的电子邮件现已准备就绪。 您可以开始发送校样并确认您的投放以发送生日电子邮件。
