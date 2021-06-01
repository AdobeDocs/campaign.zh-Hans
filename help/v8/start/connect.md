---
product: Adobe Campaign
title: 了解如何连接到Campaign v8
description: 连接到Campaign v8
feature: 受众
role: Data Engineer
level: Beginner
exl-id: 176cc4f0-8827-4127-9f03-7d75ac8cf917
source-git-commit: 5363950db5092bc7e0a72a0823db1132a17dda33
workflow-type: tm+mt
source-wordcount: '752'
ht-degree: 6%

---

# 连接到Adobe Campaign v8{#gs-ac-connect}

Campaign客户端控制台是一个富客户端，可让您连接到Campaign应用程序服务器。

在开始之前，您需要：

* 在[兼容性矩阵](compatibility-matrix.md)中检查您的系统和工具与Adobe Campaign的兼容性
* 获取Campaign服务器URL
* 获取用户凭据

## 下载并安装客户端控制台

首次使用Campaign时，或者如果您需要升级到较新版本，则需要下载客户端控制台并安装它。

有两个选项可用：

1. 作为Campaign管理员，请连接到Adobe[Software Distribution](https://experience.adobe.com/#/downloads/content/software-distribution/encampaign.html)并下载客户端控制台安装程序。 然后，您可以将其安装到本地计算机上。

1. 作为最终用户，Adobe可以为您部署控制台：更新控制台后，系统会在弹出窗口中提示您下载最新的客户端控制台版本。

>[!CAUTION]
>
>Adobe建议取消选中选项&#x200B;**[!UICONTROL No longer ask this question]** ，以确保当有新版本的控制台可用时，所有用户都会收到警报。  如果选择此选项，则用户将不会获悉新的可用版本。

## 创建连接

新安装客户端控制台后，请按照以下步骤创建与应用程序服务器的连接：

1. 从&#x200B;**Adobe Campaign**&#x200B;程序组的Windows **[!UICONTROL Start]**&#x200B;菜单启动控制台。

1. 单击凭据字段右上角的链接以访问连接配置窗口。

1. 单击&#x200B;**[!UICONTROL Add > Connection]**&#x200B;并输入Adobe Campaign应用程序服务器的标签和URL。

1. 通过URL指定与Adobe Campaign应用程序服务器的连接。 使用DNS或计算机的别名，或您的IP地址。

   例如，您可以使用[`https://<machine>.<domain>.com`](https://myserver.adobe.com)类型URL。

1. 如果为您的组织配置了AdobeIdentity Management系统(IMS)，请选中选项&#x200B;**[!UICONTROL Connect with an Adobe ID]** 。

1. 单击&#x200B;**[!UICONTROL Ok]**&#x200B;以保存设置。

您可以根据需要添加任意数量的连接，以连接到测试、暂存和生产环境等。

>[!NOTE]
>
>使用&#x200B;**[!UICONTROL Add]**&#x200B;按钮可创建&#x200B;**[!UICONTROL folders]**&#x200B;以组织所有连接。 只需将每个连接拖放到某个文件夹中。

## 登录Adobe Campaign

要登录到现有实例，请执行以下步骤：

1. 从&#x200B;**Adobe Campaign**&#x200B;程序组的Windows **[!UICONTROL Start]**&#x200B;菜单启动控制台。

1. 单击凭据字段右上角的链接以访问连接配置窗口。

1. 选择您需要登录的Campaign实例。

1. 单击 **[!UICONTROL Ok]**。

1. 输入用户登录凭据，然后单击&#x200B;**[!UICONTROL LOG IN]**。

   ![](assets/sign-in-v8.png)

根据您的配置，您的凭据可以是：

* 由您授予您访问权限的Campaign管理员提供
* 您的Adobe ID

## 授予用户访问权限

Adobe Campaign允许您定义和管理分配给各种运算符的权限。 这些权限和限制是授权或拒绝的一组权限和限制：

* 访问特定功能（通过指定权限），
* 访问某些元素，
* 创建、修改和/或删除元素（投放、联系人、营销活动、群组等）。

在[此部分](permissions.md)中了解有关用户以及如何定义其权限的更多信息。

作为Campaign管理员，您负责创建操作员并与用户共享其凭据。

## 使用Adobe ID连接到Campaign{#connect-ims}

Campaign用户可以使用其Adobe ID通过AdobeIdentity Management系统(IMS)连接到Adobe Campaign控制台。 此实施具有以下优势：

* 所有 Experience Cloud 解决方案都可以使用相同的 ID。
* 使用具有不同集成的 Adobe Campaign 时，可以记住该连接。
* 更强大的密码管理策略。
* 使用联合 ID 帐户（外部 ID 提供商）。

[!DNL :speech_balloon:] 作为受管Cloud Services用户， [请](campaign-faq.md#support) 联系Adobe以通过Campaign实施AdobeIMS。

## 通过LDAP登录连接到Campaign

可以配置Adobe Campaign，以便用户通过其LDAP身份验证访问平台。

[!DNL :speech_balloon:] 作为受管Cloud Services用户，请 [联系](campaign-faq.md#support) Adobe以配置LDAP与Campaign的集成。


## Web访问{#web-access}

应用程序的某些部分可通过使用HTML用户界面的简单Web浏览器访问：营销活动功能板、多维数据集报告、实例监控等。

[!DNL :arrow_upper_right:] 在Campaign Classicv7文档中了解有关Web [访问的更多信息](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-workspace.html?lang=en#console-and-web-access)

验证过程中也使用Web访问：操作员可以单击批准请求电子邮件，并通过其Web浏览器连接到Campaign，以验证或拒绝投放内容或预算。

[!DNL :arrow_upper_right:] 了解如何在Campaign Classicv7文档中设置 [和管理批准](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-approval.html?lang=zh-Hans#orchestrating-campaigns)
