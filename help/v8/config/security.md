---
title: Campaign安全最佳实践
description: Campaign安全最佳实践入门
feature: Privacy, PI
role: Developer
level: Beginner
exl-id: 1d593c8e-4b32-4902-93a7-7b18cef27cac
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '583'
ht-degree: 1%

---

# Campaign安全最佳实践 {#ac-security}

在Adobe，我们非常重视您的数字体验的安全性。 安全实践深深地植入到我们的内部软件开发与运行流程和工具中，我们的跨职能团队严格遵循这些惯例，以预防、检测事件并快速做出响应。

此外，我们与合作伙伴、领先的研究人员、安全研究机构和其他行业组织开展的协作也有助于我们及时了解最新的威胁和漏洞，并且我们经常将先进的安全技术融入我们提供的产品和服务中。

## 隐私

隐私配置和强化是安全优化的关键元素。 以下是有关隐私的一些可遵循的最佳实践：

* 使用HTTPS而不是HTTPProtect您的客户个人信息(PI)
* 使用[PI视图限制](../dev/restrict-pi-view.md)保护隐私并防止数据被滥用
* 确保加密密码受到限制
* Protect可能包含个人信息的页面，如镜像页面、Web应用程序等。


>[!NOTE]
>
>作为托管Cloud Service用户，Adobe将与您合作在您的环境中实施这些配置。


## 访问管理

访问管理是安全加固的重要组成部分。 以下是一些主要的最佳实践：

* 创建足够的安全组
* 检查每个操作员是否具有适当的访问权限

在[本节](../start/gs-permissions.md)中了解有关权限的详细信息

## 编码准则

在Adobe Campaign（工作流、Javascript、JSSP等）中进行开发时，请始终遵循以下准则：

* **脚本编写**：尝试避免SQL语句，使用参数化函数而不是字符串连接，通过添加要用于允许列表的SQL函数来避免SQL注入。

* **保护数据模型**：使用已命名权限限制操作员操作，添加系统筛选器(sysFilter)

* **在Web应用程序中添加验证码**：在您的公共登陆页面和订阅页面中添加验证码。

请参阅[Adobe Campaign Classic v7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/scripting-coding-guidelines.html#installing-campaign-classic){target="_blank"}以了解详情。


## 个性化

向内容添加个性化链接时，请始终避免在URL的主机名部分进行任何个性化设置，以避免潜在的安全缺口。 绝不应该在所有URL属性&lt;`a href="">`或`<img src="">`中使用以下示例：

* `<%= url >`
* `https://<%= url >`
* `https://<%= domain >/path`
* `https://<%= sub-domain >.domain.tld/path`
* `https://sub.domain<%= main domain %>/path`

## 数据限制

您必须确保低权限验证用户无法访问加密的密码。 要执行此操作，主要有两种方法：限制仅访问密码字段或访问整个实体。

此限制允许您删除密码字段，但允许所有用户从界面访问外部帐户。 请参阅[此页面](../dev/restrict-pi-view.md)以了解详情。

1. 前往&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Configuration]** > **[!UICONTROL Data schemas]**。

1. 创建新&#x200B;**[!UICONTROL Extension of a schema]**。

1. 选择&#x200B;**[!UICONTROL External Account]** (extAccount)。

1. 在最后一个屏幕中，可以编辑新的srcSchema以限制对所有密码字段的访问：

   您可以通过以下方式替换主元素(`<element name="extAccount" ... >`)：

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

   因此，您的扩展srcSchema可能如下所示：

   ```
   <...>
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
   <...> 
   ```

   >[!NOTE]
   >
   >您可以将`$(loginId) = 0 or $(login) = 'admin'`替换为`hasNamedRight('admin')`，以使所有具有管理员权限的用户都能看到这些密码。


## 访问管理

访问管理是安全加固的重要组成部分。 以下是一些主要的最佳实践：

* 创建足够的安全组
* 检查每个操作员是否具有适当的访问权限

在本节](../start/gs-permissions.md)中了解有关[中权限的更多信息。

## 编码准则

在Adobe Campaign（工作流、Javascript、JSSP等）中进行开发时，请始终遵循以下准则：

* **脚本编写**：尝试避免SQL语句，使用参数化函数而不是字符串连接，通过添加要用于允许列表的SQL函数来避免SQL注入。

* **保护数据模型**：使用已命名权限限制操作员操作，添加系统筛选器(sysFilter)

* **在Web应用程序中添加验证码**：在您的公共登陆页面和订阅页面中添加验证码。

请参阅[Adobe Campaign Classic v7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/scripting-coding-guidelines.html#installing-campaign-classic){target="_blank"}以了解详情。
