---
title: 使用数据包
description: 使用数据包
feature: Data Management, Package Export/Import
role: Developer
level: Intermediate, Experienced
exl-id: bf1ae889-9c07-4acf-8fd0-55b57151bc47
version: Campaign v8, Campaign Classic v7
source-git-commit: a2efad26232cd380eea850a589b22b23928253e8
workflow-type: tm+mt
source-wordcount: '1941'
ht-degree: 1%

---

# 使用数据包{#data-packages}

## 包入门 {#gs-data-packages}

您可以使用数据包导出和导入平台自定义设置和数据。 包可以包含不同类型的配置和组件，无论是否进行了过滤。

在Campaign数据包中，Adobe Campaign数据库的实体会显示为XML文件。 在包中，每个实体由其所有数据表示。

**数据包**&#x200B;的原理是导出数据配置并将其集成到另一个Adobe Campaign环境中。 在此[部分](#data-package-best-practices)中了解如何维护一致的数据包集。

### 程序包类型 {#types-of-packages}

您可以在Adobe Campaign中使用三种类型的包：用户包、平台包和管理包。

* **用户包**&#x200B;允许您选择要导出的实体列表。 此类型的包管理依赖项并检查错误。
* **平台包**&#x200B;包含所有添加的技术资源（非标准）：架构、JavaScript代码等。
* **管理员包**&#x200B;包含所有添加的模板和业务对象（非标准）：模板、库等。

>[!CAUTION]
>
>**platform**&#x200B;和&#x200B;**admin**&#x200B;包包含要导出的预定义实体列表。 每个实体均链接到筛选条件，以便您删除已创建资源包的现成资源。

## 数据结构 {#data-structure}

数据包的描述是符合&#x200B;**xrk：navtree**&#x200B;数据架构语法的结构化XML文档，如以下示例所示：

```xml
<package>
  <entities schema="nms:recipient">
    <recipient email="john.smith@adobe.com" lastName="Smith" firstName="John">      
      <folder _operation="none" name="nmsRootFolder"/>      
      <company _operation="none" name="Adobe"/>
    </recipient>
  </entities>
  <entities schema="sfa:company">
    <company name="Adobe">
      <location city="London" zipCode="W11 2BQ"/>
    </company>
  </entities>
</package>
```

XML文档必须以`<package>`元素开始和结束。 后续的任何`<entities>`元素按文档类型分发数据。 `<entities>`元素包含包的数据，其格式为在&#x200B;**架构**&#x200B;属性中输入的数据架构的格式。 包中的数据不得包含基之间不兼容的内部键，例如自动生成的键（**autopk**&#x200B;选项）。

在我们的示例中，`folder`和`company`链接上的连接已被目标表上所谓的“高级”键替换：

```xml
<recipient>
  <folder _operation="none" name="nmsRootFolder"/>
  <company _operation="none" name="Adobe"/>
</recipient>
```

值为`none`的`operation`属性定义协调链接。

可以从任何文本编辑器手动构建数据包。 您必须确保XML文档的结构符合`xtk:navtree`数据架构。 客户端控制台有一个数据包导出和导入模块。

## 导出资源包 {#export-packages}

可通过三种不同的方式导出资源包：

* 使用&#x200B;**[!UICONTROL Package Export]**&#x200B;助手在单个包中导出一组对象。 [了解详情](#export-a-set-of-objects-in-a-package)
* 要导出&#x200B;**单个对象**，请右键单击该对象并选择&#x200B;**[!UICONTROL Actions > Export in a package]**。
* 使用&#x200B;**包定义**&#x200B;创建包结构，在其中添加稍后在包中导出的对象。 [了解详情](#manage-package-definitions)

导出资源包后，您可以将其和所有添加的实体导入到另一个Campaign实例中。

### 导出资源包中的一组对象 {#export-a-set-of-objects-in-a-package}

要导出数据包中的一组对象，请执行以下步骤：

