---
title: Campaign中的密钥管理
description: 密钥管理入门
exl-id: ef06cb6b-1b25-4dbe-8fd0-f880ec9d645b
source-git-commit: f071fc227dac6d72873744ba56eb0b4b676de5dd
workflow-type: tm+mt
source-wordcount: '676'
ht-degree: 2%

---

# 密钥管理和唯一性 {#key-management}

在Campaign v8中，主键是通用唯一ID标识符(UUID)，该标识符是字符串。 要创建此UUID，架构的主要元素必须包含 **autouuid** 和 **奥托普** 属性设置为 **true**.

Adobe campaign v8 以 Snowflake 为核心数据库。Snowflake数据库的分布式架构不提供管理表中密钥的唯一性的机制：最终用户负责确保Adobe Campaign数据库中密钥的一致性。

要保持关系数据库的一致性，必须避免对键值（特别是对主键值）重复。 主键上的重复项会导致数据管理工作流活动出现问题，例如 **查询**, **协调**, **更新数据**，等等。

作为最佳实践，Adobe建议采用 [检测](#detect-duplicates) 和 [正确](#correct-duplicates) 策略（如果重复键值已加载到数据库中）。

## 检测重复项{#detect-duplicates}

Campaign提供了新护栏，用于在投放准备期间自动从受众中删除任何重复的UUID。 此新机制可防止在准备投放时发生任何错误。

>[!CAUTION]
>
>重复的键不限于UUID。 在中，可能会发生这种情况，包括在自定义表中创建的自定义键。

作为最终用户，您可以在投放日志中查看以下信息：由于重复的键值，某些收件人可能会从主目标中排除。 在这种情况下，将显示以下警告： `Exclusion of duplicates (based on the primary key or targeted records)`.

![](assets/delivery-log-duplicates.png)

发生此情况时，您可以创建一个工作流以标识重复的键。 然后，您便能够更正这些键。 要执行此操作，请执行以下步骤：

1. 创建新工作流。

   ![](assets/new-wf.png)

1. 添加 **查询** 活动
1. 选择 **收件人** 表

   ![](assets/add-query-on-rcp.png)

1. 添加 **重复数据删除** 活动，并删除主键(UUID)上的重复项。 只保留一个副本，然后检查  **生成补码** 用于为副本创建叫客过渡的选项。

   ![](assets/deduplicate.png)

1. 使用列表更新活动将重复项保存到列表中。

   ![](assets/list-update.png)

现在，您可以直接从列表访问复制的收件人。 即使过渡只包含重复的行之一，所有重复项都将记录到列表中。


## 更正重复项{#correct-duplicates}

更正重复项要求客户更新Campaign数据。 操作类型与重复项和实施的性质紧密绑定。 我们可能会面临多种情况，这些情况需要不同的缓解策略（删除、合并或更新）。

>[!IMPORTANT]
>
>复制的主键会阻止您使用内置的工作流活动选择或更新一个特定行。 由于重复的UUID，重复数据删除将失败，并且可能会影响数据库的完整性。 因此，强烈建议更正重复项。

例如：

* **用例1**  — 具有相同UUID和相同用户档案信息（相同的电子邮件、名字等）的重复收件人 :收件人看起来像“真实”的重复项，缓解措施可能是只删除其中一个重复项。
另一种方法是将一个收件人的信息合并到另一个收件人的信息中。

* **用例2**  — 具有相同UUID但配置文件信息（电子邮件、名字等）的重复收件人:此时，似乎有不同的用户档案，您可能希望将这两个用户档案都保留在Campaign数据库中，这意味着我们可能只希望更新其中一个用于生成新UUID的重复项。 [在本示例中了解更多信息](#deduplicate-sample).

根据您的缓解策略，您始终可以从另一个工作流中查询列表，然后根据需要应用更新。 如需更多指导，请联系Adobe。

### 重复数据删除示例{#deduplicate-sample}

如果收件人重复，您可以在Campaign数据库中保留这两个记录。 在这种情况下，您需要使用新的UUID来更新其中一个UUID。

因此，要在云数据库上运行SQL更新查询，可以使用 **SQL数据管理** 工作流活动并执行以下SQL更新：

```sql
update nmsrecipient set urecipientid = uuid_string()
where semail = 'bretta37@adobe.com'
and urecipientid = 'c04d93f2-6012-4668-b523-88db1262cd46';
```

![](assets/sql-data-management.png)

在使用新的UUID更新选定的行后，您可以从界面中检查已更新的行，并注意到UUID已按预期进行更新。 您还可以通过运行 **检测重复项** 工作流 [如下所述](#detect-duplicates).
