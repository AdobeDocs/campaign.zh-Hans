---
title: 在Adobe Campaign中创建过滤器
description: 了解如何在Campaign中过滤数据和保存过滤器
feature: Audiences, Profiles
role: Data Engineer
level: Beginner
exl-id: 873578f6-6af9-4d0c-8df3-cce320fc6a4e
source-git-commit: 9c5c5e825294bd39742ecbd07b98a90b4555c138
workflow-type: tm+mt
source-wordcount: '1667'
ht-degree: 0%

---

# 创建和管理过滤器{#create-filters}

数据过滤是指选择数据集中较小部分（仅那些符合特定条件的记录），然后将该子集用于特定操作（更新、受众创建）或分析的过程。

从 **[!UICONTROL Explorer]**，则数据会显示在列表中。 您可以使用现有的内置过滤器访问此数据的特定子集：隔离的地址、未定向的收件人、特定的年龄范围或创建日期等。

您还可以创建自己的过滤器、保存它们以供将来使用或与其他Campaign用户共享。

过滤器配置允许您从列表中选择数据 **[!UICONTROL dynamically]**:修改数据时，会更新过滤的数据。

>[!NOTE]
>
>用户界面配置设置在设备级别本地定义。 有时可能需要清理此数据，尤其是在刷新数据时出现问题时。 为此，请使用 **[!UICONTROL File > Clear the local cache]** 菜单。

Adobe Campaign中提供了以下类型的过滤器：

## 预定义过滤器{#predefined-filters}

预定义过滤器可从 **过滤器** 按钮。

例如，对于用户档案，可以使用以下内置过滤器：

![](assets/built-in-filters.png)

您可以在 **[!UICONTROL Profiles and Targets > Pre-defined filters]** 节点。

>[!NOTE]
>
>对于所有其他数据列表，预定义过滤器存储在  **[!UICONTROL Administration > Configuration > Predefined filters]** 节点。

选择过滤器以显示其定义。

![](assets/predefined-filter-list.png)

使用最后一个选项卡预览过滤的数据。

![](assets/built-in-filter-preview.png)


内置的预定义过滤器包括：

<table> 
 <tbody> 
  <tr> 
   <td> <strong>标签</strong><br /> </td> 
   <td> <strong>查询</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> 已打开<br /> </td> 
   <td> 选择已打开投放的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已打开但未单击<br /> </td> 
   <td> 选择已打开投放但未单击链接的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 不活动的收件人<br /> </td> 
   <td> 选择X个月内未打开投放的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 上次按设备类型划分的活动<br /> </td> 
   <td> 选择在最近Z天内使用设备X单击或打开投放Y的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 按设备类型划分的上次活动（跟踪）<br /> </td> 
   <td> 选择在最近Z天内使用设备X单击或打开投放Y的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 未定向的收件人<br /> </td> 
   <td> 选择在X个月内从未通过渠道Y定向的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 非常活跃的收件人<br /> </td> 
   <td> 选择在过去Y个月内点击投放至少X次的收件人。<br /> </td> 
  </tr> 
  <tr> 
 <td> 列入阻止列表电子邮件地址<br /> </td> 
    <td> 选择电子邮件地址在上的收阻止列表件人。<br/> </td>
  </tr> 
  <tr> 
   <td> 隔离的电子邮件地址<br /> </td> 
   <td> 选择其电子邮件地址被隔离的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 文件夹中的电子邮件地址重复<br /> </td> 
   <td> 选择文件夹中电子邮件地址重复的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 未打开或单击<br /> </td> 
   <td> 选择未打开投放或已单击投放的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 新收件人（天）<br /> </td> 
   <td> 选择在最近X天内创建的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 新收件人（分钟）<br /> </td> 
   <td> 选择在最近X分钟内创建的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 新收件人（月）<br /> </td> 
   <td> 选择过去X个月中创建的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 通过订阅<br /> </td> 
   <td> 按订阅选择收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 通过单击特定链接<br /> </td> 
   <td> 选择单击投放中特定URL的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 按帖子投放行为<br /> </td> 
   <td> 在收到投放后，根据收件人的行为选择收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 按创建日期<br /> </td> 
   <td> 按创建日期，在从X个月（当前日期减n个月）到Y个月（当前日期减n个月）的期间内选择收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 按列表<br /> </td> 
   <td> 按列表选择收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 按点击次数<br /> </td> 
   <td> 选择最近X个月内单击投放的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 按收到的消息数<br /> </td> 
   <td> 根据收件人收到的消息数量选择收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 按打开数<br /> </td> 
   <td> 选择在Z时间段内在X和Y投放之间打开的收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 按名称或电子邮件<br /> </td> 
   <td> 根据收件人的姓名或电子邮件选择收件人。<br /> </td> 
  </tr> 
  <tr> 
   <td> 按年龄范围<br /> </td> 
   <td> 根据收件人的年龄选择收件人。<br /> </td> 
  </tr> 
 </tbody> 
