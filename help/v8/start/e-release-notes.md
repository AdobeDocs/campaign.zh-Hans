---
title: 早期 Campaign v8 发行说明
description: 早期 Campaign v8 版本
feature: Overview
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
hide: true
hidefromtoc: true
exl-id: a45f7b22-44c7-4dad-af0a-ae8f683ae3d9
source-git-commit: ac356acdbbc8072ce8263b1c62804a4703781ca9
workflow-type: tm+mt
source-wordcount: '586'
ht-degree: 20%

---

# 早期发行说明 {#e-new-release}

此页面介绍了下一个 Campaign v8 版本中包含的改进和修复。在发行之日前，此内容可能会有所变动，恕不另行通知。[此页面](../start/release-notes.md)中提供了正式的发行说明。

## 8.5 版 {#release-8-5}

_2023年6月30日_

**新增功能**

<table> 
<thead>
<tr> 
<th> <strong>增强的推送通知服务</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td><p>Campaign 8.5将在v8上推出我们最新的推送通知服务，该服务基于现代尖端技术构建的强大框架提供支持。 此服务旨在解锁更高级别的可扩展性，确保您的通知能够以无缝的效率接触到更多受众。 通过我们增强的基础架构和优化的流程，您可以期待更高的规模和可靠性，使您能够以前所未有的方式吸引移动应用程序用户并与之建立联系。 此功能仅适用于选定的客户组（限量发布）。</p>
</td> 
</tr> 
</tbody> 
</table>

**兼容性更新**

* 现已弃用32位版本的客户端控制台。 从 8.6 开始，将仅支持 64 位客户端控制台。客户端控制台可无缝升级到64位版本。 有关如何升级操作系统的详细信息，请参阅此[技术说明](https://experienceleague.adobe.com/docs/campaign/technotes-ac/tn-new/console.html?lang=zh-Hans)。
* 您现在可以将Campaign v8实例连接到Azure synapse外部数据库。 此连接通过新的外部帐户管理。

**改进**

* 通过实施一系列优化，短信吞吐量得到了显着提升，从而提升了短信通信的速度和效率。
* 从Campaign v8.5开始，改进了Campaign v8的身份验证过程。 技术操作员必须使用AdobeIdentity Management System (IMS)连接到Campaign。
* 您现在可以利用目标和源连接来同步配置文件属性，例如Adobe Experience Platform和Campaign v8数据库之间的选择退出数据
* 投放准备已优化。
* 除了现有的用户/密码身份验证方法之外，还为SFTP外部帐户添加了一个新的基于密钥的身份验证选项。 用户现在可以使用私钥安全地进行身份验证，从而增强安全性并为SFTP访问提供替代身份验证机制。

**安全性增强**

* 不能再从客户端控制台创建运算符。 您现在需要使用Admin Console。 [了解详情](../start/gs-permissions.md)。
* 更新了多个第三方工具以优化安全性。

**修补程序**

* 修复了可能导致投放的HTML内容中的特殊字符在若干浏览器中编码不正确的问题。 (NEO-60081)
* 修复了可能导致无法在Campaign v8企业(FFDA)部署中保存报告的问题。 (NEO-56836)
* 修复了通过更新数据工作流活动将数据插入或更新到自定义FFDA架构中时发生的问题。 (NEO-54708)
* 修复了阻止数据库清理工作流删除FFDA上nms：address表中的地址的问题。 (NEO-54460)
* 修复了计费工作流可能因“编译内存耗尽”错误而失败的问题。 (NEO-51137)
* 修复了可能阻止GPG解密在数据加载（文件）工作流活动中正常工作的问题。 (NEO-50257)
* 修复了会导致 `JSPContext.sqlExecWithOneParam` 功能无法正常运行的问题。(NEO-50066)
* 修复了在个性化字段中使用不可打印字符时导致投放失败的问题。 (NEO-48588)
* 修复了在插入Adobe Target动态图像时可能导致投放错误的问题。 (NEO-62689)
* 修复了在投放中使用条件内容时阻止浏览器添加额外空格的问题。 (NEO-62132)
* 修复了在电子邮件内容编辑器中单击图像时导致弹出窗口打开的问题。 (NEO-60752)
* 修复了在编辑投放内容时可能导致错误并阻止滚动的问题。 (NEO-61364)