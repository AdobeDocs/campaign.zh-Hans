---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '54'
ht-degree: 29%
---
# generateRegisterHookScript

生成要在“appSubscriptionRcp”的“注册”事件期间调用的扩展脚本。

```text
String JSScriptStr = generateRegisterHookScript ( XML additionalXmlNodes )
```

## 参数

**additionalXmlNodes** XML节点包含其他参数和目标映射字段之间的链接。

## 返回值

**JSScriptStr** JS脚本，该脚本允许您将其他参数链接到目标映射中的字段。

## 功能

**架构：** [nms:mobileApp](s-nms-mobileapp.md)

**静态：**

是
