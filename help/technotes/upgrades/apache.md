---
product: campaign
title: 技术说明 — Adobe Campaign - Apache版本安全更新
description: Adobe Campaign - Apache版本安全更新
exl-id: 68e42fe4-7fb6-4b53-9f39-e77374e3753d
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 0%

---

# Adobe Campaign - Apache版本安全更新 {#apache-update}

>[!CAUTION]
>本文适用于：Campaign Classicv7托管Cloud Service客户、Campaign v8客户和Campaign Standard客户。

Adobe Campaign可与第三方工具配合使用，并且会定期更新兼容性，以仅实施受支持的版本，并从最新的修复和改进中受益。

Adobe Campaign包括Apache Tomcat，它通过HTTP充当应用程序服务器中的入口点，并与Apache Web Server集成。 Apache Software Foundation已发布Apache HTTP Server 2.4.53。此版本解决了可能允许远程攻击者控制受影响系统的漏洞。 了解详情，请参阅 [Apache 2.4.53发布](https://downloads.apache.org/httpd/Announcement2.4.html){target="_blank"}.

Adobe Campaign团队将通过以下方式执行Apache版本安全升级活动 **2022年6月15日** 以缓解此Apache漏洞并使实例环境更加安全。 此升级适用于在易受攻击的Apache HTTP Server版本上运行的所有Campaign Classic v7托管Cloud Service客户、Campaign v8和Campaign Standard客户。 如果您受到影响，Adobe已联系您，告知您有关此次升级的信息。

此升级预计在正常工作时间之外自动运行，以便您能够继续使用Campaign服务而不会造成任何中断。

您的非生产实例将由我们的团队首先升级，然后再升级您的生产实例。 由于这是由Adobe拥有的自动升级过程，因此无需您执行任何操作。 但是，如果您遇到任何问题，请联系 [Adobe客户关怀](https://experienceleague.adobe.com/?support-solution=Campaign#support).


>[!NOTE]
>此升级需要重新启动Apache Web Server。 停机时间不超过10分钟，具体时间如下。
> 

## 常见问题解答 {#apache-faq}

* **为什么这是强制升级？**

  当前的Apache版本易受攻击，并存在潜在的安全威胁。 请务必将Campaign实例升级到最新适用的Apache版本以解决安全风险。


* **哪些客户是安全升级的目标？**

  所有使用在旧版Apache上实施的Campaign环境的客户均已升级到最新适用的Apache版本。

* **预计停机时间是多少？**

  预计停机时间不到10分钟。

* **客户是否需要对此安全升级执行任何操作？**

  由于安全升级将自动运行，因此无需执行任何操作。

* **客户需要运行哪些验证？**

  此安全升级不需要任何特定测试。 如果发现任何问题，请联系 [Adobe客户关怀](https://experienceleague.adobe.com/?support-solution=Campaign#support)


* **我是否可以请求更改计划安全升级插槽的日期/时间？**

  由于这是安全修复，因此我们强烈建议您调整到现有计划。


对于任何其他问题，您可以联系 [Adobe客户关怀](https://experienceleague.adobe.com/?support-solution=Campaign#support).
