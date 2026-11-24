---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '76'
ht-degree: 2%
---
# 单选按钮

单选按钮允许您从多个选项中进行选择。 &lt;input>标记用于枚举可能的选项。

![单选按钮控件](assets/radio.11bc90a8.png)

## 属性

**backColor — 字符串**&#x200B;背景颜色（btnshadow，白色）。

**边框 — 字符串**&#x200B;更改控件的边框样式（实线、双线、内缩、外凸、无）。

**checkedValue — 链接到选择的字符串**&#x200B;值。

**font-size - integer**&#x200B;更改字体大小。

**标签 — 字符串**&#x200B;关联的标签。

**nolabel — 布尔值**&#x200B;隐藏关联的标签。

**readOnly — 布尔值**&#x200B;强制控件为只读。

## 备注

示例：

```xml
      <input type="RadioButton" xpath="@gender" checkedValue="0" label="Choice 1"/>
<input type="RadioButton" xpath="@gender" checkedValue="1" label="Choice 2"/>
<input type="RadioButton" xpath="@gender" checkedValue="2" label="Choice 3"/>
```
