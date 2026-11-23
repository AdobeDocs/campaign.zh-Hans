---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 6%
---
# cryptString

> 警告：
>
> 此函数已完全弃用。 有关更多详细信息，请参阅此[页](https://experienceleague.adobe.com/zh-hans/docs/campaign-classic/using/technotes/gcm-functions#deprecated-functions-headding-anchor-depracated-functions)。

使用实例的键或任何其他键加密字符串。

```text
cryptString (str [, key ] [, useSalt ])
```

## 参数

**str**&#x200B;要加密的字符串。

**key** AES加密密钥以base 64编码：如果密钥长度为32，则为256位；如果密钥长度为24，则为192位；如果密钥长度为16或未指定密钥，则为128位。

**useSalt**&#x200B;使用加密数据盐进行加密。 默认情况下为True。

## 返回值

返回加密的字符串

## 备注

加密按照以下方法进行：

* unicode字符串将转换为UTF-8字符串。
* 在末尾添加一个检查字符。
* 此字符串在加密块链接(CBC)模式下使用AES算法加密，初始化矢量为null。 如果未提供键作为参数，则使用实例键。
* 然后将加密块转换为基数64。

使用[decryptString](f-decryptstring.md)函数执行解密。

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
