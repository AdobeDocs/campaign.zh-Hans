---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 3%
---
# 登录

打开会话

```text
[ String sessionToken, sessionInfo sessionInfo, String securityToken ] = Logon ( String login, String password, XML parameters )
```

## 参数

**登录**&#x200B;用户帐户

**密码**&#x200B;与用户登录关联的密码

**参数**&#x200B;连接设置

## 返回值

**sessionToken**&#x200B;会话标记

**sessionInfo**&#x200B;会话参数

**securityToken**&#x200B;安全令牌

## 帐户锁定机制配置

登录() API中提供了帐户锁定机制。 它防止在指定时间范围内连续多次失败的登录尝试后再次尝试登录。

有四个选项可用于配置锁定机制：

* **XtkSecurity\_max\_Unsuccessul\_Attempts\_Allowed**：在指定持续时间内阻止密钥的最大失败尝试次数。 默认值为3。
* **XtkSecurity\_Initial\_Ban\_Duration**：首次禁止键的持续时间。 默认持续时间为5分钟。
* **XtkSecurity\_Max\_Ban\_Duration**：可禁止键的最长持续时间。
* **XtkSecurity\_Examine\_Window**：用于跟踪禁止无效密钥的失败登录尝试次数的时间窗口。 默认持续时间为10分钟。

例如，如果某人10分钟内尝试3次不成功，则其密钥将被阻止5分钟。

## 功能

**架构：** [xtk:session](s-xtk-session.md)

**静态：**

是
