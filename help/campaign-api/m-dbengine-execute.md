---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 5%
---
# 执行

执行SQL命令。

```text
execute (command [, value1, ... ])
```

## 参数

**命令** SQL命令。

**value1， ...**&#x200B;命令的变量。

## 返回值

如果适用于执行的命令，则更新或插入的记录数，否则为零。

## 备注

变量用于替代命令的参数。 变量类型必须与命令中声明的类型匹配。 类型如下：

* $(sz)字符串
* $(m)备注
* $(l)长
* $(s)短
* $(b)字节
* $(d)多次
* $(f)浮点数
* $(ts)时间戳
* $(dt)日期
* $(tm)时间
* $(dur)时间跨度en毫秒(ms)

以下替换参数会自动被值替换，并且不需要关联的变量。

* $(id)生成标识符
* $(id:NmsTrackingLogId)根据特定序列生成标识符
* $(curdate)当前日期和时间

运算符需要“sql”权限才能使用此函数，否则将引发异常。

## 功能

**类的方法：** [DBEngine](c-dbengine.md)

**可用位置：**

* 内容管理
* 投放属性
* 类型规则
* JSSP
* SOAP方法
* WebApp
* 工作流
