---
title: 開始使用Campaign中的設定檔和對象
description: 瞭解如何在Campaign中建立和管理設定檔和對象
feature: Audiences, Profiles
role: User
level: Beginner
exl-id: 43483085-8aa6-47e6-89e7-9211e37beaa4
source-git-commit: 34af97ae01f7dba418fd0a8c950fc549dfbbd98b
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 20%

---

# 用户档案和受众入门{#gs-profiles-and-audiences}

設定檔是儲存在Campaign資料庫中的聯絡人，例如客戶、服務的訂閱者或潛在客戶。 有许多可能的机制可获取用户档案并创建此数据库：通过 Web 窗体在线收集、手动或自动导入文本文件、复制公司数据库或其他信息系统的内容。透過Adobe Campaign，您可以將行銷記錄、購買資訊、偏好設定、CRM資料以及任何相關的PI資料整合到整合檢視中，以進行分析並採取行動。 設定檔包含鎖定目標、確認及追蹤個人所需的所有資訊。



設定檔是 **nmsRecipient** 表格或外部表格，用於儲存所有設定檔屬性，例如名字、姓氏、電子郵件地址、Cookie ID、客戶ID、行動識別碼或與特定頻道相關的其他資訊。 連結至收件者表格的其他表格包含設定檔相關資料，例如包含傳送給收件者之所有傳遞記錄的傳遞記錄表格。 進一步瞭解中的內建設定檔和收件者表格 [本節](../dev/datamodel.md#ootb-profiles).

![](assets/recipients-in-explorer.png)

在Adobe Campaign中， **收件者** 是用於傳送傳遞（電子郵件、簡訊等）的預設設定檔。

資料庫中儲存的收件者資料可讓您篩選將接收任何指定傳遞的目標，並在傳遞內容中新增個人化資料。 数据库中还有其他类型的用户档案。这些用户档案是针对不同用途而设计的。例如，种子用户档案用于在将投放内容发送给最终目标前测试该投放内容。

若要使用設定檔資料填入Adobe Campaign，您可以：

* [匯入資料檔案](../start/import.md) 來自外部資料來源（例如CRM系統或平面檔案）
* [建立網路表單](../dev/webapps.md) 允許客戶輸入自己的資訊並建立自己的設定檔
* [對應至外部資料庫](../connect/fda.md) 儲存設定檔的位置
* 在「使用者端」主控台中手動輸入設定檔，如下所示：

![](assets/create-profile.png)

<!--You can also select your message audience in an external file: recipients are stored not in the database, but in files. These are known as “external” deliveries. These contacts can be imported or not in Adobe Campaign. [Learn more](external-profiles.md).-->

匯入後，您可以建立對象以傳送訊息。 瞭解如何建立對象 [在本節中](create-audiences.md).