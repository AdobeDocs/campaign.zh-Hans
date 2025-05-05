---
product: campaign
title: 技术说明 — 凭据轮换指南
description: Adobe Campaign技术说明 — 凭据轮换指南
hide: true
hidefromtoc: true
exl-id: 0848ee2d-3506-4167-9aea-a1589aa82805
source-git-commit: 14e49a0b4de1b82239113bd670213449f464c27f
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 1%

---

# 技术说明：凭据轮换指南 {#ac-customer-credentials}

作为客户，您有责任定期使用新的凭据集替换您的凭据，以降低受到危害的风险。

## Adobe Campaign选项凭据 {#ac-options-credentials}

在Adobe Campaign Explorer中，**管理>平台>选项**&#x200B;节点允许您对Adobe Campaign选项进行修改。 如果您在此处存储了一些凭据，请确保将其轮换。

![](assets/technote-2.png)

## 外部帐户凭据 {#ac-accounts-credentials}

**管理>平台>外部帐户**&#x200B;节点允许您对Adobe Campaign外部帐户进行修改。

请轮换保存在外部帐户中的所有凭据。

>[!CAUTION]
>
>**不**&#x200B;修改Adobe托管凭据。 不应修改任何具有`adobe`相关服务器的外部帐户。

![](assets/technote-1.png)

对于特定的技术`mc*` （例如：mc1、mc2等）和`Interaction*` （例如：interaction1、interaction2等）运算符，可以采用以下两种方法中的任何一种：

1. Adobe可以更改此类操作员的凭据，并与您共享。 请注意，使用这些运算符的所有集成都将停止工作，直到您这边更新这些运算符的凭据为止。

1. Adobe可以创建与每个现有运算符对应的&#x200B;**新**&#x200B;运算符并与您共享。 在您切换到这些新运算符后，Adobe将删除所有出现的旧运算符。


## Mobile Services私钥/证书  {#ac-key-credentials}

有关与Mobile Services相关的私钥和证书的轮换，请参阅以下链接。

* 对于Android，请参阅[此文档](https://experienceleague.adobe.com/zh-hans/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android){target="_blank"}。
浏览至&#x200B;**创建Android移动应用程序>配置API版本**&#x200B;部分。

* 对于iOS，请参阅[此文档](https://experienceleague.adobe.com/zh-hans/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application){target="_blank"}。
浏览到&#x200B;**创建iOS移动应用程序 — >身份验证模式**&#x200B;部分。

## GPG 密钥 {#ac-gpg-credentials}

对于GPG密钥的旋转，需要执行以下步骤：

1. 使用现有密钥解密现有数据。 [了解详情](https://experienceleague.adobe.com/zh-hans/docs/control-panel/using/instances-settings/gpg-keys-management#decrypting-data){target="_blank"}。

1. 创建新的GPG密钥对。 在[本文档](https://experienceleague.adobe.com/zh-hans/docs/control-panel/using/instances-settings/gpg-keys-management#decrypting-data){target="_blank"}中了解有关GPG密钥管理的更多信息。

1. 将所有工作流中的现有GPG密钥使用情况替换为新创建的密钥。

1. 删除现有GPG密钥。
