---
title: Campaign电子邮件发送基础架构升级
description: Campaign电子邮件发送基础架构升级
exl-id: f01e38ad-490e-4389-af5e-87beef533eb0
source-git-commit: 4c41e5d1fef1dcb3279a26f6025338e41525e6b3
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 1%

---

# Campaign电子邮件发送基础架构升级 {#migrate-infra-to-aws}

## 将升级哪些内容？{#aws-changes}

作为我们努力提供同类最佳用户体验的一部分，我们正在升级电子邮件投放服务。

## 您是否受影响？{#aws-impact}

此更改会影响：

* Adobe Campaign Classic Managed Services客户
* Adobe Campaign Managed Cloud Services客户
* Adobe Campaign Standard On-demand客户

## 何时进行此升级？{#aws-timeline}

开发和暂存环境升级开始于 **2023年10**.

生产环境升级开始于 **2024年1月**.

## 期待完成的任务{#impact}

* 每个升级波次的长度将因受影响的Campaign实例数而异。 在计划了生产升级波次后，通知中将包括预计持续时间。

* 在暂存环境和生产环境中，Campaign实例在升级窗口期间将无法发送邮件。 其他Campaign功能预计不会受到影响。

## 常见问题解答 {#aws-faq}

* **是否必须升级？**

  是的。 作为Campaign客户，您的电子邮件发送功能要求使用电子邮件发送基础架构。

* **此升级针对哪些客户？**

  上面引用的所有Campaign客户都将升级其环境。

* **预计停机时间是多少？**

  每个升级波次的长度可能因受影响的Campaign实例数而异。 在计划了生产升级波次后，通知将包含预计持续时间。

* **客户是否需要执行任何升级操作？**

  无需执行任何操作。 Adobe将管理升级过程，升级过程将自动运行。

* **客户需要什么测试？**

  我们预计客户不会针对此升级事件进行任何测试。 如果发现任何问题，请联系 [Adobe客户关怀](https://experienceleague.adobe.com/?support-solution=Campaign#support){target="_blank"}.


* **我是否可以请求更改计划安全升级插槽的日期/时间？**

  没有。我们无法容纳对现有计划请求的任何修改，因为这样可能会中断为其他客户分配的升级事件。

对于任何其他问题，您可以联系 [Adobe客户关怀](https://experienceleague.adobe.com/?support-solution=Campaign#support){target="_blank"}..
