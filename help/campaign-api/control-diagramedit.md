---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '88'
ht-degree: 1%
---
# 图编辑

此控件用于编辑图，如工作流或调查。

![DiagramEdit控件](assets/diagramedit.d750db7e.png)

## 属性

**backColor — 字符串**&#x200B;背景颜色（btnshadow，白色）。

**边框 — 字符串**&#x200B;更改控件轮廓样式（实线、双线、内缩、外凸、无）。

**标签 — 字符串**&#x200B;关联的标签。

**nolabel — 布尔值**&#x200B;将标签显示为帮助气泡。

**readOnly — 布尔值**&#x200B;强制控件为只读。

## 备注

工具栏可以个性化，此控件的每个子元素都会与工具栏中的其他按钮相匹配。

```xml
<input type="diagramEdit" xpath=".">
  <input type="separator"/>
  <input img="xtk:properties.png" label="Properties" resetForm="true" prebuildSubForm="true">
    <form name="properties" label="Properties">
      <input xpath="/tmp/@test"/>
    </form>
  </input>
  <input type="separator"/>
  <input img="nms:prepare.png" label="Publish" checkModify="true">
    <form name="properties" label="Properties">
      <input xpath="/tmp/@test"/>
    </form>
  </input>
</input>
```

有关工具栏中按钮的更多信息，请参阅SubFormButton控件文档。
