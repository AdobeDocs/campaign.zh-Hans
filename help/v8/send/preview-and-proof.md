---
title: 预览和测试电子邮件
description: 了解如何在发送之前验证投放
feature: Personalization
role: User
level: Beginner
exl-id: 5b9fa90c-c23e-47a7-b2ca-de75da4da2ab
source-git-commit: c248dd899ea704e43873652545c6b945c2915b57
workflow-type: tm+mt
source-wordcount: '713'
ht-degree: 4%

---

# 预览和测试电子邮件 {#preview-test}

定义消息内容后，即可使用测试配置文件对其进行预览和测试。如果插入 [个性化内容](personalize.md)，则可以使用测试用户档案数据检查此内容在消息中的显示方式。 此外，要检测消息内容或个性化设置中可能出现的错误，请向测试用户档案发送校样。 每次进行更改时都应发送验证，以验证最新内容。

## 内容预览{#preview-content}

在发送校样之前，最佳做法是在投放窗口的预览部分中检查消息内容。

要预览消息内容，请执行以下步骤：

1. 浏览到 **预览** 选项卡。
1. 单击 **[!UICONTROL Test personalization]** 按钮来填充个性化数据。 您可以在数据库中选择特定收件人、种子地址，或从目标群体中选择用户档案（如果已定义）。 您还可以在不进行个性化的情况下检查内容。

   ![](assets/test-personalization.png)

1. 将生成预览，以便您检查消息渲染。 在消息预览中，个性化元素会被替换为选定的测试用户档案数据。

   ![](assets/test-personalization-with-a-recipient.png)

1. 选择其他测试用户档案，以预览消息每个变体的电子邮件呈现。

##   发送验证 {#send-proofs}

对于电子邮件投放，您可以发送校样以验证消息内容。 通过发送校样，您可以检查选择退订链接、镜像页面和任何其他链接、验证消息、验证图像是否显示、检测可能的错误等。 您可能还希望检查在不同设备上的设计和渲染。

校样是一种特定的消息，允许您在将消息发送到主受众之前对消息进行测试。 校样收件人负责批准邮件：呈现、内容、个性化设置、配置。

### 校样收件人 {#proofs-recipients}

可以在投放模板中定义校样目标，或者特定于投放。 在这两种情况下，请从 **[!UICONTROL To]** 链接，然后选择 **[!UICONTROL Target of the proofs]** 选项卡。

![](assets/target-of-proofs.png)

校样目标的类型从 **[!UICONTROL Targeting mode]** 下拉列表。

* 使用 **[!UICONTROL Definition of a specific proof target]** 选项来选择数据库中的收件人作为校样目标。
* 使用 **[!UICONTROL Substitution of the address]** 选项，以输入电子邮件地址并使用目标收件人数据来验证内容。 可以手动输入替代地址，也可以从下拉列表中选择替代地址。 关联的枚举是“替换地址”(rcpAddress)。
默认情况下，替换会随机执行，但您可以通过  **[!UICONTROL Detail]** 图标。

   ![](assets/target-of-proofs-substitution-details.png){width="800" align="left"}

   选择 **[!UICONTROL Select a profile (must be included in the target)]** 选项，然后选择收件人。

   ![](assets/target-of-proofs-substitution.png){width="800" align="left"}


* 使用 **[!UICONTROL Seed addresses]**  选项来使用种子地址作为校样目标。 这些地址可以从文件导入或手动输入。

   >[!NOTE]
   >
   >种子地址不属于默认收件人表(nms:recipient)，它们将在单独的表中创建。 如果使用新数据扩展收件人表，则还必须使用相同的数据扩展种子地址表。

   详细了解种子地址(位于 [Campaign Classicv7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses.html){target="_blank"}.

* 使用 **[!UICONTROL Specific target and Seed addresses]** 用于组合种子地址和特定电子邮件地址的选项。 相关配置随后在两个单独的子选项卡中定义。

### 发送验证{#proofs-send}

要发送消息校样，请执行以下步骤：

1. 在消息定义屏幕中，单击 **[!UICONTROL Send a proof]** 按钮。
1. 从 **[!UICONTROL Send a proof]** 窗口中，检查校样收件人。
1. 单击 **[!UICONTROL Analyze]** 以开始准备校样消息。

   ![](assets/send-proof-analyze.png){width="800" align="left"}

1. 投放准备完成后，使用 **[!UICONTROL Confirm delivery]** 开始发送校样消息。

浏览到 **[!UICONTROL Audit]** 选项卡来检查校样副本的提交。

建议在对消息内容进行每次修改后发送校样。

>[!NOTE]
>
>在发送的校样中，指向镜像页面的链接不活动。 它仅在最终消息中激活。

### 校样属性{#proofs-properties}

校样属性在 **[!UICONTROL Advanced]** 选项卡。 浏览到 **[!UICONTROL Proof properties...]** 链接以定义校样的参数和标签。 您可以选择保留：

* 校样中的地址重复
* 列入阻止列表校样中的地址
* 校样中的隔离地址

默认情况下，校样消息由 `Proof #N` 在主题中提及，其中 `N` 是校样号。 此数字会随每次校样投放分析而增加。 您可以更改 `proof` 前缀。

![](assets/proof-parameters.png){width="800" align="left"}


## 操作方法视频 {#video-proof}

了解如何为电子邮件投放发送并确认验证。

>[!VIDEO](https://video.tv.adobe.com/v/333404)
