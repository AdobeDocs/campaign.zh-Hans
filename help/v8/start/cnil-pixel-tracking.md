---
title: 电子邮件跟踪像素和CNIL指南
description: 了解CNIL关于电子邮件跟踪像素的更新指南，以及可支持合规性工作的Adobe Campaign功能。
feature: Overview
role: User
level: Beginner
hide: true
source-git-commit: 94d9f6725b0bfb458707c9900f5b6cb553d72daf
workflow-type: tm+mt
source-wordcount: '849'
ht-degree: 1%

---


# 了解CNIL关于电子邮件跟踪像素的更新指南

此帖子仅供参考。 这不是法律建议，也不保证您遵守适用法律。 下面描述的Adobe Campaign产品功能是构建块，经过适当配置和操作后，可以支持合规的实施。 各客户有责任决定及遵守其于适用法律下之责任。

## 概述

2026年4月14日，法国数据保护机构，法国国家信息和自由委员会&#x200B;_发布了关于在电子邮件中使用跟踪像素的[建议](https://www.cnil.fr/sites/default/files/2026-04/recommandation-pixels_de_suivi.pdf)。_&#x200B;该指南阐明何时需要获得同意，并强调针对电子邮件像素跟踪的适当同意实践的重要性。 此策略可能会影响向位于法国的订阅者发送电子邮件的任何实体的发送实践。

CNIL提供了自建议之日起三个月的时间，要求公司通知其电子邮件收件人（“用户”）跟踪像素的存在、其目的以及用户选择退出的权利。 在此过渡期间，客户应通知用户像素跟踪信息，并在必要时提供选择退出选项。 预计CNIL将在2026年7月14日之后开始执行活动。

随着CNIL和其他监管机构澄清有关跟踪像素和相关问题的指导，Adobe将继续监控更新，并告知客户支持电子邮件营销的Adobe产品（包括Adobe Campaign）的技术功能。

Adobe电子邮件营销执行应用程序（包括Adobe Journey Optimizer、Journey Optimizer B2B、Adobe Campaign和Marketo Engage）提供了控件，可帮助客户在投放或电子邮件级别管理打开跟踪。 根据适用的CNIL指导和其他法律，客户有责任确定自己的合规义务，但这些功能可能会为客户合规工作提供支持。

## 什么是电子邮件跟踪像素

电子邮件跟踪像素是嵌入到电子邮件HTML中的1x1透明图像。 收件人的电子邮件客户端加载该图像时，像素会向服务器发出ping信号，该信号记录时间戳、设备类型、电子邮件客户端等数据，有时还会记录IP地址以大致了解位置。 然后，该日志将绑定到收件人的记录，以允许营销人员查看电子邮件是否已打开。

## 客户支持

为实施上述更改寻求帮助的客户可以与其现有的Adobe生态系统合作。 有关所引用Adobe功能的技术问题，请联系您的客户成功经理或技术客户经理。

## 与电子邮件跟踪相关的Adobe Campaign功能

在配置架构以满足CNIL指导时，客户可以使用Adobe Campaign的本机跟踪、架构和个性化机制来处理某些元素：

* **投放的分类。** 使用`emailType`属性（身份验证、仅可投放性、事务性、营销、公共服务、B2B潜在客户）扩展`nms:delivery`。 分类可驱动哪些像素未经同意是允许的。

* **同意捕获。** 使用带有措辞版本、时间戳、捕获源和过期的专用同意结构扩展`nms:recipient`。 扩展注册表单和首选项中心，以独立于电子邮件选择加入收集像素同意。

* **像素发射。** 为每个像素定义一个`NmsTracking_OpenFormula`目的（身份验证、可投放性、性能、分析、欺诈检测）。 投放类型规则根据emailType和收件人的单用途同意来选择要发送的公式。 个性化块会封装逻辑，以便该逻辑不存在于个人创意中。

* **退出。** 向每个电子邮件页脚添加一个&#x200B;**管理跟踪器首选项**&#x200B;链接，该链接不同于取消订阅链接。 该链接指向通过`idTracking`验证的`nms:webApp`登陆页面；收件人只需点击一下即可撤回同意，而无需重新输入其电子邮件地址。 添加到标准&#x200B;**跟踪**&#x200B;工作流的筛选器步骤可防止在退出后利用先前投放的电子邮件的重新打开。

* **同意证明。** 捕获仅附加日志（例如`pix:consentLog`扩展命名空间）中的每个同意事件，并单独存储措辞版本以便在措辞更改后可检索。 通过Adobe Campaign资源管理器显示日志，并作为定期导出。
* **重新请求管理。** `lastPixelRefusalDate`字段和筛选类型规则可防止在拒绝后至少六个月重新进行请求。 定期工作流程有助于管理同意过期。

* **报告。** 现有的Adobe Campaign报表将继续针对新字段（urlCategory、emailType、同意标志）运行，而不会更改代码。

有关Adobe电子邮件营销执行应用程序中电子邮件跟踪的更多信息，请参阅此文档：

| 产品 | 文档参考 |
|---|---|
| Campaign v8 | [邮件跟踪](https://experienceleague.adobe.com/zh-hans/docs/campaign/campaign-v8/analytics/tracking/url-tracking){target="_blank"} |
| Campaign Classic | [开始使用邮件跟踪](https://experienceleague.adobe.com/zh-hans/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-message-tracking){target="_blank"} |
| Campaign Standard | [配置电子邮件渠道](https://experienceleague.adobe.com/zh-hans/docs/campaign-standard/using/administrating/configuring-channels/configuring-email-channel){target="_blank"} |
| Journey Optimizer | [邮件跟踪文档](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/channels/email/design-email/add-content/message-tracking){target="_blank"} |
| Marketo Engage | [禁用电子邮件链接的跟踪](https://experienceleague.adobe.com/zh-hans/docs/marketo/using/product-docs/email-marketing/general/functions-in-the-editor/disable-tracking-for-an-email-link){target="_blank"} |
| Journey Optimizer B2B | [电子邮件设置文档](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer-b2b/user/journey-content/email-channel/add-email){target="_blank"} |


