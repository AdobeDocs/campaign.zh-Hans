---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 6%
---
# 应用程序（类）

此类有一个实例，用于访问应用服务器的某些属性。 可通过`application`全局变量访问此单例。

## 方法

| 方法 | 描述 |
| --- | --- |
| [hasPackage](m-application-haspackage.md) | 测试软件包是否已安装。 |
| [getSchema](m-application-getschema.md) | 返回到Adobe Campaign架构的映射，如果架构不存在，则返回空值。 |
| [getDBMSType](m-application-getdbmstype.md) | 返回数据库的服务器类型。 |
| [getNewIds](m-application-getnewids.md) | 返回内部数据库键的ID列表。 |
| [getConnection](m-application-getconnection.md) | 返回到数据库服务器的新连接。 |
| [getTimezoneJson](m-application-gettimezonejson.md) | 返回一个字符串，该字符串是UTC时间及其开始日期与时区的UNIX时段相比的时间差列表的JSON表示形式。 |
| [登录](m-application-onlog.md) | 为写入日志的消息添加或删除侦听函数 |
| [onTrace](m-application-ontrace.md) | 添加或删除跟踪消息拦截函数。 |

## 属性

| 属性 | 描述 |
| --- | --- |
| [buildNumber](p-application-buildnumber.md) | 返回应用服务器的内部版本号。 |
| [实例名称](p-application-instancename.md) | 执行脚本的实例的名称。 |
| [instanceVarDir](p-application-instancevardir.md) | 执行脚本的实例的“var”目录的完整路径。 |
| [instanceUploadDir](p-application-instanceuploaddir.md) | 执行脚本的实例的“上载”目录的完整路径。 |
| [操作员](p-application-operator.md) | 返回包含有关当前操作员（名称、标识符、权限等）的信息的对象。 |
| [区域设置](p-application-locale.md) | 返回与实例Local匹配的字符字符串。 |

## 功能

**可用位置：**

* 内容管理
* 投放属性
* 类型规则
* JSSP
* SOAP方法
* WebApp
* 工作流
