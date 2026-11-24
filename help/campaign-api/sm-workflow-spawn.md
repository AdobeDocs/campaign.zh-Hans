---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '120'
ht-degree: 3%
---
# 繁殖

从模板创建工作流实例，应用补丁然后启动此工作流。

```text
Number instanceId = Spawn ( String workflowId, XML patch )
```

## 参数

**workflowId**&#x200B;工作流模板的标识符或内部名称。

**patch**&#x200B;必须在执行之前与模型合并以获取实例的XML元素。 示例：

```xml
    <workflow>
      <activities>
        <extern name="notepad">
          <additionnalArgs><![CDATA[c:\xxx.txt]]>
          </additionnalArgs>
        </extern>
      </activities>
    </workflow>
    
```

此示例替换了“记事本”活动的参数。 如果不希望应用此修补程序，请使用空的&lt;workflow/>元素或空字符串。

## 返回值

从模板创建的实例的&#x200B;**instanceId**&#x200B;标识符。

## 备注

该命令以异步模式执行，在方法返回后不会立即生效。 工作流以调用操作员的帐户开始。

## 功能

**架构：** [xtk:workflow](s-xtk-workflow.md)

**静态：**

是
