---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '62'
ht-degree: 17%
---
# Zip文件

> 警告：
>
> 通过文件API进行的访问仅限于&#x200B;**var**、**sftp**&#x200B;和Adobe Campaign的临时文件夹。

创建与文件关联的新Zip对象。

```text
ZipFile (filename)
```

## 参数

**filename**&#x200B;要加载或创建的存档的名称。

## 返回值

无。

## 备注

示例：

```javascript
var zip = new ZipFile("/tmp/archive.zip")
```

## 功能

**类的方法：** [ZipFile](c-zipfile.md)

**可用位置：**

* 内容管理
* 投放属性
* 类型规则
* JSSP
* SOAP方法
* WebApp
* 工作流
