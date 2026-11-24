---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 0%
---
# LinkEdit

用于编辑链接的控件。

![LinkEdit控件](assets/linkedit.7cb7bf14.png)

## 属性

**backColor — 字符串**&#x200B;背景颜色（btnshadow，白色）。

**边框 — 字符串**&#x200B;更改控件轮廓样式（实线、双线、内缩、外凸、无）。

**choiceButton — 布尔值**&#x200B;隐藏或显示选择按钮（默认隐藏）。

**computeStringExpr - string**&#x200B;计算字段表达式。

**computestringKey - string**&#x200B;更新计算字符串而非外键。

**computeStringAlias - string**&#x200B;计算字符串别名。

**createMode - string**&#x200B;如果链接不存在（无，内联），则使用默认编辑模式创建链接。

**externalKey — 布尔值**&#x200B;使用外部密钥。

**font-size - integer**&#x200B;更改字体大小。

**表单 — 字符串**&#x200B;强制链接编辑表单。

**标签 — 字符串**&#x200B;关联的标签。

**loadEntityOnChange — 布尔值**&#x200B;在链接更改时重新加载实体。

**强制 — 布尔值**&#x200B;拒绝空值。

**noAutoComplete — 布尔值**&#x200B;禁用自动完成模式。

**noEdition — 布尔型**&#x200B;无法修改链接。

**nolabel — 布尔值**&#x200B;隐藏关联的标签。

**notifyPathList - string**&#x200B;在上下文中加载的XPath列表（用逗号与链接元素分开）。

**noTransaction — 布尔值**&#x200B;禁用事务模式。

**noZoom — 布尔值**&#x200B;无链接编辑表单。

**orderBy — 元素**&#x200B;选择计划。

**readOnly — 布尔值**&#x200B;强制控件为只读。

**必需 — 布尔值**&#x200B;字段为必填字段。

**架构 — 链接的字符串**&#x200B;架构。

**序列化 — 布尔值**&#x200B;保存用户配置中的最后一个选择。

**sysFilter — 元素**&#x200B;选择限制。

**xpathMandatory - string**&#x200B;指向布尔属性的路径，该属性指示链接是否可以为空。

## 备注

示例：

```xml
<input xpath="operator">
  <sysFilter>
    <condition expr="@type= 1/>
  </sysFilter>
  <orderBy>
    <node expr="@name"/>
  </orderBy>
</input>

<input xpath="/tmp/recipient" type="linkEdit" label="Recipient"
       schema="nms:recipient">
```
