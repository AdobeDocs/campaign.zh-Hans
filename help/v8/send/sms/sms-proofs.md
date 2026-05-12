---
title: 短信发送校样
description: 了解如何发送短信投放验证
feature: SMS
role: User
level: Beginner, Intermediate
version: Campaign v8, Campaign Classic v7
exl-id: d2ec4d92-7f00-47c8-98e6-0613d6387de0
TQID: https://experienceleague.adobe.com/mAVky406-MXlkv76bqxfmolzhemVCUYKhQF1ESceRdE
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 244
ht-degree: 1%

---

# 发送短信投放的证明 {#sms-proof}

Adobe强烈建议您设置投放验证周期。 在将内容发送给受众之前，请确保内容已获批准。

您可以发送短信投放的验证来验证它：

1. 单击&#x200B;**[!UICONTROL Send a proof]**&#x200B;按钮，将打开一个窗口

   ![](assets/proof_targeting.png){zoomable="yes"}

   您可使用多种模式来发送验证：

   * **[!UICONTROL Definition of a specific proof target]**：允许您使用过滤器查询数据库中的地址作为验证目标
   * **[!UICONTROL Substitution of the address]**：允许您输入测试地址，并使用目标收件人数据验证内容。 可以手动输入替代地址，也可以从下拉列表中选择替代地址。 关联的[枚举](../../config/enumerations.md)是&#x200B;**[!UICONTROL Substitution address (rcpAddress)]**。
默认情况下，会随机执行替换，但您可以通过**[!UICONTROL Detail]**&#x200B;图标从主目标中选择特定收件人。
   * **[!UICONTROL Seed addresses]**：允许您访问种子地址作为验证目标。 这些地址可以从文件导入或手动输入。
   * **[!UICONTROL Specific target and Seed addresses]**：允许您合并来自收件人的种子地址和地址。

1. 选择您的&#x200B;**[!UICONTROL Targeting mode]**&#x200B;后，根据它添加您的证明地址

   在以下示例中，我们选择&#x200B;**[!UICONTROL Definition of a specific proof target]**&#x200B;并添加收件人：

   ![](assets/proof_recipient.png){zoomable="yes"}

1. 单击 **[!UICONTROL Analyze]** 按钮。
Adobe Campaign将在验证验证发送之前执行所有控制。 在分析结束时，**[!UICONTROL Confirm delivery]**&#x200B;按钮将可点击。

   ![](assets/proof_analyze.png){zoomable="yes"}

1. 要发送短信投放的证明，请单击&#x200B;**[!UICONTROL Confirm delivery]**&#x200B;按钮。

如果在此阶段一切正常，则您可以继续并[将您的短信投放发送给受众](sms-audience.md)。
