---
title: Campaign安全最佳实践
description: Campaign安全最佳实践快速入门
feature: Privacy, PI
role: Developer
level: Beginner, Intermediate, Experienced
exl-id: 1d593c8e-4b32-4902-93a7-7b18cef27cac
source-git-commit: 864f2179384d3e3cfcf310fcd04fe02240bfbefa
workflow-type: tm+mt
source-wordcount: '664'
ht-degree: 1%

---

# Campaign安全最佳实践 {#ac-security}

在Adobe，我们非常重视您的数字体验的安全性。 安全实践已深深扎根于我们的内部软件开发和操作流程及工具中，并且我们的跨职能团队也严格遵循这些实践，以便以便于的方式预防、检测和应对事件。

此外，我们与合作伙伴、领先研究人员、安全研究机构和其他行业组织的协作有助于我们及时了解最新的威胁和漏洞，并且我们会定期将先进的安全技术纳入我们提供的产品和服务中。

## 隐私

隐私配置和强化是安全优化的关键要素。 以下是有关隐私的一些最佳实践：

* 使用HTTPS而不是HTTP来Protect客户个人信息(PI)
* 使用 [PI视图限制](../dev/restrict-pi-view.md) 保护隐私并防止数据被滥用
* 确保加密密码受限
* Protect可能包含个人信息（如镜像页面、Web应用程序等）的页面。

![](../assets/do-not-localize/speech.png)  作为托管Cloud Services用户，Adobe将与您合作，在您的环境中实施这些配置。


## 访问管理

访问管理是加强安全性的重要环节。 以下是一些主要的最佳实践：

* 创建足够的安全组
* 检查每个操作员是否拥有适当的访问权限
* 避免使用管理员操作员，并避免管理员组中的运算符过多

![](../assets/do-not-localize/book.png) 在 [Adobe Campaign Classic v7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/access-management.html?lang=en#webapp-operator){target=&quot;_blank&quot;}

## 编码准则

在Adobe Campaign中进行开发（工作流、Javascript、JSSP等）时，请始终遵循以下准则：

* **脚本**:请尝试避免使用SQL语句，使用参数化函数而不是字符串连接，通过添加要用于允许列表的SQL函数来避免SQL注入。

* **保护数据模型**:使用命名权限限制运算符操作，添加系统过滤器(sysFilter)

* **在Web应用程序中添加捕获**:在公共登陆页面和订阅页面中添加捕获。

![](../assets/do-not-localize/book.png) 在 [Adobe Campaign Classic v7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/scripting-coding-guidelines.html?lang=en#installing-campaign-classic){target=&quot;_blank&quot;}


## 个性化

在向内容添加个性化链接时，应始终避免在URL的主机名部分进行任何个性化，以避免潜在的安全漏洞。 以下示例绝不应用于所有URL属性&lt;`a href="">` 或 `<img src="">`:

* `<%= url >`
* `https://<%= url >`
* `https://<%= domain >/path`
* `https://<%= sub-domain >.domain.tld/path`
* `https://sub.domain<%= main domain %>/path`

## 数据限制

您必须确保经过身份验证的低权限用户无法访问加密密码。 要实现此目的，主要有两种方法：限制仅访问密码字段或访问整个实体。

此限制允许您删除密码字段，但允许所有用户从界面访问外部帐户。 请参阅[此页面](../dev/restrict-pi-view.md)以了解详情。

1. 进去 **[!UICONTROL Administration]** > **[!UICONTROL Configuration]** > **[!UICONTROL Data schemas]**.

1. 新建 **[!UICONTROL Extension of a schema]**.

1. 选择 **[!UICONTROL External Account]** (extAccount)。

1. 在最后一个屏幕中，您可以编辑新的srcSchema以限制对所有密码字段的访问：

   您可以将主元素(`<element name="extAccount" ... >`):

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

   因此，扩展的srcSchema可能如下所示：

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
   >您可以将 `$(loginId) = 0 or $(login) = 'admin'` by `hasNamedRight('admin')` 以便所有具有管理员权限的用户都可以查看这些密码。


## 访问管理

访问管理是加强安全性的重要环节。 以下是一些主要的最佳实践：

* 创建足够的安全组
* 检查每个操作员是否拥有适当的访问权限
* 避免使用管理员操作员，并避免管理员组中的运算符过多

![](../assets/do-not-localize/book.png) 在 [Adobe Campaign Classic v7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/access-management.html?lang=en#webapp-operator){target=&quot;_blank&quot;}

## 编码准则

在Adobe Campaign中进行开发（工作流、Javascript、JSSP等）时，请始终遵循以下准则：

* **脚本**:请尝试避免使用SQL语句，使用参数化函数而不是字符串连接，通过添加要用于允许列表的SQL函数来避免SQL注入。

* **保护数据模型**:使用命名权限限制运算符操作，添加系统过滤器(sysFilter)

* **在Web应用程序中添加捕获**:在公共登陆页面和订阅页面中添加捕获。

![](../assets/do-not-localize/book.png) 在 [Adobe Campaign Classic v7文档](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/scripting-coding-guidelines.html?lang=en#installing-campaign-classic){target=&quot;_blank&quot;}