</table>


### 默认过滤器{#default-filters}

每个列表上方的字段允许您使用 **预定义默认过滤器** 列表。 对于收件人列表，默认情况下可以根据名称和电子邮件地址进行筛选。

![](assets/filter-recipient-name.png)


>[!NOTE]
>
>的 **%** 字符会替换任何字符串。 例如，输入 `%@gmail.com` 在“电子邮件”字段中，显示具有Gmail地址的所有用户档案。 输入 `%@L` 在“姓氏”字段中，显示所有姓氏为L的用户档案。

要更改收件人列表的默认过滤器，请浏览 **[!UICONTROL Profiles and Targets > Predefined filters]** 节点。

对于所有其他类型的数据，请通过 **[!UICONTROL Administration > Configuration > Predefined filters]** 节点。

应用以下步骤：

1. 选择您要默认使用的过滤器。
1. 单击 **[!UICONTROL Parameters]** 选项卡，选择 **[!UICONTROL Default filter for the associated document type]**.

   ![](assets/change-default-filter.png)

1. 取消选中当前默认预定义过滤器的相同选项。
1. 单击 **[!UICONTROL Save]** 以应用过滤器。
1. 浏览到Recipient文件夹，然后单击 **[!UICONTROL Remove this filter]** 图标：新的默认过滤器可用。
   ![](assets/updated-default-filter.png)


## 快速过滤器{#quick-filters}

使用和组合 **快速过滤器** 定义特定字段的过滤器。

添加后，快速过滤器字段会依次显示在数据列表上方。 它们可以相互独立地删除。

快速过滤器特定于每个运算符，并在每次运算符清除其客户端控制台的缓存时重新初始化。

