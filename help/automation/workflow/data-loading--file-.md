---
product: campaign
title: 数据加载（文件）
description: 进一步了解数据加载（文件）工作流活动
feature: Workflows, Data Management Activity
exl-id: 10351620-115c-4bd8-b216-e5ad6f205ef3
source-git-commit: 6464e1121b907f44db9c0c3add28b54486ecf834
workflow-type: tm+mt
source-wordcount: '1029'
ht-degree: 14%

---

# 数据加载（文件）{#data-loading-file}



## 使用 {#use}

的 **[!UICONTROL Data loading (File)]** 活动允许您直接访问外部数据源并在Adobe Campaign中使用。 事实上，定位操作所需的所有数据并非总是在Adobe Campaign数据库中找到：可在外部文件中使用。

要加载的文件可由过渡指定，或在执行此活动期间计算。 例如，它可以是客户10个最喜爱产品的列表，这些产品的购买在外部数据库中进行管理。

利用此活动的配置窗口的上部，可定义文件格式。 为此，请使用与要导入的文件格式相同的样例文件。 此文件可以存储在本地或服务器上。

>[!CAUTION]
>
>仅支持“平面”结构文件（例如CSV、TXT等）。 不建议使用XML格式。

![](assets/s_advuser_wf_etl_file.png)

您可以定义在文件导入期间执行的预处理，例如，这样就不必在服务器上解压缩文件（从而为解压缩的文件节省空间），而是在文件处理中包含解压缩。 选择 **[!UICONTROL Pre-process the file]** 选项，然后从3个选项中选择一个： **[!UICONTROL None]**, **[!UICONTROL Decompression]** (zcat)或 **[!UICONTROL Decrypt]** (gpg)。

![](assets/preprocessing-dataloading.png)

## 定义文件格式 {#defining-the-file-format}

加载文件时，将自动检测列格式以及每种数据类型的默认参数。 您可以修改这些默认参数，以指定要应用于数据的特定进程，尤其是当存在错误或空值时。

要执行此操作，请选择 **[!UICONTROL Click here to change the file format...]** 在 **[!UICONTROL Data loading (file)]** 活动。 随后将打开格式详细信息窗口。

![](assets/file_loading_columns_format.png)

然后，您可以修改文件的常规格式以及每列的格式。

利用常规文件格式，可定义列的识别方式（文件编码、使用的分隔符等）。

利用列格式，可定义每个列的值处理：

* **[!UICONTROL Ignore column]**：在数据加载过程中不处理此列。
* **[!UICONTROL Data type]**：指定每个列所需的数据类型。
* **[!UICONTROL Allow NULLs]**:指定如何管理空值。

   * **[!UICONTROL Adobe Campaign default]**：仅为数字字段生成错误，否则插入 NULL 值。
   * **[!UICONTROL Empty value allowed]**：授权空值。因此，会插入 NULL 值。
   * **[!UICONTROL Always populated]**：如果值为空，则生成错误。

* **[!UICONTROL Length]**:指定 **字符串** 数据类型。
* **[!UICONTROL Format]**:定义时间和日期格式。
* **[!UICONTROL Data transformation]**:定义是否需要对 **字符串**.

   * **[!UICONTROL None]**:导入的字符串未被修改。
   * **[!UICONTROL First letter in upper case]**:字符串中每个单词的第一个字母以大写开头。
   * **[!UICONTROL Upper case]**:字符串中的所有字符均以大写形式显示。
   * **[!UICONTROL Lower case]**:字符串中的所有字符均以小写形式显示。

* **[!UICONTROL White space management]**:指定字符串中是否需要忽略某些空格。 的 **[!UICONTROL Ignore spaces]** 值仅允许忽略字符串开头和结尾的空格。
* **[!UICONTROL Error processings]**：定义遇到错误时的行为。

   * **[!UICONTROL Ignore the value]**：忽略值。工作流执行日志中会生成警告。
   * **[!UICONTROL Reject line]**：不处理整个行。
   * **[!UICONTROL Use a default value in case of error]**：将导致错误的值替换为在 **[!UICONTROL Default value]** 字段中定义的默认值。
   * **[!UICONTROL Reject the line when there is no remapping value]**:除非为错误值定义了映射，否则不会处理整行(请参阅 **[!UICONTROL Mapping]** 选项)。
   * **[!UICONTROL Use a default value in case the value is not remapped]**:将导致错误的值替换为在 **[!UICONTROL Default value]** 字段，除非为错误值定义了映射(请参阅 **[!UICONTROL Mapping]** 选项)。

* **[!UICONTROL Default value]**：根据所选的错误处理指定默认值。
* **[!UICONTROL Mapping]**:此字段仅在列详细信息配置中可用（通过双击或通过列列表右侧的选项访问）。 这会在导入某些值时对其进行转换。 例如，您可以将“three”转换为“3”。

## 示例：收集数据并将其加载到数据库中 {#example--collecting-data-and-loading-it-in-the-database}

以下示例允许您每天在服务器上收集文件，加载其内容并根据其包含的信息更新数据库中的数据。 要收集的文件中包含客户可能已购买（超过3,000欧元）、要求退款或未购买任何商品就访问商店的信息。 根据此信息，将对数据库中的用户档案应用各种进程。

![](assets/s_advuser_load_file_sample_0.png)

1. 文件收集器允许您恢复存储在目录中的文件，具体取决于给定的频率。

   的 **[!UICONTROL Directory]** 选项卡包含有关要恢复的文件的信息。 在本例中，将恢复名称中包含单词“customers”且存储在服务器tmp/Data/files目录中的所有文本格式的文件。

   使用 **[!UICONTROL File collector]** 详见 [文件收集器](file-collector.md) 中。

   ![](assets/s_advuser_load_file_sample_1.png)

   的 **[!UICONTROL Schedule]** 选项卡，可安排执行收集器，即指定检查这些文件存在的频率。

   在本例中，我们希望在每个工作日的晚上9点触发收集器。

   ![](assets/s_advuser_load_file_sample_2.png)

   为此，请单击 **[!UICONTROL Change...]** 按钮，并配置计划。

   有关更多信息，请参阅 [调度程序](scheduler.md).

1. 然后，配置数据加载（文件）活动，以指示应如何读取收集的文件。 为此，请选择与要加载的文件具有相同结构的样例文件。

   ![](assets/s_advuser_load_file_sample_3.png)

   在此，文件包含五列：

   * 第一列包含与事件一致的代码：购买（3,000欧元以上），一次或多次购买时不得购买或退款。
   * 以下四列包含客户的名字、姓氏、电子邮件和帐号。

   要加载的文件的格式配置与在Adobe Campaign中数据导入期间定义的格式配置一致。

1. 在拆分活动中，根据 **事件** 列值。

   有关拆分活动的详情，请参阅一节。

   ![](assets/s_advuser_load_file_sample_4.png)

   对于每个子集，请在 **事件** 列。

   ![](assets/s_advuser_load_file_sample_5.png)

   的 **[!UICONTROL Split]** 因此，活动将包含以下信息：

   ![](assets/s_advuser_load_file_sample_6.png)

1. 然后，指定要针对每种类型的群体执行的进程。 在我们的示例中，我们将 **[!UICONTROL Update the data]** 在数据库中。 为此，请在 **[!UICONTROL Update data]** 活动。

   的 **[!UICONTROL Update data]** 活动在 [更新数据](update-data.md) 中。
