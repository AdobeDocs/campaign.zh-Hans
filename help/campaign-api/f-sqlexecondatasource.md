---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '123'
ht-degree: 8%
---
# sqlExecOnDataSource

对数据源执行SQL脚本。

```text
sqlExecOnDataSource (query, dataSource [, value1, ... ])
```

## 参数

**查询** SQL查询。

**数据源**&#x200B;数据源。

**value1， ...** SQL查询的变量。

## 返回值

在UPDATE或INSERT SQL命令中更新或插入的记录数。

## 备注

数据源的授权值可以是：

* “”或“默认”指向Adobe Campaign数据库

* “nms:extAccount:InternalName”指向Adobe Campaign外部帐户(FDA)中定义的数据源

* “名称”（数据源的名称）指向实例配置文件(config-instance.xml)中定义的数据源，其形式如下：

  ```xml
                   <dataStore hosts="*" lang="">
        <dataSource name="datasourcename">
          <dbcnx encrypted="" login="" password=""
                 provider="" server=""/>
        </dataSource>
      </dataStore>
  ```

示例：

```javascript
sqlExecOnDataSource("UPDATE XtkOption SET sStringValue = $(sz) WHERE sName = $(sz)", oracleExternalDB, 'WdbcOptions_TableSpaceWork_nms:extAccount:' + sExtAccount)
```

作为此函数的参数设置的可选变量在[sqlGetString(query， value1， ...)](f-sqlgetstring.md)中定义

## 功能

**可用位置：**

* 内容管理
* 投放属性
* 类型规则
* JSSP
* SOAP方法
* WebApp
* 工作流
