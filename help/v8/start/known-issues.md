---
title: Campaign v8已知问题
description: 最新Campaign版本中的已知问题
feature: Overview
role: Data Engineer
level: Beginner
hide: true
hidefromtoc: true
exl-id: 89a4ab6c-de8e-4408-97d2-8b8e574227f9
source-git-commit: 09db0cc1a14bffefe8d1b8d0d5a06d5b6517a5bb
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 2%

---

# 已知问题{#known-issues}

此页面列出了&#x200B;**最新Campaign v8版本**&#x200B;中发现的已知问题。 此外，Campaign v8的限制在此页面](ac-guardrails.md)中列出[。


>[!NOTE]
>
>Adobe会自行发布此已知问题列表。 它基于客户报告的数量、严重性和变通方案可用性。 如果您遇到的问题未列出，则该问题可能不符合在此页面中发布的条件。

## Campaign v8.3.8{#8.3-issues}

### 更改数据Source活动问题 {#issue-2}

#### 说明{#issue-2-desc}

当使用Campaign **查询**&#x200B;和&#x200B;**更改数据Source**&#x200B;活动将数据注入Snowflake云数据库时，如果数据中存在反斜线字符，该过程将失败。 源字符串未转义，并且数据在Snowflake时无法正确处理。

仅当反斜杠字符位于字符串的结尾时，才会发生此问题，例如： `Barker\`。


#### 复制步骤{#issue-2-repro}

1. 连接到客户端控制台并创建工作流。
1. 添加&#x200B;**查询**&#x200B;活动并进行配置。
1. 选择具有上述特征的数据。
1. 添加&#x200B;**更改数据Source**&#x200B;活动，并将其配置为选择Snowflake云数据库。
1. 运行工作流并检查工作流日志以查看错误。


#### 错误消息{#issue-2-error}

```sql
Error:
04/21/2022 4:01:58 PM     loading when an error is encountered, use other values such as 'SKIP_FILE' or 'CONTINUE' for the ON_ERROR option. For more information on loading options, please run 'info loading_data' in a SQL client. SQLState: 22000
04/21/2022 4:01:58 PM    ODB-240000 ODBC error: String '100110668547' is too long and would be truncated   File 'wkf1656797_21_1_3057430574#458516uploadPart0.chunk.gz', line 1, character 0   Row 90058, column "WKF1656797_21_1"["SCARRIER_ROUTE":13]   If you would like to continue
```

#### 解决方法{#issue-2-workaround}

解决方法是排除字符串末尾包含反斜杠字符的数据，或将其从源文件中删除。


#### 内部引用{#issue-2-ref}

引用：NEO-45549


### 数据加载（文件）活动无法在服务器上上传文件 {#issue-3}

#### 说明{#issue-3-desc}

在具有&#x200B;**数据加载（文件）**&#x200B;活动的Campaign服务器上传文件时，该进程将以100%停止，但永不结束。

#### 复制步骤{#issue-3-repro}

1. 连接到客户端控制台并创建工作流。
1. 添加&#x200B;**数据加载（文件）**&#x200B;活动并进行配置。
1. 选择&#x200B;**上载服务器**&#x200B;选项。
1. 选择本地计算机上的文件，
1. 单击&#x200B;**上传**


#### 错误消息{#issue-3-error}

这个过程永远不会结束。

#### 解决方法{#issue-3-workaround}

解决方法是使用旧版的客户端控制台。 然后，您便能够将文件上传到服务器上。

作为Campaign管理员，您可以在[Adobe软件分发](https://experience.adobe.com/#/downloads/content/software-distribution/en/campaign.html?1_group.propertyvalues.property=.%2Fjcr%3Acontent%2Fmetadata%2Fdc%3Aversion&amp;1_group.propertyvalues.operation=equals&amp;1_group.propertyvalues.0_values=target-version%3Acampaign%2F8&amp;orderby=%40jcr%3Acontent%2Fjcr%3AlastModified&amp;orderby.sort=desc&amp;layout=list&amp;p.offset=0&amp;p.limit=4){target="_blank"}中下载Campaign v8.3.1客户端控制台。

在此页面](https://experienceleague.adobe.com/docs/experience-cloud/software-distribution/home.html?lang=zh-Hans){target="_blank"}中了解如何访问Adobe软件分发[。

在本页](connect.md)中了解如何升级您的客户端控制台[

#### 内部引用{#issue-3-ref}

引用：NEO-47269

