---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '60'
ht-degree: 15%
---
# fileGetTempName

生成临时文件名。

```text
fileGetTempName ( [directory ] [, prefix ] [, extension ])
```

## 参数

临时文件的&#x200B;**目录**&#x200B;目录。 如果为空，则使用系统定义的临时目录。

**前缀**&#x200B;最多包含4个字符。 如果为空，则使用tmp前缀。

**扩展名**&#x200B;文件扩展名。

## 返回值

文件的全名。

## 功能

**可用位置：**

* 内容管理
* 投放属性
* 类型规则
* JSSP
* SOAP方法
* WebApp
* 工作流
