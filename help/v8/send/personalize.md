---
title: 个性化入门
description: 瞭解如何個人化訊息內容
feature: Personalization
role: User
level: Beginner
exl-id: 1da45746-4d69-415b-a793-9a08ce80091d
source-git-commit: c248dd899ea704e43873652545c6b945c2915b57
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 36%

---

# 个性化入门 {#personalize-content}

為了充分運用每一次行銷活動，Adobe Campaign可讓您提供自訂內容，以與客戶層級溝通。 根據設定檔資料，個人化功能可為不同群組和個人建立自訂體驗：您可以運用您擁有的關於特定收件者的資料和資訊，根據每位收件者調整訊息。 這可以是他們的名字、興趣、居住地、購買內容等等。

Adobe Campaign簡化了個人化：您可以使用單一畫面來顯示為每個收件者自訂的不同內容型別 [電子郵件範本](create-templates.md). 在您的交易式訊息（例如購買確認或購物車放棄電子郵件）中，在單一電子郵件範本中包含每個人的產品清單資訊。


## 個人化策略 {#personalization-strategy}

使用Campaign建立動態內容並傳送個人化訊息。 可結合個人化功能來改善您的訊息並建立自訂使用者體驗。

可以通过以下方式个性化邮件内容：

* 插入动态&#x200B;**个性化字段**

   个性化字段用于邮件的第一级个性化。您可以从个性化编辑器中选择数据库中可用的任何字段。对于投放，您可以选择与收件人、邮件或投放相关的任何字段。可将这些个性化属性插入邮件的主题行或正文中。[了解详情](personalization-fields.md)。

   以下语法可在您的内容中插入收件人的城市：&lt;%= recipient.location.city %>。

* 插入预定义的&#x200B;**内容块**

   Campaign 附带了一组个性化块，其中包含可插入投放中的特定渲染。例如，您可以添加徽标、问候邮件或指向邮件的镜像页面的链接。可以从个性化编辑器的专用条目中获得内容块。[了解详情](personalization-blocks.md)。

* 建立 **條件式內容**

   例如，設定條件式內容，以根據收件者的設定檔新增動態個人化。 當特定條件為true時，會插入文字區塊和/或影像。 [了解详情](conditions.md)。

<!--* Add **personalized offers**
    
    Insert personalized offers in your message content, depending on the recipient location, the current weather, or the last purchase order.
-->


## 護欄和建議{#perso-guardrails}

### 個人化逾時{#perso-timeout}

若要改善傳送保護，您可以設定個人化階段的逾時期間。

在 **[!UICONTROL Delivery]** 的標籤 **[!UICONTROL Delivery properties]**，請為以下專案選取以秒為單位的最大值 **[!UICONTROL Maximum personalization run time]** 選項。

在預覽或傳送期間，如果個人化階段超過您在此欄位中設定的最大時間，流程將中止，並出現錯誤訊息，傳送將失敗。

預設值為5秒。

如果您將此選項設為0，則個人化階段將沒有時間限制。


### 內部變數{#internal-variables}

下列變數是可用於個人化的內部變數，但不得修改： **傳遞**， **message**， **資料來源**， **targetdata**， **提供者**， **抵用券**， **抵用券值**， **主張**.


## 教學課程影片 {#personalization-video}

了解不同类型的动态内容，并了解如何创建个性化块和条件语句并将它们应用到投放中。


>[!VIDEO](https://video.tv.adobe.com/v/335734?quality=12)
