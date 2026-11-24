---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '92'
ht-degree: 3%
---
# 图标框

启用多页选择的图标列表。

![Iconbox控件](assets/iconbox.05daa4bf.png)

## 属性

**backColor — 字符串**&#x200B;背景颜色（btnshadow，白色）。

**名称 — 字符串**&#x200B;容器ID。

**左内边距 — integer**&#x200B;容器左侧的空间（以像素为单位）。

**右内边距 — integer**&#x200B;容器右侧的空格（以像素为单位）。

**padding-top — 容器上方的整数**&#x200B;空格（以像素为单位）。

**填充底部 — 整数**&#x200B;容器下以像素为单位的空间。

**边距 — 容器周围的整数**&#x200B;空格（以像素为单位）。

**readOnly - boolean**&#x200B;强制控件及其所有后代为只读。

## 备注

每个容器子元素表示一个页面。 示例：

```xml
<container name="iconbox" type="iconbox">
   <container colcount="3" label="Header">
     ...
   </container>
   <container img="ncm:ctprop.bmp" label="Intro">
     ...
   </container>
   <container img="ncm:subsection.bmp" label="Event">
     ...
   </container>
   <container img="ncm:book.bmp" label="Selection">
     ...
   </container>
   <container img="nms:contacts.bmp" label="Services">
     ...
   </container>
   <container img="nms:contacts.bmp" label="Mail footer ">
     ...
   </container>
 </container>
```