如果需要重复使用过滤器，请创建 **高级过滤器** 然后保存它。 [了解详情](#advanced-filters)。

创建 **快速过滤器**，请按照以下步骤操作：

1. 右键单击要筛选的字段并选择 **[!UICONTROL Filter on this field]**.

   ![](assets/quick-filter-on-this-field.png)

   默认过滤器字段显示在列表上方。

   ![](assets/quick-filter-above-list.png)

1. 选择过滤器选项。
1. 如果需要，请使用过滤器右侧的灰色图标将其删除。
1. 您可以组合过滤器以优化过滤器。

   ![](assets/add-filter-above-the-list.png)


如果需要筛选表单中不可用的字段，请在列中筛选，然后筛选该列。 为此，

1. 单击 **[!UICONTROL Configure list]** 图标。

   ![](assets/configure-list.png)

1. 选择要显示的列（例如，收件人的年龄），然后单击 **确定**.

   ![](assets/add-age-column.png)

1. 右键单击 **年龄** 列，然后选择 **[!UICONTROL Filter on this column]**.

   ![](assets/age-filter-on-this-column.png)

   然后，您可以选择年龄筛选选项。 在页面上添加其他过滤器以定义范围。

   ![](assets/filter-on-age.png)

## 高级过滤器{#advanced-filters}

在 **高级过滤器**. 使用这些过滤器可创建复杂查询或数据查询的组合。 这些过滤器可以保存并与其他Campaign用户共享。

### 创建高级过滤器{#create-adv-filters}

创建 **高级过滤器**，请单击 **[!UICONTROL Filters]** 按钮，选择 **[!UICONTROL Advanced filter...]**.

![](assets/adv-filter.png)

您还可以右键单击数据列表并选择 **[!UICONTROL Advanced filter...]**.

定义筛选条件。 在以下示例中，您将筛选帐户号码不以NL开头的收件人以及居住在巴黎或洛杉矶的收件人。

1. 单击 **[!UICONTROL Edit expression]** 图标 **[!UICONTROL Expression]** 列。

   ![](assets/edit-exp.png)

1. 选择要筛选的字段。
1. 从下拉列表中选择要应用的运算符。

   ![](assets/select-operator.png)

1. 从 **[!UICONTROL Value]** 列。 您可以组合多个过滤器来优化查询。 要添加过滤条件，请单击 **[!UICONTROL Add]**.

   ![](assets/add-an-exp.png)

   >[!NOTE]
   >
   >您可以为表达式分配层级，或使用工具栏箭头更改查询表达式的顺序。

1. 有三个运算符可用于组合表达式：  **和**, **或**, **除外**. 单击箭头以切换到 **或**.

   ![](assets/select-or-operator.png)

1. 单击 **[!UICONTROL Ok]** 创建过滤器并将其应用到当前列表。

应用的过滤器显示在列表上方。

![](assets/adv-filter-link.png)

要编辑或修改此过滤器，请在列表上方单击其描述链接（蓝色）。


### 保存高级过滤器{#save-adv-filters}

您可以将高级过滤器另存为  [预定义过滤器](#predefined-filters)，以便可重复使用它并与其他Campaign用户共享。

要保存高级过滤器，请执行以下步骤：

1. 单击过滤器的描述以对其进行编辑。
1. 单击 **[!UICONTROL Save as filter]** 图标。

   ![](assets/save-as-filter.png)

1. 输入此过滤器的名称并保存该过滤器。

   ![](assets/application-filter-save.png)

过滤器会添加到 [预定义过滤器](#predefined-filters). 可以从此节点更新。

![](assets/added-to-predefined-filters.png)

>[!NOTE]
>
>您可以为过滤器添加一个快捷键，以通过键盘激活它。



此过滤器也可从收件人列表的预定义过滤器中使用。

![](assets/access-to-new-predefined-filter.png)



### 使用过滤器定义区段 {#filter-as-segment}

您可以使用和组合过滤器来创建目标群体区段。

保存后，在 **[!UICONTROL User filters]** 中。

![](assets/adv-filter-target-type.png)


>[!NOTE]
>
>使用 **[!UICONTROL Exclude recipients from this segment]** 以仅定向与筛选条件不匹配的联系人。


### 使用函数构建高级过滤器{#use-functions-adv-filters}

要执行高级过滤功能，请使用函数定义过滤器的内容。 高级过滤器编辑器可利用Campaign查询编辑器的所有功能。

了解如何在Adobe Campaign Classic v7文档中构建高级查询。 例如：

* 了解如何根据 [Adobe Campaign Classic v7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/query.html?lang=en#example--targeting-on-simple-recipient-attributes){target=&quot;_blank&quot;}。
* 了解如何过滤过去7天内未联系的收件人(位于 [Adobe Campaign Classic v7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/querying-using-many-to-many-relationship.html){target=&quot;_blank&quot;}。
* 了解如何恢复可按 [Adobe Campaign Classic v7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/creating-a-filter.html){target=&quot;_blank&quot;}。
* 了解如何在  [Adobe Campaign Classic v7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/sending-a-birthday-email.html?lang=en#identifying-recipients-whose-birthday-it-is){target=&quot;_blank&quot;}。


### 预定义过滤器的高级参数 {#param-for-data-filters}

高级参数可用于预定义过滤器。 要访问这些页面，请浏览 **[!UICONTROL Parameters]** 选项卡。

* 要默认显示基于此文档类型的所有列表的过滤器，请选择 **[!UICONTROL Default filter for the associated document type]** 选项。

   例如， **[!UICONTROL By name or login]** 过滤器应用于运算符此选项处于选中状态，因此过滤器始终显示在所有运算符列表上。

* 要使过滤器对所有Campaign运算符可用，请选择  **[!UICONTROL Filter shared with other operators]** 选项。

* 要定义表单以选择筛选条件，请选择  **[!UICONTROL Use parameter entry form]** 选项。 必须在 **[!UICONTROL Form]** 选项卡。 例如，内置的预定义过滤器 **[!UICONTROL Recipients who have opened]**&#x200B;收件人列表中显示的过滤器字段允许您选择应用过滤器的投放。

![](assets/predefined-filters-parameters.png)


* 的 **[!UICONTROL Advanced parameters]** 链接允许您定义其他设置。

   * 可以将SQL表与过滤器关联，以使其对共享该表的所有编辑器都通用。
   * 要阻止任何用户覆盖过滤器，请选择 **[!UICONTROL Do not restrict the filter]** 选项。 例如，对于投放向导中提供的“投放的收件人”和“属于文件夹的投放的收件人”过滤器，此选项处于活动状态。 这些过滤器不能过载。
