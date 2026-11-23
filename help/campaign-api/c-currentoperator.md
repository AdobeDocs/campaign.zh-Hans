---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 9%
---
# CurrentOperator（类）

包含有关当前操作员（名称、标识符、权限等）信息的对象。

此类有一个实例，用于访问应用服务器的某些属性。 可通过`application`全局变量的属性访问此单例。

示例：

```text
var operator = application.operator logInfo("login: " + operator.login) logInfo("id: " + operator.id) logInfo("description: " + operator.computeString) logInfo("=== Groups ===") for each(var id in operator.groups) logInfo(id) logInfo("=== Rights ===") for each(var right in operator.rights) logInfo(right)
```

## 方法

| 方法 | 描述 |
| --- | --- |
| [hasRight](m-currentoperator-hasright.md) | 测试运算符是否具有特定的命名权限。 |

## 属性

| 属性 | 描述 |
| --- | --- |
| [登录](p-currentoperator-login.md) | 返回当前操作员的登录名。 |
| [id](p-currentoperator-id.md) | 返回当前操作员的内部标识符。 |
| [computeString](p-currentoperator-computestring.md) | 返回当前运算符描述字符串。 默认情况下，这是运算符的名称，后跟其登录名。 |
| [组](p-currentoperator-groups.md) | 返回当前操作员组中的标识符列表。 |
| [个权限](p-currentoperator-rights.md) | 返回当前操作员的权限列表。 |
| [时区](p-currentoperator-timezone.md) | 返回当前操作员使用的时区的名称。 |
| [主页](p-currentoperator-home.md) | 返回当前操作员的根文件夹的名称。 |

## 功能

**可用位置：**

* 内容管理
* 投放属性
* 类型规则
* JSSP
* SOAP方法
* WebApp
* 工作流
