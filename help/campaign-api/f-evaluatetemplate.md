---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '27'
ht-degree: 14%
---
# evaluateTemplate

评估JavaScript模板(&lt;%= ... %>)。

```text
evaluateTemplate (template)
```

## 参数

**模板**&#x200B;要评估的模板。

## 返回值

替换&lt;%和%>之间的表达式后的字符串。

## 备注

示例：

```javascript
      vars.filename = evaluateTemplate(activity.filename)
```

## 功能

**可用位置：**

* 工作流
