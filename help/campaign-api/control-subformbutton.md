---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '101'
ht-degree: 1%
---
# SubFormButton

用于打开子表单的按钮。

![SubFormButton控件](assets/button.f0aea09a.png)

## 属性

**backColor — 字符串**&#x200B;背景颜色（btnshadow，白色）。

**边框 — 字符串**&#x200B;更改控件轮廓样式（实线、双线、内缩、外凸、无）。

**discardReadOnly — 字符串**&#x200B;阻止将“只读”属性传播到子表单。

**font-size - integer**&#x200B;更改字体大小。

**img — 字符串**&#x200B;关联的图像。

**标签 — 按钮的字符串**&#x200B;标签。

**nolabel - string**&#x200B;允许您对齐标签列上的控件。

**prebuildSubForm — 字符串**&#x200B;在创建控件时初始化子表单。 此选项默认处于启用状态，但可以禁用它以加快初始显示。

**必需 — 布尔值**&#x200B;字段为必填字段。

## 备注

示例：

```xml
      <input type="subformbutton" label="Advanced parameters...">
  <form label=" Advanced parameters">
    <input xpath="@stopIfTooManyRejects"/>
    <input xpath="@traceMode"/>
  </form>
</input>
```
