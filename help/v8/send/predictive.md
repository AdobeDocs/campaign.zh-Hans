---
title: 预测用户参与度功能
description: 了解如何使用预测发送时间和参与度评分
feature: Send Time Optimization
role: User
level: Intermediate
source-git-commit: fdaf107fd22f439a728f32ceb8cfc13a8c5bc1ad
workflow-type: tm+mt
source-wordcount: '759'
ht-degree: 65%

---

# 发送时间优化和预测参与度评分{#optimize-message-delivery}

Adobe Campaign的发送时间优化和预测参与度评分由AI和机器学习提供支持，可以根据历史参与量度分析和预测开放率、最佳发送时间和可能的客户流失。

Adobe Campaign提供了两种新的机器学习模型： [预测发送时间优化](#predictive-send) 和 [预测参与度评分](#predictive-scoring). 这两种模型是机器学习模型，专门用于设计和交付更好的客户旅程。

>[!CAUTION]
>
>此功能并非作为产品的一部分现成可用。它仅适用于运行Adobe Campaign Classic v7或Adobe Campaign v8的Adobe Campaign Managed Cloud Services客户。
>
>实施需要咨询 Adobe。要了解更多信息，请联系您的Adobe代表。


## 预测发送时间优化{#predictive-send}

预测发送时间优化可针对电子邮件打开数或点击数以及推送消息打开数预测每个收件人用户档案的最佳发送时间。 对于每个收件人用户档案，分数表示每个工作日的最佳发送时间以及用于获取最佳结果的最佳发送工作日。

在预测发送时间优化模型中，有两个子模型：

* 打开的预测发送时间是必须向客户发送通信以最大化打开数的最佳时间

* 单击的预测发送时间是必须向客户发送通信以最大化点击数的最佳时间


**模型输入**:投放日志、跟踪日志和用户档案属性（非PII）

**模型输出**:发送消息的最佳时间（针对打开数和点击数）

输出详细信息:

* 计算一周 7 天内发送电子邮件的最佳时间（间隔时间为 1 小时）（例如：上午 9:00，上午 10:00，上午11:00）
* 该模型将指示一周中的最佳一天和当天的最佳时刻
* 每个最佳时间会计算两次：一次用于最大化打开率，一次用于最大化点击率
* 给定 16 个字段（14 个字段用于一周的天数，2 个字段用于整周）：
   * 发送电子邮件以优化星期一的点击数的最佳时间 - 值介于 0 和 23 之间
   * 发送电子邮件以优化星期一的打开数的最佳时间 - 值介于 0 和 23 之间
   * ...
   * 发送电子邮件以优化星期天的点击数的最佳时间 - 值介于 0 和 23 之间
   * 发送电子邮件以优化星期天的打开数的最佳时间 - 值介于 0 和 23 之间
   * ...
   * 发送电子邮件以优化整周的打开数的最佳日期 - 星期一到星期天
   * 发送电子邮件以优化整周的打开数的最佳时间 - 值介于 0 和 23 之间


预测发送时间优化存储在用户档案级别：

![](assets/sto-schema.png)


>[!NOTE]
>
>该模型需要至少一个月的数据才能产生显著效果。这些预测功能仅适用于电子邮件和推送渠道。


## 预测参与度评分 {#predictive-scoring}

预测参与度评分可预测收件人与消息互动的概率，以及在下次发送电子邮件后7天内选择退出（取消订阅）的概率。 这些概率会根据您对内容的预计参与级别进一步划分为多个分段：高、中或低。 这些模型还为客户提供取消订阅风险百分等级，以便了解特定客户的等级与其他客户的等级之间的关系。

预测参与度评分使您能够：

* **选择受众**：通过使用查询活动，可以选择要与特定消息交互的受众
* **排除受众**：通过使用查询活动，可以删除要取消订阅的受众
* **个性化**：根据参与度级别对消息进行个性化（高度参与的用户将获取与未参与的用户不同的消息）

此模型使用多个分数来指示：

* **打开参与度分数/点击参与度分数**：该值与订阅者将与特定消息进行交互（打开或点击）的概率匹配。值的范围为 0.0 到 1.0。
* **取消订阅概率**：该值与收件人从电子邮件渠道取消订阅（假设已打开一封电子邮件）的概率匹配。值的范围为 0.0 到 1.0。
* **保留级别**：该值将用户分为三个级别：低、中、高。高表示最有可能坚持使用该品牌，值为低表示可能取消订阅。
* **保留的百分等级**：根据取消订阅概率而定的用户档案等级。值的范围为 0.0 到 1.0。例如，如果保留百分比等级为 0.953，则此收件人很可能坚持使用该品牌，而取消订阅的可能性则小于所有收件人的 95.3%。

>[!NOTE]
>
>这些预测功能仅适用于电子邮件投放。
>
>该模型需要至少一个月的数据才能产生显著效果。

**模型输入**：投放日志、跟踪日志和特定用户档案属性

**模型输出**：用于描述用户档案分数和类别的用户档案属性