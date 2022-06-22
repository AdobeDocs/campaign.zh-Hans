---
title: Campaign v8已知问题
description: 最新Campaign版本中的已知问题
feature: Overview
role: Data Engineer
level: Beginner
hide: true
hidefromtoc: true
source-git-commit: e82ae1158926fb6335380626158089c6394377a1
workflow-type: tm+mt
source-wordcount: '428'
ht-degree: 3%

---

# 已知问题{#known-issues}

本页列出了 **最新Campaign v8版本**. 此外，还列出了Campaign v8附带的限制 [本页](known-limitations.md).


>[!NOTE]
>
>Adobe自行发布此已知问题列表。 它基于客户报表的数量、严重性和解决方法的可用性。 如果遇到的问题未列出，则可能不符合此页面中发布的条件。

## 更改数据源活动问题 {#issue-1}

### 说明{#issue-1-desc}

的 **更改数据源** 将数据从Campaign本地数据库传输到Snowflake云数据库时，活动失败。 在切换方向时，活动可能会产生问题。

### 复制步骤{#issue-1-repro}

1. 连接到客户端控制台并创建工作流。
1. 添加 **查询** 活动和 **更改数据源** 活动。
1. 在 **电子邮件**，字符串。
1. 运行工作流并右键单击过渡以查看群体：电子邮件记录显示为 `****`.
1. 检查工作流日志：the **更改数据源** 活动会将这些记录解释为数值。

### 错误消息{#issue-1-error}

```
04/13/2022 10:00:18 AM              Executing change data source 'Ok' (step 'Change Data Source')
04/13/2022 10:00:18 AM              Starting 1 connection(s) on pool 'nms:extAccount:ffda tractorsupply_mkt_stage8' (Snowflake, server='adobe-acc_tractorsupply_us_west_2_aws.snowflakecomputing.com', login='tractorsupply_stage8_MKT:tractorsupply_stage8')
04/13/2022 10:00:26 AM              ODB-240000 ODBC error: {*}Numeric value '{*}******{*}{{*}}' is not recognized\{*}   File 'wkf1285541_13_1_0_47504750#458318uploadPart0.chunk.gz', line 1, character 10140   Row 279, column "WKF1285541_13_1_0"["BICUST_ID":1]   If you would like to continue loading when a
04/13/2022 10:00:26 AM              n error is encountered, use other values such as 'SKIP_FILE' or 'CONTINUE' for the ON_ERROR option. For more information on loading options, please run 'info loading_data' in a SQL client. SQLState: 22018
04/13/2022 10:00:26 AM              WDB-200001 SQL statement 'COPY INTO wkf1285541_13_1_0 (SACTIVE, SADDRESS1, SADDRESS2, BICUST_ID, SEMAIL) FROM ( SELECT $1, $2, $3, $4, $5 FROM $$@BULK_wkf1285541_13_1_0$$) FILE_FORMAT = ( TYPE = CSV RECORD_DELIMITER = '\x02' FIELD_DELIMITER = '\x01' FIEL
04/13/2022 10:00:26 AM              D_OPTIONALLY_ENCLOSED_BY = 'NONE') ON_ERROR = ABORT_STATEMENT PURGE = TRUE' could not be executed.
```

### 解决方法{#issue-1-workaround}

要将Snowflake从Cloud数据库传输到Campaign本地数据库并返回Snowflake，您必须使用两种不同的 **更改数据源** 活动。

### 内部引用{#issue-1-ref}

引用：NEO-45549



## 由于反斜线，数据加载（文件）活动失败 {#issue-2}

### 说明{#issue-2-desc}

在通过Campaign加载活动将数据注入Snowflake云数据库时，该过程可能会因源文件中存在反斜线字符而失败。 字符串不会转义，并且数据在Snowflake时无法正确处理。

仅当反斜杠位于字符串的末尾时，才会出现此问题，例如：“巴克”。


### 复制步骤{#issue-2-repro}

1. 连接到客户端控制台并创建工作流。
1. 添加 **数据加载（文件）** 活动并对其进行配置。
1. 选择具有上述特征的本地文件。
1. 运行工作流并检查工作流日志以查看错误。


### 错误消息{#issue-2-error}

```
Error:
04/21/2022 4:01:58 PM     loading when an error is encountered, use other values such as 'SKIP_FILE' or 'CONTINUE' for the ON_ERROR option. For more information on loading options, please run 'info loading_data' in a SQL client. SQLState: 22000
04/21/2022 4:01:58 PM    ODB-240000 ODBC error: String '100110668547' is too long and would be truncated   File 'wkf1656797_21_1_3057430574#458516uploadPart0.chunk.gz', line 1, character 0   Row 90058, column "WKF1656797_21_1"["SCARRIER_ROUTE":13]   If you would like to continue
```

### 解决方法{#issue-2-workaround}

作为解决方法，请导出带双引号的文件，并在诸如“Barker\”之类的值周围添加一个文件格式选项FIELD_ONOPIL_CONTRIUDED_BY = &#39;&#39;

### 内部引用{#issue-2-ref}

引用：NEO-45549


## 数据加载（文件）活动无法在服务器上上载文件 {#issue-3}

### 说明{#issue-3-desc}

在Campaign服务器上上传文件时，使用 **数据加载（文件）** 活动时，该进程将在100%停止，但永远不会结束。

### 复制步骤{#issue-3-repro}

1. 连接到客户端控制台并创建工作流。
1. 添加 **数据加载（文件）** 活动并对其进行配置。
1. 选择 **在服务器上传** 选项。
1. 在本地计算机上选择文件，
1. 单击 **上传**


### 错误消息{#issue-3-error}

这个过程永远不会结束。

### 解决方法{#issue-3-workaround}

无

### 内部引用{#issue-3-ref}

引用：NEO-47269