1. 通过资源管理器的&#x200B;**[!UICONTROL Tools > Advanced > Export package...]**&#x200B;菜单浏览到资源包导出助手。
1. 选择[类型的包](#types-of-packages)。

   ![](assets/package_type.png)

1. 单击&#x200B;**添加**&#x200B;按钮选择要导出为包的实体。

   >[!CAUTION]
   >
   >如果导出&#x200B;**[!UICONTROL Offer category]**、**[!UICONTROL Offer environment]**、**[!UICONTROL Program]**&#x200B;或&#x200B;**[!UICONTROL Plan]**&#x200B;类型文件夹，请勿选择&#x200B;**xtk：folder**，因为可能会丢失一些数据。 为优惠类别选择与文件夹对应的实体： **nms：offerCategory**，为优惠环境选择与&#x200B;**nms：offerEnv**，为项目选择与&#x200B;**nms：program**&#x200B;对应的实体，为计划选择与&#x200B;**nms：plan**&#x200B;对应的实体。

   依赖关系机制控制实体导出顺序。 有关详细信息，请参阅[管理依赖项](#manage-dependencies)。

1. 单击&#x200B;**[!UICONTROL Next]**&#x200B;并根据要提取的文档类型定义过滤器查询。 必须为数据提取配置筛选子句。

   >[!NOTE]
   >
   >查询编辑器出现在[此部分](../../automation/workflow/query.md)中。

1. 单击&#x200B;**[!UICONTROL Next]**&#x200B;并选择导出数据的排序顺序。

1. 预览要提取的数据以检查配置。

1. 利用资源包导出助手的最后一页，可开始导出。 该数据将存储在&#x200B;**[!UICONTROL File]**&#x200B;字段中指示的文件中。

### 管理依赖项 {#manage-dependencies}

导出过程会跟踪各种导出元素之间的链接。 此机制由两个规则定义：

* 链接到具有`own`或`owncopy`类型完整性的链接的对象将导出到与导出的对象相同的包中。
* 链接到具有`neutral`或`define`类型完整性的链接的对象（定义的链接）必须单独导出。

>[!NOTE]
>
>在[此页面](database-links.md)中定义了链接到架构元素的完整性类型。

#### 导出营销活动 {#export-a-campaign}

以下是如何导出营销活动的示例。 要导出的营销活动包含：
* `MyTask`任务
* `campaignWorkflow`工作流位于以下文件夹中： **[!UICONTROL Administration > Production > Technical workflows > Campaign processes > MyWorkflow]**。

由于匹配的架构通过具有`own`类型完整性的链接连接，因此任务和工作流将在与营销活动相同的包中导出。

包内容为：

```xml
<?xml version='1.0'?>
<package author="Administrator (admin)" buildNumber="7974" buildVersion="7.1" img=""
label="" name="" namespace="" vendor="">
 <desc></desc>
 <version buildDate="2013-01-09 10:30:18.954Z"/>
 <entities schema="nms:operation">
  <operation duration="432000" end="2013-01-14" internalName="OP1" label="MyCampaign"
  modelName="opEmpty" start="2013-01-09">
   <controlGroup>
    <where filteringSchema=""/>
   </controlGroup>
   <seedList>
    <where filteringSchema="nms:seedMember"></where>
    <seedMember internalName="SDM1"></seedMember>
   </seedList>
   <parameter useAsset="1" useBudget="1" useControlGroup="1" useDeliveryOutline="1"
   useDocument="1" useFCPValidation="0" useSeedMember="1" useTask="1"
   useValidation="1" useWorkflow="1"></parameter>
   <fcpSeed>
    <where filteringSchema="nms:seedMember"></where>
   </fcpSeed>
   <owner _operation="none" name="admin" type="0"/>
   <program _operation="none" name="nmsOperations"/>
   <task end="2013-01-17 10:07:51.000Z" label="MyTask" name="TSK2" start="2013-01-16 10:07:51.000Z"
   status="1">
    <owner _operation="none" name="admin" type="0"/>
    <operation _operation="none" internalName="OP1"/>
    <folder _operation="none" name="nmsTask"/>
   </task>
   <workflow internalName="WKF12" label="CampaignWorkflow" modelName="newOpEmpty"
   order="8982" scenario-cs="Notification of the workflow supervisor (notifySupervisor)"
   schema="nms:recipient">
    <scenario internalName="notifySupervisor"/>
    <desc></desc>
    <folder _operation="none" name="Folder4"/>
    <operation _operation="none" internalName="OP1"/>
   </workflow>
  </operation>
 </entities>
</package>   
```

在具有`@pkgAdmin and @pkgPlatform`属性的架构中定义了包类型的隶属关系。 这两个属性都接收定义与包关联的条件的XTK表达式。

```xml
<element name="offerEnv" img="nms:offerEnv.png" 
template="xtk:folder" pkgAdmin="@id != 0">
```

最后，`@pkgStatus`属性允许您为这些元素或属性定义导出规则。 根据属性的值，可在导出的资源包中找到元素或属性。 此属性的三个可能值是：

* `never`：不导出字段/链接
* `always`：强制导出此字段
* `preCreate`：授权创建链接的实体

>[!NOTE]
>
>`preCreate`值仅允许用于链接类型事件。 它允许您创建或指向尚未在导出的资源包中加载的实体。

## 管理包定义 {#manage-package-definitions}

包定义允许您创建包结构，其中添加稍后将在单个包中导出的实体。 然后，您可以将此资源包和所有添加的实体导入另一个Campaign实例。

### 创建包定义 {#create-a-package-definition}

可从&#x200B;**[!UICONTROL Administration > Configuration > Package management > Package definitions]**&#x200B;菜单访问包定义。

要创建包定义，请单击&#x200B;**[!UICONTROL New]**&#x200B;按钮，然后填写包定义常规信息。

![](assets/packagedefinition_create.png)

然后，可以将实体添加到包定义中，并将其导出到XML文件包中。

**相关主题：**

* [将实体添加到包定义](#add-entities-to-a-package-definition)
* [配置包定义生成](#configure-package-definitions-generation)
* [从资源包定义导出资源包](#export-packages-from-a-package-definition)

### 将实体添加到包定义 {#add-entities-to-a-package-definition}

在&#x200B;**[!UICONTROL Content]**&#x200B;选项卡中，单击&#x200B;**[!UICONTROL Add]**&#x200B;按钮以选择要与包一起导出的实体。 [此部分](#export-a-set-of-objects-in-a-package)中介绍了选择实体时的最佳实践。

![](assets/packagedefinition_addentities.png)

实体可以直接从其在实例中的位置添加到包定义中。 为此请执行以下操作步骤：

1. 右键单击所需的实体，然后选择&#x200B;**[!UICONTROL Actions > Export in a package]**。

1. 选择&#x200B;**[!UICONTROL Add to a package definition]**，然后选择要向其中添加实体的包定义。

1. 实体已添加到包定义中，它将随包一起导出（请参阅[此部分](#export-packages-from-a-package-definition)）。

### 配置包定义生成 {#configure-package-definitions-generation}

可以从包定义&#x200B;**[!UICONTROL Content]**&#x200B;选项卡配置包生成。 为此，请单击&#x200B;**[!UICONTROL Generation parameters]**&#x200B;链接。

![](assets/packagedefinition_generationparameters.png)

* 使用&#x200B;**[!UICONTROL Include the definition]**&#x200B;选项包括当前在包定义中使用的定义。
* 使用&#x200B;**[!UICONTROL Include an installation script]**&#x200B;选项添加在导入包时执行的javascript脚本。 选中后，**[!UICONTROL Script]**&#x200B;选项卡将添加到包定义屏幕中。
* 使用&#x200B;**[!UICONTROL Include default values]**&#x200B;选项将所有实体属性的值添加到包中。

  默认情况下，为了避免较长的导出，不选中此选项。 这意味着默认情况下，具有默认值(“空字符串”、“0”和“false”（如果未在架构中另外定义）)的实体属性不会添加到包中，因此不会导出。

  >[!CAUTION]
  >
  >如果导入资源包的实例包含与资源包实体相同的实体（例如，外部ID相同），则不会更新其属性。 如果前实例中的属性具有默认值，则可能会发生这种情况，因为它们未包含在程序包中。 在这种情况下，选择&#x200B;**[!UICONTROL Include default values]**&#x200B;选项将阻止版本合并，因为前实例中的所有属性都将随包一起导出。

### 从资源包定义导出资源包 {#export-packages-from-a-package-definition}

要从资源包定义导出资源包，请执行以下步骤：

1. 选择要导出的包定义，单击&#x200B;**[!UICONTROL Actions]**&#x200B;按钮，然后选择&#x200B;**[!UICONTROL Export the package]**。
1. 检查导出文件的名称和位置。
1. 单击&#x200B;**[!UICONTROL Start]**&#x200B;按钮启动导出。

## 导入包 {#import-packages}

可通过客户端控制台的主菜单&#x200B;**[!UICONTROL Tools > Advanced > Import package]**&#x200B;访问包导入助手。

### 从文件安装包 {#install-a-package-from-a-file}

要导入现有的数据包，请执行以下步骤：

1. 通过客户端控制台的主菜单&#x200B;**[!UICONTROL Tools > Advanced > Import package]**&#x200B;访问导入助手。
1. 选择XML文件并单击&#x200B;**[!UICONTROL Open]**。

然后，要导入的包的内容将显示在编辑器的中间部分。

单击&#x200B;**[!UICONTROL Next]**&#x200B;和&#x200B;**[!UICONTROL Start]**&#x200B;启动导入。

### 安装内置软件包 {#install-a-standard-package}

内置软件包(又称 标准包)在配置Adobe Campaign时安装。 根据您的权限、部署模型和产品选项，您可以导入新的标准资源包。

请参阅您的许可协议，查看可以安装的软件包。

## 数据包最佳实践 {#data-package-best-practices}

本节介绍如何在项目的整个生命周期中以一致的方式组织数据包。


### 版本

您必须始终在同一平台版本中导入。 您必须检查是否在具有相同内部版本的两个实例之间部署包。 切勿强制导入，并始终先更新平台（如果内部版本不同）。

>[!IMPORTANT]
>
>Adobe不支持在不同版本之间导入。

注意架构和数据库结构。 导入包含架构的包后必须生成架构。

### 包类型 {#package-types}

首先定义不同类型的资源包。 仅使用四种类型：

**个实体**

* Adobe Campaign中的所有“xtk”和“nms”特定元素，如架构、表单、文件夹、投放模板等。
* 您可以将实体同时视为“管理员”和“平台”元素。
* 在Campaign实例上上传包时，包中不应包含多个实体。

如果您需要在新实例上部署配置，则可以导入所有实体包。

**功能**

此类型的包：
* 回答客户端要求/规范。
* 包含一个或多个功能。
* 应包含所有依赖项，以便能够在没有任何其他包的情况下运行功能。

**营销活动**

此包不是强制性的。 有时，为所有营销活动创建特定类型会很有用，即使营销活动被视为一项功能也是如此。

**更新**

配置功能后，可将其导出到其他环境中。 例如，可以将包从开发环境导出到测试环境。 在此测试中，发现了一个缺陷。 首先，它需要在开发环境中进行修复。 然后，将修补程序应用到测试平台。

第一个解决方案是再次导出整个功能。 但是，为了避免任何风险（更新不需要的元素），只包含修正值的套餐更加安全。

因此，我们建议创建一个“更新”包，其中只包含该特征的一个图元类型。

更新不仅可以是修复，也可以是实体/功能/营销活动包的新元素。 要避免部署整个包，可以导出更新包。

### 命名约定 {#data-package-naming}

现在已定义了类型，我们应该指定命名约定。 Adobe Campaign不允许为包规范创建子文件夹，这意味着数字是保持有条不紊的最佳解决方案。 数字前缀包名称。

例如，您可以使用以下约定：

* 实体：从1到99
* 功能：从100到199
* 促销活动：从200到299
* 更新：从5000到5999

#### 实体包顺序 {#entity-packages-order}

为帮助导入，应按照导入顺序对实体包进行排序。

例如：

* 001 — 架构
* 002 — 表单
* 003 — 图像
* 等等。

>[!NOTE]
>
>在&#x200B;**架构更新后，只应导入** Forms。


#### 包文档 {#package-documentation}

更新包时，应始终在描述字段中添加注释以详细说明任何修改和原因（例如，“添加新架构”或“修复缺陷”）。

最佳实践还包括输入更新日期。

>[!IMPORTANT]
>
>描述字段最多只能包含2.000个字符。
