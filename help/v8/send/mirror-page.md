---
title: 添加指向镜像页面的链接
description: 了解如何添加和管理指向镜像页面的链接
feature: Email
role: User
level: Beginner
source-git-commit: 34af97ae01f7dba418fd0a8c950fc549dfbbd98b
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# 链接到镜像页面{#mirror-page}

## 关于镜像页面{#about-mirror-page}

镜像页面是您电子邮件的在线版本。

虽然大多数电子邮件客户端在渲染图像时没有出现问题，但出于安全原因，某些预设可以避免显示图像。 用户可以浏览电子邮件的镜像页面，例如，当他们尝试在收件箱中查看电子邮件时遇到呈现问题或图像损坏时。 还建议出于无障碍原因提供在线版本，或鼓励社交共享。

由Adobe Campaign生成的镜像页面包含所有个性化数据。

![镜像链接示例](assets/mirror-page-link.png){width="600" align="left"}

## 添加指向镜像页面的链接{#link-to-mirror-page}

插入指向镜像页面的链接是一种好做法。 此链接可以是“在浏览器中查看此电子邮件”或“在线阅读此内容”。 它通常位于电子邮件的页眉或页脚。

在Adobe Campaign中，您可以使用 **个性化块**. 内置 **链接到镜像页面** 个性化块在电子邮件内容中插入以下代码： `<%@ include view='MirrorPage' %>`.

![](assets/mirror-page-insert.png){width="800" align="left"}


有关自定义内容块插入的更多信息，请参阅 [个性化块](personalization-blocks.md).

## 镜像页面生成{#mirror-page-generation}

默认情况下，如果电子邮件内容不为空，并且包含指向镜像页面的链接（即镜像链接），则Adobe Campaign会自动生成镜像页面。

您可以控制电子邮件镜像页面的生成模式。 提交属性中提供了相应选项。 要访问这些选项，请执行以下操作：

1. 浏览到 **[!UICONTROL Validity]** 选项卡。
1. 在 **镜像页面管理** ，请检查 **[!UICONTROL Mode]** 下拉列表。

![](assets/mirror-page-generation.png){width="800" align="left"}

除了默认模式之外，还提供以下选项：

* **[!UICONTROL Force the generation of the mirror page]**:即使投放中未插入指向镜像页面的链接，也使用此模式生成镜像页面。
* **[!UICONTROL Do not generate the mirror page]**:使用此模式可避免生成镜像页面，即使投放中存在链接也是如此。
* **[!UICONTROL Generates a mirror page accessible using only the message identifier]**:如果电子邮件内容中不存在镜像页面链接，则使用此选项可启用在投放日志窗口中访问镜像页面的内容，如下所述。

## 检查收件人的镜像页面{#mirror-page-access}

您可以使用个性化数据访问投放特定收件人的镜像页面内容。

要访问此镜像页面，请执行以下操作：

1. 发送投放后，将其打开并浏览到其 **[!UICONTROL Delivery]** 选项卡。

1. 选择收件人并单击 **[!UICONTROL Display the mirror page for this message...]** 链接。

   ![](assets/mirror-page-display.png){width="800" align="left"}

   镜像页面会显示在专用屏幕中，并包含选定收件人的个性化数据。

