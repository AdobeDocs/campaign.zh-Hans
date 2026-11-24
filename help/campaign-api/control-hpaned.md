---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 1%
---
# 已弃用

垂直排列多个容器。

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

每个子元素必须是一个容器。 由于height-percent属性，其每个子容器都可以指定要使用的总高度的百分比。 示例：

```xml
<container type="hpaned">
  <container label="Group 1" height-percent="25"/>
    <input .../>
  </container>
  <container label="Group 2" height-percent="75"/>
    <input .../>
  </container>
</container>
```
