---
source-git-commit: 77f8182ea5b1fda08206021a164b2e0ff827890a
workflow-type: tm+mt
source-wordcount: '72'
ht-degree: 16%
---
# getEnv

>[!WARNING]
>
>此函数适用于内部部署环境。

>[!NOTE]
>
>您可以将&#x200B;**XtkSecurity\_Disable\_GetSetEnv**&#x200B;选项传递给&#x200B;**true**&#x200B;来禁用此函数。

返回环境变量的值。

```text
getEnv (name [, default ])
```

## 参数

**name**&#x200B;变量的名称。

**默认值**&#x200B;在未找到环境变量时使用的默认值。

## 返回值

变量的值。

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
