---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 7%
---
# SubmitNotification

从场景创建并提交通知。

```text
Number notificationId = SubmitNotification ( String scenarioName, XML target )
```

## 参数

**scenarioName**&#x200B;模板的内部名称

**目标**&#x200B;投放目标群体替换场景中的群体

## 返回值

**notificationId**&#x200B;通知标识符

## 备注

警告：此API并非旨在管理大量数据或实时工作。 它设计为每分钟最多可处理多个调用。 SubmitNotification会在投放分析期间阻止线程。 这可能需要几秒钟的时间。 “target”参数指定投放目标。 它将覆盖模板中指定的目标。 要传送到数据库中的目标，目标元素将使用以下语法：

```xml
<delivery>
  <targets>
    <deliveryTarget>
      <targetPart type='query' exclusion='false' ignoreDeleteStatus='false'>
        <where>
          <condition expr='[@folder-id] = 1050'/>
        </where>
      </targetPart>
    </deliveryTarget>
  </targets>
</delivery>
```

要传送到文件中的目标，请执行以下操作：

```xml
<delivery>
  <targets>
    <deliveryFile upload='false'>
      <name>c:/tmp/myFile.csv</name>
    </deliveryFile>
  </targets>
</delivery>
```

可以明确地定义目标（实际上是指用作目标的文件内容）：

```xml
<delivery>
  <targets fromExternalSource='true'>
    <externalSource>MsgId|ClientId|Title|Name|FirstName|Mobile|Email|Market_segment|Product_propensity1|Product_propensity2|Product_propensity3|Product_propensity4|Support_Number|Amount|Threshold1|
                    000001234|M.|Martin|Peter|0650201020|pmartin@neolane.com|1|A1|A2|A3|A4|E12|120000|100000
    </externalSource>
  </targets>
</delivery>
```

也可以使用属性“\_keepTemplateTarget”保留模板中定义的目标

```xml
<delivery>
  <targets _keepScenarioTarget='true'/>
</delivery>
```

## 功能

**架构：** [nms:delivery](s-nms-delivery.md)

**静态：**

是
