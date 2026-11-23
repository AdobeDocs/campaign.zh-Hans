---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '86'
ht-degree: 10%
---
# getEntry

从存档中提取文件。

```text
getEntry (filename)
```

## 参数

**文件名**&#x200B;存档中文件的名称。

## 返回值

包含文件内容的⌐ [MemoryBuffer](c-memorybuffer.md)。

## 备注

存档必须已使用⌐[open()](m-zipfile-open.md)方法打开，然后才能使用此方法。 否则，将引发异常。 示例：以下示例从归档文件中提取dir/content.xml文件并将其保存到/tmp/文件夹。

```javascript
var zip = new ZipFile("/tmp/archive.zip")
zip.open()

var content = zip.getEntry("dir/content.xml")
content.save("/tmp/content.xml")

zip.dispose()
content.dispose()
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
