---
product: campaign
title: 在网页中添加选件
description: 了解如何在网页中添加选件
exl-id: 1eb0775a-5da9-4a27-aa7b-339372748f9c
source-git-commit: 213a10fea36b3b08c1dd8525084d212e191b2fc7
workflow-type: tm+mt
source-wordcount: '1455'
ht-degree: 0%

---

# 在网页中添加选件{#add-an-offer-in-web}

要在网页中调用选件引擎，请将对JavaScript代码的调用直接插入到该页面中。 此调用会返回目标元素中的选件内容。

调用URL的脚本如下所示：

```
<script id="interactionProposalScript" src="https://<SERVER_URL>/nl/interactionProposal.js?env=" type="text/javascript"></script>
```

“**env**“参数接收专用于匿名交互的实时环境的内部名称。

要演示选件，我们需要在Adobe Campaign中创建环境和选件空间，然后配置HTML页面。

以下用例详细介绍了通过JavaScript集成选件的可能选项。

## 选项1:HTML模式 {#html-mode}

### 提供匿名优惠 {#presenting-an-anonymous-offer}

**步骤1:准备优惠引擎**

1. 打开Adobe Campaign界面并准备匿名环境。
1. 创建链接到匿名环境的选件空间。
1. 创建链接到选件空间的选件及其表示形式。

**步骤2:更新HTML页面的内容**

HTML页面必须包含一个具有@id属性的元素，且该元素的值为已创建选件空间的内部名称(“i_internal name space”)。 该选件将通过交互插入到此元素中。

在本例中，@id属性接收“i_SPC12”值，其中“SPC12”是之前创建的选件空间的内部名称：

```
<div id="i_SPC12"></div>
```

在我们的示例中，用于调用脚本的URL如下所示（“OE3”是实时环境的内部名称）：

```
<script id="interactionProposalScript" src="https://instance.adobe.org:8080/nl/interactionProposal.js?env=OE3" type="text/javascript"></script>
```

>[!CAUTION]
>
>的 `<script>` 标记不得自闭。

此静态调用将自动生成一个动态调用，其中包含选件引擎所需的所有参数。

此行为允许您在同一页面上使用多个选件空间，以便通过对选件引擎的一次调用进行管理。

**步骤3:在HTML页面中显示结果**

选件表示的内容由选件引擎返回到HTML页面：

```
<div id="banner_header">
 <div id="i_SPC12">
   <table>
    <tbody>
        <tr>
            <td><h3>Fly to Japan!</h3></td>
        </tr>
        <tr>
            <td><img width="150px" src="https://instance.adobe.org/res/Track/874fdaf72ddc256b2d8260bb8ec3a104.jpg"></td>
            <td>
            <p>Discover Japan for 2 weeks at an unbelievable price!!</p>
            <p><b>2345 Dollars - All inclusive</b></p>
        </td>
        </tr>
    </tbody>
    </table>
 </div>
<script src="https://instance.adobe.org:8080/nl/interactionProposal.js?env=OE3" id="interactionProposalScript" type="text/javascript"></script>
</div>
```

### 提供已识别的选件 {#presenting-an-identified-offer}

