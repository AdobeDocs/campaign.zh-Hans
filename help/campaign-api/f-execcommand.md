---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 5%
---
# 执行命令

> 警告：此函数适用于内部部署环境。

执行命令并捕获错误代码和标准输出。

```text
execCommand (command [, bNoThrow ])
```

## 参数

**command**&#x200B;要执行的命令及其参数。

**bNoThrow** true以获取输出和错误代码，即使命令未返回零（默认情况下为false）。

## 返回值

返回其第一个元素对应于命令的返回代码的表（如果返回代码与零不同，则存在异常），第二个元素是包含生成的标准输出的字符串。

## 备注

如果不使用bNothrow选项，则在无法执行命令或执行命令时引发异常。 如果bNoThrow等于true，则仅当无法执行命令时才会引发异常。 运算符需要“createProcess”权限才能使用此函数，否则将引发异常。 根据您的安装，阻止列表上可能会显示一些命令。 例如：ln、dd、openssl、curl、wget、python、python3、perl、ruby、sh、bash、dash、zsh、base64、nlserver、node、phantomjs、java、awk、nc、telnet、ssh、scp、ftp。

## 示例

```text
var result = execCommand('gpg-exec.sh gpg --no-tty --yes -r CampaignOperations@adobe.com --encrypt "file_to_encrypt"', true);
```

## 功能

**可用位置：**

* 内容管理
* 投放属性
* 类型规则
* JSSP
* SOAP方法
* WebApp
* 工作流
