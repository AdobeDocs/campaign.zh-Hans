---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 2%
---
# SubFormLink

打开子表单的链接。

![SubFormLink控件](assets/urlbutton.d1cf6f42.png)

## 属性

**backColor — 字符串**&#x200B;背景颜色（btnshadow，白色）。

**边框 — 字符串**&#x200B;更改控件轮廓样式（实线、双线、内缩、外凸、无）。

**discardReadOnly — 字符串**&#x200B;阻止将“只读”属性传播到子表单。

**font-size - integer**&#x200B;更改字体大小。

**img — 字符串**&#x200B;关联的图像。

**标签 — 字符串**&#x200B;按钮标签。

**nolabel - string**&#x200B;允许您将控件与标签列对齐。

**prebuildSubForm — 字符串**&#x200B;在创建控件时初始化子表单。 此选项默认处于启用状态，但可以禁用它以加快初始显示。

## 备注

示例：

```xml
      <input type="subformlink" label="Advanced parameters...">
  <form label=" Advanced parameters">
    <input xpath="@stopIfTooManyRejects"/>
    <input xpath="@traceMode"/>
  </form>
</input>
```
