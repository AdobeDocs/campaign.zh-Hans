---
title: 限制 PI 视图
description: 了解如何限制PI视图
feature: PI, Privacy, Configuration
role: Developer
level: Intermediate, Experienced
exl-id: 1b833745-71d7-430d-ac7d-c830c78ea232
source-git-commit: 8ff207246bea1f476b37b1d4f2c79498362e7481
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 1%

---

# 限制 PI 视图{#restricting-pii-view}

## 概述 {#overview}

如果您希望营销用户能够访问数据记录，但不希望他们查看收件人的个人信息(PI)（如名字、姓氏或电子邮件地址），请应用以下准则来保护隐私，并防止常规营销活动操作人员滥用数据。

## 实现 {#implementation}

架构中添加了可以应用于任何元素或属性的特定属性，它补充了现有属性&#x200B;**[!UICONTROL visibleIf]**。 此属性是： **[!UICONTROL accessibleIf]**。 当包含与当前用户上下文相关的XTK表达式时，它可以利用&#x200B;**[!UICONTROL HasNamedRight]**&#x200B;或&#x200B;**[!UICONTROL $(login)]**，例如。

您可以找到收件人模式扩展的示例，该示例显示了以下用法：

```
<srcSchema desc="Recipient table (profiles" entitySchema="xtk:srcSchema" extendedSchema="xxl:nmsRecipientXl"
           img="nms:recipient.png" label="Recipients" labelSingular="Recipient"
           name="recipient" namespace="sec" xtkschema="xtk:srcSchema">
  <element desc="Recipient table (profiles" img="xxl:recipient.png" label="Recipients"
           labelSingular="Recipient" name="recipient">
    <attribute name="firstName" accessibleIf="$(login)=='admin'"/>
    <attribute name="lastName" visibleIf="$(login)=='admin'"/>
    <attribute name="email" accessibleIf="$(login)=='admin'"/>
  </element>
</srcSchema>
```

主要属性包括：

* **[!UICONTROL visibleIf]**：从元数据中隐藏字段，因此在架构视图、列选择或表达式生成器中无法访问这些字段。 但这不会隐藏任何数据，如果手动在表达式中输入字段名称，则会显示值。
* **[!UICONTROL accessibleIf]**：隐藏结果查询中的数据（用空值替换）。 如果visibleIf为空，则它将获得与&#x200B;**[!UICONTROL accessibleIf]**&#x200B;相同的表达式。

以下是在Campaign中使用此属性的后果：

* 在控制台中使用通用查询编辑器不会显示数据，
* 数据在概述列表和记录列表（控制台）中不可见。
* 在详细视图中，数据将变为只读。
* 数据只能在过滤器中使用（这意味着使用某些二分法，您仍然可以猜测值）。
* 使用受限字段构建的任何表达式都会受到限制：lower(@email)将变得与@email一样可访问。
* 在工作流中，您可以将受限列作为过渡的额外列添加到目标群体，但Adobe Campaign用户仍无法访问它。
* 当将目标群体存储在组（列表）中时，所存储的字段的特征与数据源相同。
* 默认情况下，JS代码无法访问数据。

>[!IMPORTANT]
>
>对关键参数（如组合键中的参数）使用&#x200B;**accessibleIf**&#x200B;属性可能会导致用户因隐藏数据而无法读取数据的错误。 这可能会导致查询失败或意外行为。 确保可以访问基本参数以防止出现中断。

## 推荐做法 {#recommendations}

在每次投放中，电子邮件地址都会复制到&#x200B;**[!UICONTROL broadLog]**&#x200B;和&#x200B;**[!UICONTROL forecastLog]**&#x200B;表中：因此，这些字段也需要受到保护。

以下是实施此操作的日志表扩展示例：

```
<srcSchema entitySchema="xtk:srcSchema" extendedSchema="nms:broadLogRcp" img="nms:broadLog.png"
           label="Recipient delivery logs" labelSingular="Recipient delivery log"
           name="broadLogRcp" namespace="sec" xtkschema="xtk:srcSchema">
  <element img="nms:broadLog.png" label="Recipient delivery logs" labelSingular="Recipient delivery log"
           name="broadLogRcp">
    <attribute accessibleIf="$(login)=='admin'" name="address"/>
  </element>
</srcSchema>
<srcSchema desc="Delivery messages being prepared." entitySchema="xtk:srcSchema"
           extendedSchema="nms:tmpBroadcast" img="" label="Messages being prepared"
           labelSingular="Message" name="tmpBroadcast" namespace="sec" xtkschema="xtk:srcSchema">
  <element desc="Delivery messages being prepared." label="Messages being prepared"
           labelSingular="Message" name="tmpBroadcast">
    <attribute accessibleIf="$(login)=='admin'" name="address"/>
  </element>
</srcSchema>
<srcSchema entitySchema="xtk:srcSchema" extendedSchema="nms:excludeLogRcp" img="nms:excludeLog.png"
           label="Recipient exclusion logs" labelSingular="Recipient exclusion log"
           name="excludeLogRcp" namespace="sec" xtkschema="xtk:srcSchema">
  <element img="nms:excludeLog.png" label="Recipient exclusion logs" labelSingular="Recipient exclusion log"
           name="excludeLogRcp">
    <attribute accessibleIf="$(login)=='admin'" name="address"/>
  </element>
</srcSchema>
```

>[!CAUTION]
>
>此限制仅适用于非技术用户，并且不会隔离数据：具有相关权限的技术用户可以检索数据。
