---
title: 添加指向镜像页面的链接
description: 了解如何添加和管理指向镜像页面的链接
feature: Email
role: User
level: Beginner
exl-id: 7bf3937c-484d-4404-8a9b-de7a10f5455a
source-git-commit: b333db04dd10cc28956959a446f6567e2a89b2d4
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 56%

---

# 链接到镜像页面 {#mirror-page}

## 关于镜像页面 {#about-mirror-page}

镜像页面是电子邮件的在线版本。

大多数电子邮件客户端可以轻松渲染图像，但出于安全原因，某些预设可以避免显示图像。例如，如果用户尝试在收件箱中查看电子邮件时遇到渲染问题或损坏的图像，则可以浏览到电子邮件的镜像页面。此外，建议提供在线版本以方便访问或鼓励社交共享。

Adobe Campaign 生成的镜像页面包含所有个性化数据。

![镜像链接示例](assets/mirror-page-link.png){width="600" align="left"}

## 添加指向镜像页面的链接 {#link-to-mirror-page}

插入指向镜像页面的链接是一种好的做法。例如，此链接可以是“在浏览器中查看此电子邮件”或“在线阅读此电子邮件”。它通常位于电子邮件的页眉或页脚。

在 Adobe Campaign 中，您可以使用专用&#x200B;**个性化块**&#x200B;在电子邮件内容中插入指向镜像页面的链接。内置的&#x200B;**指向镜像页面的链接**&#x200B;个性化块会在电子邮件内容中插入以下代码：`<%@ include view='MirrorPage' %>`。

![](assets/mirror-page-insert.png){width="800" align="left"}


有关插入个性化内容块的更多信息，请参阅[个性化块](personalization-blocks.md)。

## 管理镜像页面的生成 {#mirror-page-generation}

默认情况下，如果电子邮件内容不为空，并且包含指向镜像页面的链接（也称为镜像链接），则 Adobe Campaign 会自动生成镜像页面。

您可以控制电子邮件镜像页面的生成方式。投放属性中提供了选项。要访问这些选项，请执行以下操作：

1. 浏览到电子邮件属性的&#x200B;**[!UICONTROL Validity]**&#x200B;选项卡。
1. 在&#x200B;**镜像页面管理**&#x200B;部分中，检查&#x200B;**[!UICONTROL Mode]**&#x200B;下拉列表。

![](assets/mirror-page-generation.png){width="800" align="left"}

除默认模式外，还提供以下选项：

* **[!UICONTROL Force the generation of the mirror page]**：使用此模式生成镜像页面，即使投放中未插入指向镜像页面的链接。
* **[!UICONTROL Do not generate the mirror page]**：使用此模式可避免生成镜像页面，即使链接存在于投放中也是如此。
* **[!UICONTROL Generates a mirror page accessible using only the message identifier]**：当电子邮件内容中不存在镜像页面链接时，请使用此选项在投放日志窗口中启用对镜像页面内容的访问，如下所述。

## 检查收件人的镜像页面 {#mirror-page-access}

您可以为投放的特定收件人访问镜像页面的内容，其中包含个性化数据。

要访问此镜像页面，请执行以下操作：

1. 发送投放后，打开它并浏览到其&#x200B;**[!UICONTROL Delivery]**&#x200B;选项卡。

1. 选择一个收件人，然后单击&#x200B;**[!UICONTROL Display the mirror page for this message...]**&#x200B;链接。

   ![](assets/mirror-page-display.png){width="800" align="left"}

   镜像页面显示在专用屏幕中，其中包含选定收件人的个性化数据。
