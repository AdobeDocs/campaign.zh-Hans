---
product: campaign
title: 加载 (SOAP)
description: 加载 (SOAP)
feature: Workflows
source-git-commit: 2b1dec4b9c456df4dfcebfe10d18e0ab01599275
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 4%

---

# 加载 (SOAP){#loading-soap}



>[!CAUTION]
>
>的 **加载(SOAP)** 活动仅在 **FDA（联合数据访问）** 已安装模块。 请核实您的许可协议。

的 **加载(SOAP)** 除 **数据加载(RDBMS)** 活动。

操作如下：

1. 在使用XML示例或WSDL之间进行选择。

   以下示例来自消息中心模块的技术工作流。

   ![](assets/load_soap_002.png)

1. 对于XML示例，请选择一个样例文件。 分析该文件以建立结果示例。

   对于WSDL，输入匹配的访问URL，然后生成骨骼代码。 选定的服务和调用将自动更新并显示。

   ![](assets/soap_load_003.png)

1. 选择 **[!UICONTROL Click here to view and edit analysis results]** 以指定每个已标识列。

   ![](assets/soap_load_001.png)

   如果要更新示例，请选择 **[!UICONTROL Re-analyze the example]**.

   您还可以通过**将列数据的格式个性化。

1. 您可以将行号用作标识符和/或指定SOAP调用返回多个元素。
1. 根据选项卡脚本的函数输入以下选项卡脚本：

   * **[!UICONTROL Initialization]**:建立SOAP连接。
   * **[!UICONTROL Iteration]**:执行对SOAP服务的调用。 此函数的返回必须是与示例或WSDL描述兼容的XML对象。

      在返回空XML对象之前，Adobe Campaign将在循环中调用此选项卡的代码。

   * **[!UICONTROL Finalization]**:关闭连接和/或释放处理过程中创建的其他资源。
