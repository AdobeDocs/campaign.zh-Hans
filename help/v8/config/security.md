---
solution: Campaign Classic
product: campaign
title: 活动安全最佳实践
description: 开始使用活动安全最佳实践
translation-type: tm+mt
source-git-commit: c2d066ca2f935455861c3d6747c9805c847f2e0d
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 0%

---

# 活动安全最佳实践{#ac-security}

在Adobe，我们非常重视您数字体验的安全性。 安全实践已深深地扎根于我们的内部软件开发和操作流程及工具之中，并且我们的跨职能团队会严格遵循这些实践，以便以权宜的方式预防、检测和响应事件。

此外，我们与合作伙伴、领先研究人员、安全研究机构和其他行业组织的协作有助于我们及时了解最新的威胁和漏洞，并且我们会定期将高级安全技术纳入我们优惠的产品和服务中。

## 隐私

隐私配置和强化是安全优化的关键要素。 以下是有关隐私的一些最佳实践：

* Protect客户个人信息(PI)，使用HTTPS代替HTTP
* 使用[PI视图限制](../dev/restrict-pi-view.md)保护隐私并防止数据被滥用
* 确保加密密码受限
* Protect可能包含镜像页面、Web应用程序等个人信息的页面。

:speech_balloon:作为托管Cloud Services用户，Adobe将与您一起在您的环境上实施这些配置。

## 个性化

在向内容添加个性化链接时，请始终避免在URL的主机名部分包含任何个性化，以避免潜在的安全漏洞。 以下示例不应用于所有URL属性&lt;`a href="">`或`<img src="">`:

* `<%= url >`
* `https://<%= url >`
* `https://<%= domain >/path`
* `https://<%= sub-domain >.domain.tld/path`
* `https://sub.domain<%= main domain %>/path`

## 数据限制

您必须确保经过身份验证的低权限用户无法访问加密的口令。 为此，有两种主要方式：仅限对密码字段或对整个实体（需要内部版本>= 8770）的访问。

此限制允许您删除口令字段，但允许所有用户从界面访问外部帐户。 请阅读[本页](../dev/restrict-pi-view.md)了解更多信息。

1. 进入&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Configuration]** > **[!UICONTROL Data schemas]**。

1. 新建&#x200B;**[!UICONTROL Extension of a schema]**。

1. 选择&#x200B;**[!UICONTROL External Account]**(extAccount)。

1. 在最后一个屏幕中，您可以编辑新的srcSchema以限制对所有密码字段的访问：

   可以通过以下方式替换主元素(`<element name="extAccount" ... >`):

   ```
   <element name="extAccount">
       <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
       <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
   
       <element name="s3Account">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="awsSecret"/>
       </element>
       <element name="wapPush">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
       </element>
       <element name="mms">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
       </element>
   </element>
   ```

   因此，您的扩展srcSchema可以如下所示：

   ```
   <srcSchema _cs="External Accounts (cus)" created="2017-05-12 07:53:49.691Z" createdBy-id="0"
               desc="Definition of external accounts (Email, SMS...) used by the modules"
               entitySchema="xtk:srcSchema" extendedSchema="nms:extAccount" img="" label="External Accounts"
               labelSingular="External account" lastModified="2017-05-12 08:33:49.365Z"
               mappingType="sql" md5="E9BB0CD6A4375F500027C86EA854E101" modifiedBy-id="0"
               name="extAccount" namespace="cus" xtkschema="xtk:srcSchema">
       <createdBy _cs="Administrator (admin)"/>
       <modifiedBy _cs="Administrator (admin)"/>
       <element name="extAccount">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
   
           <element name="s3Account">
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="awsSecret"/>
           </element>
           <element name="wapPush">
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
           </element>
           <element name="mms">
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
           </element>
       </element>
   </srcSchema>    
   ```

   >[!NOTE]
   >
   >您可以通过`hasNamedRight('admin')`将`$(loginId) = 0 or $(login) = 'admin'`替换为允许具有管理员权限的所有用户查看这些密码。


## 访问管理

访问管理是加强安全的一个重要部分。 以下是一些主要的最佳实践：

* 创建足够的安全组
* 检查每个运营商是否拥有适当的访问权限
* 避免使用管理员操作员，并避免管理员组中的操作员过多

:arrow_upper_right:了解有关[Adobe Campaign Classic文档](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/access-management.html?lang=en#webapp-operator)的更多信息

## 编码指南

在Adobe Campaign(工作流、Javascript、JSSP等)中进行开发时，始终遵循以下准则：

* 脚本：尝试避免SQL语句，使用参数化函数而不是字符串连接，通过向允许列表添加要使用的SQL函数来避免SQL注入。

* 保护数据模型：使用已命名权限限制操作符操作，添加系统过滤器(sysFilter)

* 在Web应用程序中添加捕捉：在您的公共登陆页和订阅页面中添加捕捉。

:arrow_upper_right:了解有关[Adobe Campaign Classic文档](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/scripting-coding-guidelines.html?lang=en#installing-campaign-classic)的更多信息
