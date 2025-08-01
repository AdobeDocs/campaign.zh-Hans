---
title: Campaign增强的安全加载项
description: Campaign增强安全性加载项入门
feature: Configuration
role: Developer
level: Experienced
exl-id: 7c586836-82e1-45fb-9c28-18361572e1fa
source-git-commit: 3f36d7c425dd5a9a13e1de7a77371b29a462dbea
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 3%

---


# Campaign增强安全性加载项 {#enhanced-security}

为了使网络连接更加安全并为您的资源提供更好的安全性，[!DNL Adobe Campaign]提供了新的&#x200B;**增强安全性**&#x200B;加载项。

此附加组件包括两个生态系统功能：

* [安全的客户管理密钥(CMK)集成](#secure-cmk-integration)

* [安全虚拟专用网络(VPN)隧道](#secure-vpn-tunneling)

这些功能详见下文。

本页列出了与增强安全功能相关的一些护栏和限制。 此外，您必须确保所有安全CMK集成/安全VPN隧道用例都正常工作。

在实施这些功能后，Adobe将监控：

* 您的实例可用性，如果密钥不可用，则继续发送警报。

* VPN通道，并在出现任何问题时继续发出警报。

## 安全的客户管理密钥集成 {#secure-cmk-integration}

**安全客户管理的密钥(CMK)集成**&#x200B;允许您通过Amazon Web Services (AWS)帐户使用自己的密钥加密静态数据。

客户管理的密钥是您在您的AWS帐户中创建、拥有和管理的Key Management Service (KMS)密钥。 您可以完全控制这些KMS密钥，并使用它们来加密和解密数据。 通过让您负责生成和管理加密密钥，此容量使您能够更好地控制密钥，包括撤销密钥。

>[!CAUTION]
>
>如果您撤销了密钥，则必须了解将会产生的影响。 [了解详情](#cmk-callouts)

要启用CMK与Campaign的集成，请执行以下步骤：

1. 连接到您的[Amazon Web Services (AWS)](https://aws.amazon.com/){target="_blank"}帐户。

1. 使用AWS密钥管理服务(KMS)生成具有自动轮换的密钥。 [了解如何操作](https://docs.aws.amazon.com/kms/latest/developerguide/create-keys.html){target="_blank"}。

1. 将Adobe提供给您的策略应用到您的AWS帐户，以便授予对资源的访问权限。 [了解详情](https://docs.aws.amazon.com/kms/latest/developerguide/key-policy-services.html){target="_blank"}。<!--link TBC-->

1. 与[共享您的](https://docs.aws.amazon.com/kms/latest/developerguide/find-cmk-id-arn.html){target="_blank"}Amazon资源名称（键ARN）[!DNL Adobe Campaign]。 为此，请联系您的Adobe代表。<!--or Adobe transition manager?-->

1. 创建和测试Amazon EventBridge规则，以启用Adobe对密钥的监控&#x200B;。 [了解详情](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-rules.html){target="_blank"}。


### 护栏和限制 {#cmk-callouts}

以下护栏和限制适用于与Adobe Campaign v8的CMK集成：

* Adobe不提供[Amazon Web Services (AWS)](https://aws.amazon.com/){target="_blank"}帐户。 您必须拥有自己的AWS帐户并进行设置，以生成您的密钥并将其与Adobe共享。

* 仅支持[AWS密钥管理服务](https://docs.aws.amazon.com/kms/latest/developerguide/overview.html){target="_blank"} (KMS)密钥。 不能使用KMS之外的客户生成的键&#x200B;。

* 首次设置期间预计会出现停机时间。&#x200B;AEM停机时间持续时间取决于数据库的大小。

* 作为客户，您拥有和维护密钥。 如果密钥发生任何更改，您必须联系Adobe&#x200B;。

* 您可以使用[AWS CloudTrail](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-user-guide.html){target="_blank"}审核您的密钥，并在需要时撤消它。&#x200B;

* 如果您撤消、禁用或删除密钥，则在还原相应的操作之前，将无法访问已加密的资源和实例。

  >[!CAUTION]
  >
  >如果禁用了密钥并且没有在7天内还原此操作，则只能从备份中恢复数据库。
  >
  >如果您删除了密钥并且没有在30天内还原此操作，则您的所有数据将被永久删除并将丢失&#x200B;。

## 安全的虚拟专用网络隧道 {#secure-vpn-tunneling}

**安全虚拟专用网络(VPN)隧道**&#x200B;是一个点对点VPN，它通过专用网络为传输中的数据提供从您的设施到[!DNL Adobe Campaign]实例的安全访问。

<!--As it connects two networks together, it is a site-to-site VPN.-->

为确保高可用性(HA)，它使用两个通道来避免在一个通道上发生问题时造成任何中断。

支持以下三个用例：

* 通过VPN的联合数据访问(FDA)，用于通过VPN从Campaign实例访问内部部署数据库

* 从胖客户机通过VPN登录实例

* 通过VPN的实例SFTP访问

>[!CAUTION]
>
>支持内部部署和云数据库。 [了解详情](#vpn-databases)

要确保正确使用此功能，请遵循以下准则：

* 根据Adobe端VPN配置设置您的端VPN。

* 保持两个通道处于正常运行状态，以实现高可用性。

* 监视侧隧道。

* 您必须是通道的发起者，如果通道关闭，您必须对齐以重新启动连接。

* 在终端设置连接失败时的重试机制。

### 支持的数据库和设备 {#vpn-databases}

支持以下内部部署数据库：

* MySQL
* Netezza
* Oracle
* SAP HANA
* SQL Server
* Sybase
* Teradata
* Hadoop（通过 HiveSQL）
* PostgreSQL

支持云数据库。 请参阅[兼容性矩阵](../start/compatibility-matrix.md#FederatedDataAccessFDA)。

>[!NOTE]
>
>* 不支持到第三方或外部供应商的VPN连接。
>
>* 不包括由Adobe管理的到专用云数据库的其他VPN。
