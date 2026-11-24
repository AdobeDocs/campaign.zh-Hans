---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '87'
ht-degree: 1%
---
# LinkListChoice

选择一个或多个实体。

## 属性

**backColor — 字符串**&#x200B;背景颜色（btnshadow，白色）。

**边框 — 字符串**&#x200B;更改控件轮廓样式（实线、双线、内缩、外凸、无）。

**dblClickAction — 字符串**&#x200B;双击时打开的表单的名称。

**font-size - integer**&#x200B;更改字体大小。

**标签 — 字符串**&#x200B;关联的标签。

**multiSelection — 布尔值**&#x200B;授权多项选择

**nolabel — 布尔值**&#x200B;隐藏关联的标签。

**readOnly — 布尔值**&#x200B;强制控件为只读。

**序列化 — 布尔值**&#x200B;保存用户配置中的最后选择。wu

**xpath-link — 列表的字符串**&#x200B;链接。

## 备注

示例：

```xml
      <input xpath="." type="linkListChoice" xpath-link="operator">
  <input xpath="[/]"  label="Operator or named right "/>
  <input xpath="@type"/>
  <input xpath="comment"/>
  <sysFilter>
    <condition expr="@type <> 1"/>
  </sysFilter>
  <orderBy>
    <node expr="@type"/>
  </orderBy>
</input>
```
