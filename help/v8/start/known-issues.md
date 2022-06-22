---
title: Campaign v8已知问题
description: 最新Campaign版本中的已知问题
feature: Overview
role: Data Engineer
level: Beginner
hide: true
hidefromtoc: true
source-git-commit: 099d14ace04df1b98e03be283a6436f49f535958
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 1%

---

# 已知问题{#known-issues}

本页列出了 **最新Campaign v8版本**. 此外，还列出了Campaign v8附带的限制 [本页](known-limitations.md).


>[!NOTE]
>
>Adobe自行发布此已知问题列表。 它基于客户报表的数量、严重性和解决方法的可用性。 如果遇到的问题未列出，则可能不符合此页面中发布的条件。

## 更改数据源活动问题 {#issue-1}

### 说明

的 **更改数据源** 将数据从Campaign本地数据库传输到Snowflake云数据库时，活动失败。 在切换方向时，活动可能会产生问题。

### 复制步骤

1. 连接到客户端控制台并创建工作流。
1. 添加 **查询** 活动和 **更改数据源** 活动。
1. 在 **电子邮件**，字符串。
1. 运行工作流并右键单击过渡以查看群体：电子邮件记录显示为 `****`.
1. 检查工作流日志：the **更改数据源** 活动会将这些记录解释为数值。

### 解决方法

要将Snowflake从Cloud数据库传输到Campaign本地数据库并返回Snowflake，您必须使用两种不同的 **更改数据源** 活动。

### 内部引用

引用：NEO-45549


## 数据加载（文件）活动无法在服务器上上载文件 {#issue-2}

### 说明

Campaign服务器上的文件上传以100%进度停止，但永远不结束。

### 复制步骤

1. 连接到客户端控制台并创建工作流。
1. 添加 **数据加载（文件）** 活动并对其进行配置。
1. 选择 **在服务器上传** 选项。
1. 在本地计算机上选择文件，
1. 单击 **上传**

### 解决方法

无

### 内部引用

引用：NEO-47269