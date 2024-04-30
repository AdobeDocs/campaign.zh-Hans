---
title: 增强的安全加载项
description: Campaign增强安全性加载项入门
feature: Configuration
role: Developer
level: Experienced
hide: true
hidefromtoc: true
exl-id: 7c586836-82e1-45fb-9c28-18361572e1fa
source-git-commit: f9b064dffa0f8792e8653760cb2ac44cfdf43848
workflow-type: tm+mt
source-wordcount: '696'
ht-degree: 1%

---

# 增强的安全加载项 {#enhanced-security}

要使网络连接更安全，并为您的资源提供更好的安全性， [!DNL Adobe Campaign] 提供新的 **增强的安全性** 加载项。

此附加组件包括两个生态系统功能：

* [安全CMK集成](#secure-cmk-integration)

* [安全VPN隧道](#secure-vpn-tunneling)

这些功能详见下文。

## 安全CMK集成 {#secure-cmk-integration}

此 **安全的客户管理密钥(CMK)集成** 允许您通过Amazon Web Services (AWS)帐户使用自己的密钥加密实例和数据。

客户管理的密钥是您在您的AWS帐户中创建、拥有和管理的Key Management Service (KMS)密钥。 您可以完全控制这些KMS密钥，并使用它们来加密和解密数据。 通过让您负责生成和管理加密密钥，此容量使您能够更好地控制密钥，包括撤销密钥。

>[!CAUTION]
>
>如果您撤销了密钥，则必须了解将会产生的影响。 [了解详情](#cmk-callouts)

要启用CMK与Campaign的集成，请执行以下步骤：

1. 连接到您的 [Amazon Web Services (AWS)](https://aws.amazon.com/){target="_blank"} 帐户。

1. 使用AWS密钥管理服务(KMS)生成具有自动轮换的密钥。 [了解如何](https://docs.aws.amazon.com/kms/latest/developerguide/create-keys.html){target="_blank"}.

1. 通过Adobe您的AWS帐户来应用提供给您的策略，以便授予对资源的访问权限。 [了解详情](https://docs.aws.amazon.com/kms/latest/developerguide/key-policy-services.html){target="_blank"}. <!--link TBC-->

1. 共享您的 [Amazon资源名称（键ARN）](https://docs.aws.amazon.com/kms/latest/developerguide/find-cmk-id-arn.html){target="_blank"} 替换为 [!DNL Adobe Campaign]. 为此，请联系您的Adobe代表。 <!--or Adobe transition manager?-->

1. 创建并测试Amazon EventBridge规则，以启用按Adobe监视密钥&#x200B;。 [了解详情](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-rules.html){target="_blank"}。

## 安全VPN隧道 {#secure-vpn-tunneling}

此 **安全虚拟专用网络(VPN)隧道** 是一个点对点VPN，通过专用网络，为传输中的数据提供从您的设施到 [!DNL Adobe Campaign] 实例。

<!--As it connects two networks together, it is a site-to-site VPN.-->

为确保高可用性(HA)，它使用两个通道来避免在一个通道上发生问题时造成任何中断。

支持以下三个用例：

* 通过VPN的联合数据访问(FDA)<!--to access your on-premise database from the Campaign instance over VPN-->

* 从胖客户机通过VPN登录实例

* 通过VPN的实例SFTP访问

>[!CAUTION]
>
>仅支持本地数据库和与AWS兼容的VPN设备。 [了解详情](#vpn-callouts)

要确保正确使用此功能，请遵循以下准则：

* 根据Adobe端VPN配置设置您的端VPN。

* 保持两个通道处于正常运行状态，以实现高可用性。

* 监视侧隧道。

* 您必须是通道的发起者，如果通道关闭，您必须对齐以重新启动连接。

* 在终端设置连接失败时的重试机制。

## 护栏 {#callouts}

下面列出了与增强安全功能相关的一些护栏和限制。

* 确保您的所有Secure CMK集成/Secure VPN隧道用例都正常工作。

<!--* Adobe shall reach out to you or your technical team if any issue is found on your side.

* Currently, when using Enhanced security features, any communication with Adobe must be performed manually via email.-->

* Adobe将监控：

   * 您的实例可用性，如果密钥不可用，则继续发送警报。

   * VPN通道，并在出现任何问题时继续发出警报。

### 安全CMK集成护栏 {#cmk-callouts}

* Adobe不提供AWS帐户。 您必须拥有自己的AWS帐户并进行设置，以生成您的密钥并将其与Adobe共享。

* 仅 [AWS密钥管理服务](https://docs.aws.amazon.com/kms/latest/developerguide/overview.html){target="_blank"} 支持(KMS)键。 不能使用KMS之外的客户生成的键&#x200B;。

* 首次设置将涉及一些停机时间。&#x200B;AEM停机时间将取决于数据库的大小。

* 在您拥有和维护密钥时，如果密钥发生任何更改，您必须联系Adobe。&#x200B;

* 您可以使用以下工具审核您的密钥 [AWS CloudTrail](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-user-guide.html){target="_blank"} 如有需要，可将其撤销&#x200B;。

* 如果您撤消、禁用或删除密钥，则在还原相应的操作之前，将无法访问已加密的资源和实例。

  >[!CAUTION]
  >
  >如果禁用了密钥并且没有在7天内还原此操作，则只能从备份中恢复数据库。
  >
  >如果您删除了密钥并且没有在30天内还原此操作，则您的所有数据将被永久删除并将丢失&#x200B;。

### 安全VPN隧道护栏 {#vpn-callouts}

* 目前，仅支持内部部署数据库，例如<!--Richa to check the list with PM-->：

   * MySQL
   * netezza 
   * oracle 
   * SAP HANA 
   * SQL Server 
   * Sybase 
   * teradata 
   * Hadoop（通过 HiveSQL）

* 仅支持与AWS兼容的VPN设备。 上提供了兼容设备的列表 [此页面](https://docs.aws.amazon.com/vpn/latest/s2svpn/your-cgw.html#example-configuration-files){target="_blank"}<!--check which list should be communicated-->.

* 不支持到第三方或外部供应商的VPN连接。

* 不包括由Adobe管理的到私有云数据库的其他VPN。
