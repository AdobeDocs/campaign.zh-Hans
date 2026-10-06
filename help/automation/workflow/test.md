---
product: campaign
title: 测试
description: 了解有关测试工作流活动的更多信息
feature: Workflows
version: Campaign v8, Campaign Classic v7
exl-id: 0d4d13f6-7128-44d3-ad5c-4ed02257ee64
TQID: 'https://experienceleague.adobe.com/dXkGOQ-OD-KUwWx29DcE7FqYzbDSF-M6ox8-8cTurjA'
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
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 4%
---
# 测试{#test}



**Test**&#x200B;类型活动激活满足与其关联的条件的第一个过渡。 如果未满足任何条件，并且激活了&#x200B;**[!UICONTROL Use the default fork]**&#x200B;选项，则将激活默认过渡。

条件是一个JavaScript表达式，其计算结果必须为“true”或“false”。 要输入表达式，请单击条件名称右侧的图标，然后选择&#x200B;**[!UICONTROL Edit...]**。

![](assets/edit_test.png)

有关通过工作流JavaScript访问的应用服务器的所有其他JavaScript函数和SOAP方法的更多信息，请参阅[JSAPI文档](https://experienceleague.adobe.com/zh-hans/tools/campaign-api){target="_blank"}。

您还可以直接从此编辑器插入变量。 有关如何使用变量的更多信息，请参阅[此章节](javascript-scripts-and-templates.md#variables)。

可以从活动属性编辑窗口中添加、删除或排序条件，也可以从过渡中修改条件。

如果计算结果被不同的条件重用，则可以在活动的初始化脚本中对其进行计算。 结果必须存储在任务的变量中，以供条件脚本(task.vars.xxx)访问。
