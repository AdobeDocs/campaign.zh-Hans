---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 1%
---
# 树编辑

控件可查看和编辑分组在不同类别中的各种值。

![TreeEdit控件](assets/treeedit.253f1374.png)

## 属性

**backColor — 字符串**&#x200B;背景颜色（btnshadow，白色）。

**边框 — 字符串**&#x200B;更改控件轮廓样式（实线、双线、内缩、外凸、无）。

**可编辑 — 字符串**&#x200B;授权修改（默认为true）。

**font-size - integer**&#x200B;更改字体大小。

**标签 — 字符串**&#x200B;关联的标签。

**noImage — 字符串**&#x200B;隐藏列表中元素的图像。

**nolabel — 布尔值**&#x200B;隐藏关联的标签。

**readOnly — 布尔值**&#x200B;强制控件为只读。

## 备注

子元素的属性

* visibleIf：用于显示或隐藏元素的XTK条件。
* label：元素的标签。
* exprLabel：表达式形式的元素标签。
* xpath：元素的XPath。
* img：元素的图像。

输入子元素的属性

* 可编辑：可编辑的值。 默认值继承自根元素。

容器子元素的属性

* 折叠： true\|false显示或隐藏子元素。

示例：

```xml
<input nolabel="true" type="treeEdit">
  <container label="Text fields">
    <input xpath="@text1"/>
    <input xpath="@text2"/>
    <input xpath="@text3"/>
    <input xpath="@text4"/>
    <input xpath="@text5"/>
  </container>
  <container label="Boolean fields">
    <input xpath="@boolean1"/>
    <input xpath="@boolean2"/>
    <input xpath="@boolean3"/>
  </container>
</input>
    
```
