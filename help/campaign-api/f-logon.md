---
source-git-commit: 3319b56a62aa8a8364c7f2f85bc81708a66a5978
workflow-type: tm+mt
source-wordcount: '103'
ht-degree: 12%
---
# 登录

将脚本执行上下文更改为当前登录。

```text
logon (sessionToken)
```

```text
logon (login, password)
```

```text
logon (context)
```

## 参数

**sessionToken**&#x200B;要使用的会话令牌。

**login**&#x200B;要使用的操作员登录。

**密码**&#x200B;操作员密码。 如果当前登录具有“管理员”权限，则密码可为空字符串。

**上下文**&#x200B;表示登录的对象，由上次登录调用返回。

## 返回值

返回与上次登录匹配的对象。 这可以通过将此参数传递给登录函数来恢复以前的登录。

## 备注

示例：

```javascript
var oldContext = logon("jdoe", "")

// ...

logon(oldContext)
```

## 功能

**可用位置：**

* 内容管理
* 投放属性
* 投放消息
* 类型规则
* 导入
* JSSP
* SOAP方法
* WebApp
* 工作流
