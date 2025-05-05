---
title: 将Campaign发送基础设施迁移到Amazon Web Services (AWS)
description: 将Campaign发送基础设施迁移到Amazon Web Services (AWS)
hide: true
hidefromtoc: true
exl-id: 50279a2f-0296-43f5-8967-16cc6a0c88f6
source-git-commit: 3e95a56825a143a4457ab7ee242208d7daaeb414
workflow-type: tm+mt
source-wordcount: '474'
ht-degree: 0%

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
* Campaign Standard客户

## 何时进行此迁移？{#aws-timeline}

开发和暂存环境迁移将于&#x200B;**2023年10月**&#x200B;进行。

生产环境迁移计划于&#x200B;**2024年1月**&#x200B;开始。 随着日期的临近，将提供更多详细信息。

作为Campaign客户，您将在安排迁移批次时收到其他通知。 对于暂存环境，通知将在迁移前至少7天发送，对于生产环境，通知将在迁移前至少30天发送。

## 会有什么影响？{#impact}

此举将对客户透明：

* 每个迁移波次的长度可能因受影响的Campaign实例数而异。 当计划了迁移波次时，通知将包含预期的持续时间。

* Campaign实例在迁移时段将无法发送邮件。 任何其他Campaign功能都不会受到影响。


## 常见问题解答 {#aws-faq}

* **为什么这是强制升级？**

  Adobe计划停用旧式数据中心，在该数据中心运行的Adobe Campaign实例必须转移到新的参考数据中心Amazon Web Services (AWS)。

  Managed Services云Adobe托管在Amazon Web Services (AWS)上，它是一个现代化、安全和优化的环境。 [进一步了解Amazon Web Services](https://aws.amazon.com/application-hosting/benefits/){target="_blank"}。

* **此迁移的目标客户是哪些客户？**

  所有Campaign v8客户和Campaign Classicv7混合、托管和Campaign Managed Services都将迁移其环境。 Campaign Standard客户也受到影响。

* **预计停机时间是多少？**

  迁移过程预计需要30分钟到60分钟之间，但每个迁移波次的长度可能因受影响的Campaign实例数而异。 当计划了迁移波次时，通知将包含预期的持续时间。

* **客户是否需要执行任何迁移操作？**

  无需执行任何操作，因为Adobe会自动运行迁移。

* **客户需要运行哪些验证？**

  此迁移不需要任何特定测试。 如果发现任何问题，请联系[Adobe客户关怀](https://experienceleague.adobe.com/zh-hans?support-solution=Campaign#support){target="_blank"}。


* **我可以请求更改计划的安全升级槽的日期/时间吗？**

  由于这是强制性迁移，因此我们无法适应对现有计划的修改。

如有任何其他问题，您可以联系[Adobe客户关怀](https://experienceleague.adobe.com/zh-hans?support-solution=Campaign#support){target="_blank"}。
