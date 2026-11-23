---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 4%
---
# DBEngine（类）

表示数据库连接。

使用此对象可以查询数据库并执行相关操作。

此类中的大多数方法都需要“sql”权限。 如果操作员调用方法但没有相应的权限，则会引发异常。 一般来说，所有更改数据库的方法都需要“sql”权限，而只是查看信息的方法则不需要。 请参阅有关每种方法的文档以了解是否需要权限。

## 方法

| 方法 | 描述 |
| --- | --- |
| [batchDelete](m-dbengine-batchdelete.md) | 按数据包删除表的记录。 |
| [处置](m-dbengine-dispose.md) | 从链接到它的所有资源中释放连接。 |
| [执行](m-dbengine-execute.md) | 执行SQL命令。 |
| [执行](m-dbengine-exec.md) | execute命令的别名。 此函数已过时，请使用[execute()](m-dbengine-execute.md) |
| [查询](m-dbengine-query.md) | 执行SELECT类型的SQL查询。 |
| [queryWithTypes](m-dbengine-querywithtypes.md) | 执行具有列类型规范的SELECT类型SQL查询。 |
| [开始](m-dbengine-begin.md) | 在连接上启动新事务。 |
| [提交](m-dbengine-commit.md) | 批准连接上正在进行的事务。 |
| [回滚](m-dbengine-rollback.md) | 取消连接上正在进行的事务。 |

## 属性

| 属性 | 描述 |
| --- | --- |
| [是Oracle](p-dbengine-isoracle.md) | 如果数据库是Oracle，则返回true。 |
| [isDB2](p-dbengine-isdb2.md) | 如果数据库为DB2类型，则返回true。 |
| [isMySQL](p-dbengine-ismysql.md) | 如果数据库为MySQL类型，则返回true。 |
| [isMSSQL](p-dbengine-ismssql.md) | 如果数据库是SQL Server，则返回true。 |
| [isPostgreSQL](p-dbengine-ispostgresql.md) | 如果数据库是PostgreSQL，则返回true。 |
| [isSybase](p-dbengine-issybase.md) | 如果数据库是Sybase，则返回true。 |
| [isSybaseIQ](p-dbengine-issybaseiq.md) | 如果数据库是Sybase IQ，则返回true。 |
| [isFDA](p-dbengine-isfda.md) | 如果通过FDA访问数据库，则返回true。 |
| [isBroken](p-dbengine-isbroken.md) | 如果连接不再可用，则返回true。 |
| [useUnicodeData](p-dbengine-useunicodedata.md) | 如果数据库包含unicode数据，则返回true。 |
| [useNChar](p-dbengine-usenchar.md) | 如果Adobe Campaign使用NCHAR、NVARCHAR、NCLOB和NTEXT类型字段，则返回true。 |

## 功能

**可用位置：**

* 内容管理
* 投放属性
* 类型规则
* JSSP
* SOAP方法
* WebApp
* 工作流
