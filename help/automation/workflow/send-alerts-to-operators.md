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



在此示例中，我们希望向运算符发送警报，该运算符将包含已打开新闻稿但未单击其所包含链接的用户档案名称。

用户档案的名字和姓氏字段均链接到 **[!UICONTROL Recipients]** 定位维度，而 **[!UICONTROL Alert]** 活动已链接到 **[!UICONTROL Operator]** 定向维度。 因此，两个定向维度之间没有可用的字段来执行协调并检索名字和姓氏字段，并在警报活动中显示它们。

此过程是构建一个工作流，如下所示：

1. 使用 **[!UICONTROL Query]** 活动来定位数据。
1. 添加 **[!UICONTROL JavaScript code]** 活动，将查询中的群体保存到实例变量。
1. 使用 **[!UICONTROL Test]** 活动以检查群体计数。
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

* 的 **[!UICONTROL queryDef schema]** 标记应与查询活动中使用的定向维度的名称相对应。
* 的 **[!UICONTROL node expr]** 标记应与要检索的字段名称相对应。

![](assets/uc_operator_3.png)

要检索这些信息，请执行以下步骤：

1. 右键单击 **[!UICONTROL Query]** 活动，然后选择 **[!UICONTROL Display the target]**.

   ![](assets/uc_operator_4.png)

1. 右键单击列表，然后选择 **[!UICONTROL Configure list]**.

   ![](assets/uc_operator_5.png)

1. 查询定向维度和字段名称将显示在列表中。

   ![](assets/uc_operator_6.png)

## 测试群体计数 {#testing-the-population-count}

将以下代码添加到 **[!UICONTROL Test]** 活动，以检查定向群体是否至少包含1个用户档案。

```
var.recCount>0
```

![](assets/uc_operator_7.png)

## 设置警报 {#setting-up-the-alert}

现在，已将群体添加到具有所需字段的实例变量中，接下来可以将这些信息添加到 **[!UICONTROL Alert]** 活动。

为此，请将添加到 **[!UICONTROL Source]** 选项卡代码：

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
>的 **[!UICONTROL <%= item.target.recipient.@fieldName %>]** 命令允许您通过 **[!UICONTROL JavaScript code]** 活动。\
>只要字段已插入到JavaScript代码中，就可以添加所需数量的字段。

![](assets/uc_operator_8.png)
