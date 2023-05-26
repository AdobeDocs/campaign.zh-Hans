---
product: campaign
title: 向操作员发送个性化提醒
description: 了解如何向运营商发送个性化提醒
feature: Workflows
exl-id: 41a009f6-d1e9-40c9-8494-3bbb4bd3d134
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 2%

---

# 向操作员发送个性化提醒{#sending-personalized-alerts-to-operators}



在本例中，我们希望向操作员发送警报，该操作员将包含打开了新闻稿但未单击新闻稿所包含链接的用户档案的名称。

用户档案的名字和姓氏字段链接到 **[!UICONTROL Recipients]** 定位维度，而 **[!UICONTROL Alert]** 活动链接到 **[!UICONTROL Operator]** 定位维度。 因此，两个定向维度之间没有可用字段来执行协调，检索名字和姓氏字段并在警报活动中显示它们。

该过程将构建一个工作流，如下所示：

1. 使用 **[!UICONTROL Query]** 活动以定位数据。
1. 添加 **[!UICONTROL JavaScript code]** 活动添加到工作流中，以将群体从查询保存到实例变量。
1. 使用 **[!UICONTROL Test]** 用于检查群体计数的活动。
1. 使用 **[!UICONTROL Alert]** 活动向操作员发送警报，具体取决于 **[!UICONTROL Test]** 活动结果。

![](assets/uc_operator_1.png)

## 将群体保存到实例变量 {#saving-the-population-to-the-instance-variable}

将以下代码添加到 **[!UICONTROL JavaScript code]** 活动。

```
var query = xtk.queryDef.create(  
    <queryDef schema="temp:query" operation="select">  
      <select>  
       <node expr="[target/recipient.@firstName]"/>  
       <node expr="[target/recipient.@lastName]"/>  
      </select>  
     </queryDef>  
  );  
  var items = query.ExecuteQuery();
```

确保Javascript代码与您的工作流信息相对应：

* 此 **[!UICONTROL queryDef schema]** 标记应对应于查询活动中使用的定向维度的名称。
* 此 **[!UICONTROL node expr]** 标记应该对应于要检索的字段的名称。

![](assets/uc_operator_3.png)

要检索这些信息，请执行以下步骤：

1. 从右键单击叫客过渡 **[!UICONTROL Query]** 活动，然后选择 **[!UICONTROL Display the target]**.

   ![](assets/uc_operator_4.png)

1. 右键单击列表，然后选择 **[!UICONTROL Configure list]**.

   ![](assets/uc_operator_5.png)

1. 查询定向维度和字段名称显示在列表中。

   ![](assets/uc_operator_6.png)

## 测试群体计数 {#testing-the-population-count}

将以下代码添加到 **[!UICONTROL Test]** 活动以检查目标群体是否至少包含1个用户档案。

```
var.recCount>0
```

![](assets/uc_operator_7.png)

## 设置警报 {#setting-up-the-alert}

现在，群体已通过所需字段添加到实例变量中，您可以将这些信息添加到 **[!UICONTROL Alert]** 活动。

为此，请将添加到 **[!UICONTROL Source]** 选项卡下面的代码：

```
<ul>
<%
var items = new XML(instance.vars.items)
for each (var item in items){
%>
<li><%= item.target.@firstName %> <%= item.target.@lastName %></li>
<%
} %></ul>
```

>[!NOTE]
>
>此 **[!UICONTROL <%= item.target.recipient.@fieldName %>]** 命令允许您添加已通过保存到实例变量的字段之一 **[!UICONTROL JavaScript code]** 活动。\
>您可以根据需要添加任意数量的字段，只要这些字段已插入JavaScript代码中即可。

![](assets/uc_operator_8.png)
