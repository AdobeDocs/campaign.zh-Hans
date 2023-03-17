---
title: 添加指向镜像页面的链接
description: 了解如何链接到镜像页面
feature: Email
role: User
level: Beginner
source-git-commit: 2c35b169725b5300940260124a4b559eb44ffe43
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 0%

---

# 关于电子邮件镜像页面{#mirror-page}

镜像页面是您电子邮件的在线版本。

虽然大多数电子邮件客户端在渲染图像时没有出现问题，但出于安全原因，某些预设可以避免显示图像。 用户可以浏览电子邮件的镜像页面，例如，当他们尝试在收件箱中查看电子邮件时遇到呈现问题或图像损坏时。 还建议出于无障碍原因提供在线版本，或鼓励社交共享。

由Adobe Campaign生成的镜像页面包含所有个性化数据。

![](assets/mirror-page-link.png)


## 添加指向镜像页面的链接{#link-to-mirror-page}

插入指向镜像页面的链接是一种好做法。 此链接可以是“在浏览器中查看此电子邮件”，通常位于电子邮件的页眉或页脚。

在Adobe Campaign中，您可以使用 **个性化块**. 默认情况下，仅当将链接插入消息内容中时，才会生成镜像页面。

内置 **链接到镜像页面** 个性化块在电子邮件内容中插入以下代码： `<%@ include view='MirrorPage' %>`.

<!--For more on personalization blocks insertion, refer to [Personalization blocks](personalization-blocks.md).-->

## 镜像页面生成{#mirror-page-generation}

默认情况下，如果电子邮件内容不为空，并且包含指向镜像页面的链接（即镜像链接），则Adobe Campaign会自动生成镜像页面。

您可以控制电子邮件镜像页面的生成模式。 提交属性中提供了相应选项。 要访问这些选项，请执行以下操作：

1. 浏览到 **[!UICONTROL Validity]** 选项卡。
1. 在 **镜像页面管理** ，请检查 **[!UICONTROL Mode]** 下拉列表。

![](assets/mirror-page-generation.png)

除了默认模式之外，还提供以下选项：

* **[!UICONTROL Force the generation of the mirror page]**:即使投放中未插入指向镜像页面的链接，也使用此模式生成镜像页面。
* **[!UICONTROL Do not generate the mirror page]**:使用此模式可避免生成镜像页面，即使投放中存在链接也是如此。
* **[!UICONTROL Generates a mirror page accessible using only the message identifier]**:使用此选项可启用在投放日志窗口中访问包含个性化数据的镜像页面内容。 要访问此镜像页面，请执行以下操作：发送投放后，将其打开并浏览到其 **[!UICONTROL Delivery]** 选项卡。 选择收件人并单击 **[!UICONTROL Display the mirror page for this message...]** 链接。 镜像页面将显示在新选项卡中。

