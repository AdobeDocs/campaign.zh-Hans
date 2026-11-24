---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 2%
---
# 笔记本

用于显示多个页面的选项卡列表。

![笔记本控件](assets/notebook.3b531a46.png)

## 属性

**backColor — 字符串**&#x200B;背景颜色（btnshadow，白色）。

**名称 — 字符串**&#x200B;容器ID。

**左内边距 — integer**&#x200B;容器左侧的空间（以像素为单位）。

**右内边距 — integer**&#x200B;容器右侧的空格（以像素为单位）。

**padding-top — 容器上方的整数**&#x200B;空格（以像素为单位）。

**填充底部 — 整数**&#x200B;容器下以像素为单位的空间。

**边距 — 容器周围的整数**&#x200B;空格（以像素为单位）。

**readOnly - boolean**&#x200B;强制控件及其所有后代为只读。

**样式 — 字符串**&#x200B;平坦\|向下\|向上\|（默认）。

## 备注

每个子元素表示一个页面。 示例：

```xml
      <container colspan="2" style="down" type="notebook">
   <container label="Products">
     ...
   </container>

   <container colcount="3" xpath="link">
     ...
   </container>

   <container xpath="linkCollection">
     ...
   </container>
 </container>
```