要向已识别的联系人展示选件，该过程与详细过程类似 [在此部分中](#presenting-an-anonymous-offer).

在网页内容中，您需要添加以下脚本，以便在调用选件引擎期间识别联系人：

```
<script type="text/javascript">
  interactionTarget = <contact_identifier>;
</script>
```

1. 转到网页将调用的选件空间，单击 **[!UICONTROL Advanced parameters]** 并添加一个或多个标识键。

   ![](assets/interaction_htmlmode_001.png)

   在此示例中，标识键是复合的，因为它既基于电子邮件，也基于收件人名称。

1. 在网页显示期间，脚本评估允许您将收件人ID传递到选件引擎。 如果ID是复合的，则键值会按与高级设置中相同的顺序显示，并且会由 | 。

   在以下示例中，联系人已登录到网站，并在调用选件引擎时因其电子邮件和姓名而被识别。

   ```
   <script type="text/javascript">
     interactionTarget = myEmail|myName;
   </script>
   ```

### 使用HTML渲染函数 {#using-an-html-rendering-function}

要自动生成HTML选件表示，您可以使用渲染函数。

1. 转到选件空间，然后单击 **[!UICONTROL Edit functions]** 链接。
1. 选择 **[!UICONTROL Overload the HTML rendering function]**。
1. 转到 **[!UICONTROL HTML rendering]** 选项卡，并插入与选件空间中为选件内容定义的字段匹配的变量。

   ![](assets/interaction_htmlmode_002.png)

   在此示例中，选件以网页横幅的形式显示，由可单击图像和与选件内容中定义的字段相匹配的标题组成。

## 选项2:XML模式 {#xml-mode}

### 提供优惠 {#presenting-an-offer}

Campaign **互动** 模块允许您将XML节点返回到HTML页，该页调用选件引擎。 此XML节点可以由客户端开发的函数进行处理。

对选件引擎的调用如下所示：

```
<script type="text/javascript" id="interactionProposalScript" src="https://<SERVER_URL>/nl/interactionProposal.js?env=&cb="></script>
```

* “**env**“参数接收实时环境的内部名称。

* “**cb**&quot;参数接收函数的名称，该函数将读取由包含（回调）命题的引擎返回的XML节点。 此参数是可选的。

* “**t**“参数接收目标的值，仅用于已标识的交互。 此参数还可以与 **interactionTarget** 变量。 此参数是可选的。

* “**c**&quot;参数接收类别的内部名称列表。 此参数是可选的。

* “**th**&quot;参数接收主题列表。 此参数是可选的。

* “**gctx**“参数接收到整个页面的调用数据全局（上下文）。 此参数是可选的。

返回的XML节点如下所示：

```
<propositions>
 <proposition id="" offer-id="" weight="" rank="" space="" div=""> //proposition identifiers
   ...XML content defined in Adobe Campaign...
 </proposition>
 ...
</propositions>
```

以下用例详细介绍了在Adobe Campaign中执行以启用XML模式的配置，然后在HTML页面中显示对引擎的调用结果。

1. **创建环境和选件空间**

   有关创建环境的更多信息，请参阅 [本页](interaction-env.md).

   有关创建优惠空间的更多信息，请参阅 [本页](interaction-offer-spaces.md).

1. **扩展选件架构以添加新字段**

   此架构将定义以下字段：标题2和价格。

   示例中架构的名称为 **cus:offer**

   ```
   <srcSchema _cs="Marketing offers (cus)" created="2013-01-18 17:14:20.762Z" createdBy-id="0"
              desc="" entitySchema="xtk:srcSchema" extendedSchema="nms:offer" img="nms:offer.png"
              label="Marketing offers" labelSingular="Marketing offers" lastModified="2013-01-18 15:20:18.373Z"
              mappingType="sql" md5="F14A7AA009AE1FCE31B0611E72866AC3" modifiedBy-id="0"
              name="offer" namespace="cus" xtkschema="xtk:srcSchema">
     <createdBy _cs="Administrator (admin)"/>
     <modifiedBy _cs="Administrator (admin)"/>
     <element img="nms:offer.png" label="Marketing offers" labelSingular="Marketing offer"
              name="offer">
       <element label="Content" name="view">
         <element label="Price" name="price" type="long" xml="true"/>
         <element label="Title 2" name="title2" type="string" xml="true"/>
   
         <element advanced="true" desc="Price calculation script." label="Script price"
                  name="price_jst" type="CDATA" xml="true"/>
         <element advanced="true" desc="Title calculation script." label="Script title"
                  name="title2_jst" type="CDATA" xml="true"/>
       </element>
     </element>
   </srcSchema>
   ```

   >[!CAUTION]
   >
   >每个元素需要定义两次。 CDATA(&quot;_jst&quot;)类型元素可以包含个性化字段。
   >
   >不要忘记更新数据库结构。

   您可以扩展选件架构，以批量和统一模式以及任何格式(文本、HTML和XML)添加新字段。

1. **扩展选件公式以编辑新字段并修改现有字段**

   编辑 **选件(nsm)** 输入表单。

   在“视图”部分，插入两个新字段，其中包含以下内容：

   ```
   <input label="Title 2" margin-right="5" prebuildSubForm="false" type="subFormLink" xpath="title2_jst">
        <form label="Edit title 2" name="editForm" nothingToSave="true">
            <input nolabel="true" toolbarAlign="horizontal" type="jstEdit" xpath="." xpathInsert="/ignored/customizeTitle2">
            <container>
                <input menuId="viewMenuBuilder" options="inbound" type="customizeBtn" xpath="/ignored/customizeTitle2"/>
            </container>
            </input>
        </form>
    </input>
    <input nolabel="true" type="edit" xpath="title2_jst"/>
    <input label="Price" margin-right="5" prebuildSubForm="false" type="subFormLink" xpath="price_jst">
        <form label="Edit price" name="editForm" nothingToSave="true">
        <input nolabel="true" toolbarAlign="horizontal" type="jstEdit" xpath="." xpathInsert="/ignored/customizePrice">
            <container>
                <input menuId="viewMenuBuilder" options="inbound" type="customizeBtn" xpath="/ignored/customizePrice"/>
            </container>
        </input>
        </form>
    </input>
    <input colspan="2" label="Prix" nolabel="true" type="number" xpath="price_jst"/>
   ```

   注释掉目标URL字段：

   ![](assets/interaction_xmlmode_form_001.png)

   >[!CAUTION]
   >
   >( `<input>`)表单必须指向在创建的架构中定义的CDATA类型元素。

   选件表示表单中的呈现如下所示：

   ![](assets/interaction_xmlmode_form.png)

   的 **[!UICONTROL Title 2]** 和 **[!UICONTROL Price]** 已添加字段，并且 **[!UICONTROL Destination URL]** 字段。

1. **创建优惠**

   有关创建选件的更多信息，请参阅 [本页](interaction-offer.md).

   在以下用例中，选件的输入方式如下：

   ![](assets/interaction_xmlmode_offer.png)

1. **批准选件**

   批准选件或由其他人批准该选件，然后在上一步创建的选件空间上将其激活，以便该选件在链接的实时环境中可用。

1. **引擎调用和HTML页面上的结果**

   对HTML页面中选件引擎的调用如下所示：

   ```
   <script id="interactionProposalScript" src="https://<SERVER_URL>/nl/interactionProposal.js?env=OE7&cb=alert" type="text/javascript">
   ```

   “**env**“ parameter（参数）是实时环境的内部名称。

   “**cb**“参数”是函数的名称，需要解释引擎返回的XML节点。 在本例中，调用的函数将打开一个模式窗口(alert()函数)。

   选件引擎返回的XML节点如下所示：

   ```
   <propositions>
    <proposition id="a28002" offer-id="10322005" weight="1" rank="1" space="SPC14" div="i_SPC14">
     <xmlOfferView>
      <title>Travel to Russia</title>
      <price>3456</price>
      <description>Discover this vacation package!INCLUDES 10 nights. FEATURES buffet breakfast daily. BONUS 5th night free.</description>
      <image>
       <path>https://myinstance.com/res/Track/ae1d2113ed732d58a3beb441084e5960.jpg</path>
       <alt>Travel to Russia</alt>
      </image>
     </xmlOfferView>
    </proposition>
   </propositions>
   ```

### 使用渲染函数 {#using-a-rendering-function-}

可以使用XML渲染函数创建选件演示文稿。 此函数将修改在调用选件引擎期间返回到HTML页面的XML节点。

1. 转到选件空间，然后单击 **[!UICONTROL Edit functions]** 链接。
1. 选择 **[!UICONTROL Overload the XML rendering function]**。
1. 转到 **[!UICONTROL XML rendering]** 选项卡，然后插入所需的函数。

   函数可以如下所示：

   ```
   function (proposition) {
     delete proposition.@id;
     proposition.@newAttribute = "newValue";
   } 
   ```

![](assets/interaction_xmlmode_001.png)

## 设置SOAP集成

为选件管理提供的SOAP Web服务与Adobe Campaign中常用的服务不同。 您可以通过上一节中描述的交互URL访问这些选件，并让您展示或更新给定联系人的选件。

### 优惠建议 {#offer-proposition}

有关通过SOAP提供的建议，请在 **nms:campation#Propose** 命令后跟以下参数：

* **targetId**:收件人的主键（可以是复合键）。
* **maxCount**:指定联系人的选件建议数。
* **上下文**:允许您在空间架构中添加上下文信息。 如果使用的架构为 **nms:interaction**, **`<empty>`** 值。
* **类别**:指定选件必须属于的类别。
* **主题**:指定选件必须属于的主题。
* **uid**:Adobe Campaign永久cookie的值(“uuid230”)。
* **nli**:Adobe Campaign会话Cookie(“nlid”)的值。
* **noProp**:使用“true”值停用建议书插入。

>[!NOTE]
>
>的 **targetId** 和 **maxCount** 设置是强制性的。 其他选项是可选的。

响应查询，SOAP服务将返回以下参数：

* **interactionId**:交互的ID。
* **命题**:XML元素，包含命题列表，每个命题都有自己的ID和HTML表示。

### 选件更新 {#offer-update}

添加 **nms:interaction#UpdateStatus** 命令到URL，然后是以下参数：

* **命题**:字符串，它包含在选件建议期间作为输出给出的建议ID。 请参阅 [优惠建议](#offer-proposition).
* **状态**:字符串类型，它会指定选件的新状态。 可能的值列在 **命题状态** 枚举，在 **nms:common** 架构。 例如，现成的数字3对应于 **已接受** 状态。
* **上下文**:XML元素，用于在空间架构中添加上下文信息。 如果使用的架构为 **nms:interaction**, **`<empty>`** 值。

### 使用SOAP调用的示例 {#example-using-a-soap-call}

以下是SOAP调用的代码示例：

```
<%
  var space = request.parameters.sp
  var cnx = new HttpSoapConnection(
    "https://" + request.serverName + ":" + request.serverPort + "/interaction/" + env + "/" + space,
    "utf-8",
    HttpSoapConnection.SOAP_12)
  var session = new SoapService(cnx, "nms:interaction")
  var action = request.parameters.a
  if( action == undefined )
    action = 'propose'

  try
  {
    switch( action )
    {
    case "update":
      var proposition = request.parameters.p
      var status      = request.parameters.st
      session.addMethod("UpdateStatus", "nms:interaction#UpdateStatus",
       ["proposition", "string",
        "status",      "string",
        "context",     "NLElement"],
       [])
      session.UpdateStatus(proposition, status, <undef/>)
      var redirect = request.parameters.r
      if( redirect != undefined )
        response.sendRedirect(redirect)
      break;

    case "propose":
      var count = request.parameters.n
      var target = request.parameters.t
      var categorie = request.parameters.c
      var theme = request.parameters.th
      var layout = request.parameters.l
      if( count == undefined )
        count = 1
      session.addMethod("Propose", "nms:proposition#Propose",
       ["targetId",      "string",
        "maxCount",      "string",
         "categories",    "string",
         "themes",        "string",
        "context",       "NLElement"],
       ["interactionId", "string",
        "propositions",  "NLElement"])
      response.setContentType("text/html")
      var result = session.Propose(target, count, category, theme, <empty/>)
      var props = result[1]
  %><table><tr><%
      for each( var propHtml in props.proposition.*.mdSource )
      {
        %><td><%=propHtml%></td><%
      }
  %></tr></table><%
      break;
    }
  }
  catch( e )
  {
  }
  %>
```
