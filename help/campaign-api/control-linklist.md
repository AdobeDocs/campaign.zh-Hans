---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 0%
---
# 链接列表

用于编辑收藏集的控件。

![LinkList控件](assets/linklist.8b71bb0e.png)

## 属性

**addButton — 布尔值**&#x200B;显示添加按钮。 仅当启用了hideEditButtons选项时，此选项才有效。

**backColor — 字符串**&#x200B;背景颜色（btnshadow，白色）。

**边框 — 字符串**&#x200B;更改控件轮廓样式（实线、双线、内缩、外凸、无）。

**dblClickAction — 字符串**&#x200B;双击时打开的表单的名称。

**delButton - boolean**&#x200B;显示删除按钮。 仅当启用了hideEditButtons按钮时，此选项才有效。

**enumImage - string**&#x200B;用于显示每行图像的系统枚举的名称。

**font-size - integer**&#x200B;更改字体大小。

**表单 — 用于链接编辑的字符串**&#x200B;表单。

**hideEditButtons - boolean**&#x200B;隐藏添加、删除和编辑按钮。

**img — 字符串**&#x200B;图像。

**标签 — 字符串**&#x200B;关联的标签。

**nolabel — 布尔值**&#x200B;控件前面没有标签。

**noToolbar — 布尔值**&#x200B;隐藏工具栏。

**orderBy — 元素**&#x200B;列表计划。

**readOnly — 布尔值**&#x200B;强制控件为只读。

**sysFilter — 元素**&#x200B;列表筛选。

**toobarAlign — 字符串**&#x200B;水平\|垂直。

**toobarCaption — 工具栏中显示的string**&#x200B;标签。

**xpath-link — 列表的string**&#x200B;链接（请参阅组的示例）。

**xpathIndex - string**&#x200B;选择索引将存储在此路径指定的位置。

**xpathLinkEdit — 用于编辑的字符串**&#x200B;链接（请参阅组示例）。

**缩放 — 布尔值**&#x200B;授权链接编辑。

## 备注

示例：

```xml
      <input type="linkList" xpath="operator" enumImage="@type" nolabel="true">
  <input xpath="@name" label="Name" colSize="30"/>
  <input xpath="@login"/>
  <sysFilter>
    <condition expr="@type=1"/>
  </sysFilter>
</input>

<input type="linkList" xpath="operator" enumImage="@type" nolabel="true">
  <input xpath="@name" label="Name" colSize="30"/>
  <input xpath="@login"/>
  <form label="Add operators">
  <input xpath="." type="linkListChoice" xpath-link="recipient" img="nms:group.bmp">
  <input xpath="@lastName"/>
  <input xpath="@firstName"/>
  </input>
  </form>
</input>

<input type="linklist" xpath="rcpGrpRel" zoom="true" label="Recipients" form="nms:recipient"
       xpath-link="rcpGroup"
       xpathLinkEdit="recipient">
  <input xpath="recipient/@lastName"/>
  <input xpath="recipient/@firstName"/>
  <input xpath="recipient/@email"/>
  <input xpath="recipient/@phone"/>
</input>
```
