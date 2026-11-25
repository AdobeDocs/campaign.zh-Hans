---
product: campaign
title: 定义 Web 窗体布局
description: 定义 Web 窗体布局
feature: Web Forms
version: Campaign v8, Campaign Classic v7
exl-id: 23ca17f8-de1a-4f9c-8357-3965dc3329b1
TQID: 'https://experienceleague.adobe.com/-0PZWl-79Q-MXZ-jHjp-VF12IUPeMcq27aGSgWl5Ans'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
subfeature_v2:
  - id: f391046b-0cf3-4e76-bd3b-97fe06654506
    internal-label: Web Apps
  - id: ed29abcd-b6a8-4d4b-ab8b-b7e746973281
    internal-label: Web Forms
  - id: d7be2b01-dc9c-40f7-aace-a151707504ed
    internal-label: Landing pages
source-git-commit: d3b34546c1b08190772154efe6f818b98cc1094c
workflow-type: tm+mt
source-wordcount: '703'
ht-degree: 1%
---
# 定义 Web 窗体布局{#defining-web-forms-layout}



## 创建容器 {#creating-containers}

通过容器，可组合页面的字段并配置其布局和组织页面中的元素。

对于表单的每个页面，均通过工具栏的&#x200B;**[!UICONTROL Containers]**&#x200B;按钮创建容器。

![打开了“容器”工具栏按钮的Web窗体页面编辑器，提供了“标准容器”选项](assets/s_ncs_admin_survey_containers_add.png)

使用容器对页面的元素进行分组，而无需将标签添加到最终渲染。 元素将分组到容器子树中。 标准容器允许您管理布局。

例如：

![包含两个容器（常规信息和您的合同）的树的页面属性及其表单字段](assets/s_ncs_admin_survey_containers_std_arbo.png)

标签的位置将应用于层次结构中放置在容器下方的元素。 如有必要，可以为每个元素重载。 添加或删除列以更改布局。 请参阅[定位页面上的字段](#positioning-the-fields-on-the-page)。

在上例中，渲染将如下所示：

![带有两个容器的已渲染表单页面：个人详细信息字段和合同复选框列表，以及验证按钮](assets/s_ncs_admin_survey_containers_std_ex.png)

## 将字段放置在页面上 {#positioning-the-fields-on-the-page}

Web窗体的布局在每个容器中逐页定义，并且可以根据需要过载。

页面可划分为若干列：每个页面均包含一定数量的列。 页面的每个字段占用&#x200B;**n**&#x200B;个单元格。 容器也占据一定数量的列，并且它们包含的字段占据一定数量的单元格。

默认情况下，页面构建在一列上，每个元素占据一个单元格。 这意味着字段会逐行显示，每个字段占一整行，如下所示：

![呈现单列表单页面，其中性别、姓名、名字和电子邮件字段栈叠在单独的行上](assets/s_ncs_admin_survey_container_ex.png)

在以下示例中，保留了默认配置。 页面占据一列，其中包含四个容器。

![具有四个容器且列数设置为1的页面属性突出显示](assets/s_ncs_admin_survey_container_ex0.png)

每个容器占据一列，每个元素占据一个单元格：

![在“显示”设置中将单元格数设置为1的信息元素属性突出显示](assets/s_ncs_admin_survey_container_ex0a.png)

呈现方式如下：

![具有四个容器的单列页面渲染，每个容器有一个垂直栈叠的列](assets/s_ncs_admin_survey_container_ex0_rend.png)

您可以调整显示参数以获得以下渲染：

![两列页面渲染，其中容器1和3填充左列，容器2和4填充右列](assets/s_ncs_admin_survey_container_ex1_rend.png)

在上述渲染示例中，每个输入字段、标题和图像在容器的列中占据一个单元格。

您可以修改每个容器中的格式。 在本例中，您可以将容器4的内容分布到两列上并分发元素。

![包含两列的容器4：标题和组合框各取一个单元格，复选框跨两个单元格](assets/s_ncs_admin_survey_container_ex2_rend.png)

标题和列表分别占据一个单元格（因此是容器的整行），复选框会扩展到两个单元格上。 根据字段类型，归属于输入字段的单元格数定义在&#x200B;**[!UICONTROL General]**&#x200B;选项卡或&#x200B;**[!UICONTROL Advanced]**&#x200B;选项卡中：

在“显示”设置](assets/s_ncs_admin_survey_container_ex2.png)下将单元格数设置为2的复选框元素的![高级选项卡

## 定义标签位置 {#defining-the-position-of-labels}

您可以在表单中定义字段和标签的对齐方式。

默认情况下，字段和页面其他内容的显示参数继承自表单的一般配置、页面的配置或父容器的配置（如果存在）。

在表单属性框中指定整个表单的全局显示参数。 **[!UICONTROL Rendering]**&#x200B;选项卡允许您选择标签的位置。

![Web窗体属性对话框，呈现选项卡，带有标签位置列表：已继承、左侧、右侧、上侧、下方、隐藏](assets/s_ncs_admin_survey_label_position.png)

可以通过&#x200B;**[!UICONTROL Advanced]**&#x200B;选项卡为每个页面、每个容器和每个字段重载此位置。

支持以下对齐：

* 继承：对齐方式继承自父元素（默认值），即父容器（如果有）或其他页面。
* 左/右：标签位于字段的右侧或左侧，
* 上/下：标签位于字段的上方或下方，
* 隐藏：不显示标签。
