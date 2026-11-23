---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 1%
---
# 列表

内存列表。

## 属性

**backColor — 字符串**&#x200B;背景颜色（btnshadow，白色）。

**边框 — 字符串**&#x200B;更改控件轮廓样式（实线、双线、内缩、外凸、无）。

**可编辑 — 布尔值**&#x200B;授权列表编辑。

**font-size - integer**&#x200B;更改字体大小。

**表单 — 字符串**&#x200B;编辑表单。

**img — 每行的字符串**&#x200B;图像。

**标签 — 字符串**&#x200B;关联的标签。

**nolabel — 布尔值**&#x200B;无标签。

**notitle — 布尔值**&#x200B;不显示列标题。

**noToolbar — 布尔值**&#x200B;隐藏工具栏。

**已排序 — 布尔值**&#x200B;授权列表计划。

**readOnly — 布尔值**&#x200B;强制控件为只读。

**toobarAlign — 字符串**&#x200B;水平\|垂直。

**toobarCaption — 工具栏中显示的string**&#x200B;标签。

**缩放 — 布尔值**&#x200B;显示编辑表单。

**zoomOnAdd - boolean**&#x200B;添加行时打开表单。

**xpathIndex - xpath**&#x200B;所选内容的索引将存储在此路径指定的位置。

**xpathSelection - xpath**&#x200B;将存储XPATH路径以到达所选元素的节点。

## 备注

示例1：

```xml
      <input type="list" xpath="dataTransferStep" nolabel="true" editable="false"
       zoom="true" form="xtk:exportSource" zoomOnAdd="true" img="xtk:script.bmp">
  <input xpath="@name" colSize="15"/>
  <input xpath="@active" editable="true" colSize="15"/>
</input>
```

示例2：

```xml
<input type="list" xpath="operator" zoom="true">
  <input xpath="@name" colSize="15"/>
  <form>
    <input xpath="@name"/>
  </form>
</input>
```
