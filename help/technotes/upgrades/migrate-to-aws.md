---
title: 将Campaign发送基础设施迁移到Amazon Web Services (AWS)
description: 将Campaign发送基础设施迁移到Amazon Web Services (AWS)
hide: true
hidefromtoc: true
source-git-commit: f1b4002063c8b94eb7251a9bcde9fe11791d0be3
workflow-type: tm+mt
source-wordcount: '401'
ht-degree: 2%

---


# Campaign将基础设施迁移至Amazon Web Services (AWS) {#migrate-infra-to-aws}

## 更改了哪些内容？{#aws-changes}

作为我们持续努力提供最高质量的电子邮件投放服务的一部分，Campaign电子邮件发送基础架构正在从Adobe托管的数据中心迁移至Amazon Web Services (AWS)。

此举将确保高可用性、最佳吞吐量以及扩展能力，以满足客户的需求。

## 您是否受影响？{#aws-impact}

此更改会影响：

* Campaign Classicv7托管客户和混合客户
* Campaign Managed Services客户
* 所有Campaign v8客户

## 何时进行此迁移？{#aws-timeline}

开发和暂存环境迁移将在以下位置进行： **2023年10**.

生产环境迁移计划在中开始 **2024年1月**. 随着日期的临近，将提供更多详细信息。

作为Campaign客户，您将在安排迁移批次时收到其他通知。 对于暂存环境，通知将在迁移前至少7天发送，对于生产环境，通知将在迁移前至少30天发送。

## 会有什么影响？{#impact}

此举将对客户透明：

* 迁移预计需要30分钟到60分钟之间的时间

* Campaign实例在迁移时段将无法发送邮件。 任何其他Campaign功能都不会受到影响。


## 常见问题解答 {#aws-faq}

* **为什么这是强制升级？**

  由Adobe Web Services (AWS)托管的新Campaign发送基础设施为我们的客户提供更好的质量和可靠性。 它还提供了强大而现代的基础架构，以确保更好的可用性和最佳吞吐量。

* **此迁移面向哪些客户？**

  所有Campaign v8客户和Campaign Classicv7混合、托管和Campaign Managed Services都将迁移其环境。

* **预计停机时间是多少？**

  预计停机时间为30到60分钟。

* **客户是否需要执行任何迁移操作？**

  无需执行任何操作，因为Adobe会自动运行迁移。

* **客户需要运行哪些验证？**

  此迁移不需要任何特定测试。 如果发现任何问题，请联系 [Adobe客户关怀](https://experienceleague.adobe.com/?support-solution=Campaign#support)


* **我是否可以请求更改计划安全升级插槽的日期/时间？**

  由于这是强制性迁移，我们强烈建议您调整现有计划。


对于任何其他问题，您可以联系 [Adobe客户关怀](https://experienceleague.adobe.com/?support-solution=Campaign#support).
