---
product: campaign
title: 加载 (SOAP)
description: 加载 (SOAP)
feature: Workflows
role: User
exl-id: 21c42a36-9a50-49b8-8a07-b041ba8b2026
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 4%

---

# 加载 (SOAP){#loading-soap}



>[!CAUTION]
>
>仅当您安装了&#x200B;**FDA（联合数据访问）**&#x200B;模块时，**加载(SOAP)**&#x200B;活动才可用。 请核实您的许可协议。

如果无法在外部数据库中直接通过FDA收集数据，则除了&#x200B;**数据加载(RDBMS)**&#x200B;活动之外，还会使用&#x200B;**加载(SOAP)**&#x200B;活动。

操作如下：

1. 选择使用XML示例或WSDL。

   以下示例来自消息中心模块的技术工作流。

   ![](assets/load_soap_002.png)

1. 对于XML示例，请选择一个示例文件。 对文件进行分析，建立结果实例。

   对于WSDL，输入匹配的访问URL，然后生成骨架代码。 所选服务和呼叫将自动更新并显示。

   ![](assets/soap_load_003.png)

1. 选择&#x200B;**[!UICONTROL Click here to view and edit analysis results]**&#x200B;以指定每个已识别的列。

   ![](assets/soap_load_001.png)

   如果要更新示例，请选择&#x200B;**[!UICONTROL Re-analyze the example]**。

1. 您可以使用行号作为标识符和/或指定SOAP调用返回多个元素。
1. 根据功能输入以下选项卡脚本：

   * **[!UICONTROL Initialization]**：建立SOAP连接。
   * **[!UICONTROL Iteration]**：执行对SOAP服务的调用。 此函数的返回必须是一个与示例或WSDL的说明兼容的XML对象。

     此选项卡的代码将由Adobe Campaign循环调用，直到返回空的XML对象。

   * **[!UICONTROL Finalization]**：关闭连接和/或释放在处理期间创建的其他资源。
