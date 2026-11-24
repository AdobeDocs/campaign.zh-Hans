---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 5%
---
# 文件（类）

文件类

> 警告：
>
> 通过文件API进行的访问仅限于&#x200B;**var**、**sftp**&#x200B;和Adobe Campaign的临时文件夹。

以下是如何使用类按顺序读取和处理文件所有行的示例。

```javascript
var file = new File("/tmp/test.txt")
file.open()
for each(var line in file)
  logInfo(line)
file.close()
 
```

## 方法

| 方法 | 描述 |
| --- | --- |
| [文件](m-file-file.md) | 创建与文件关联的新对象。 |
| [关闭](m-file-close.md) | 关闭文件。 |
| [复制到](m-file-copyto.md) | 复制文件。 |
| [处置](m-file-dispose.md) | 释放对象使用的资源。 |
| [刷新](m-file-flush.md) | 强制在磁盘上写入 |
| [列表](m-file-list.md) | 列出目录的内容。 |
| [mkdir](m-file-mkdir.md) | 使用当前[File](c-file.md)对象的路径创建目录。 |
| [打开](m-file-open.md) | 在读取或写入模式下打开文件。 |
| [移除](m-file-remove.md) | 删除文件。 |
| [renameTo](m-file-renameto.md) | 重命名文件。 |
| [readln](m-file-readln.md) | 读取文本文件的一行。 |
| [rmdir](m-file-rmdir.md) | 删除目录（不是级联的）。 |
| [写入](m-file-writeln.md) | 将一行文本写入文件。 |

## 属性

| 属性 | 描述 |
| --- | --- |
| [canRead](p-file-canread.md) | 如果可以读取文件，则返回true。 |
| [canWrite](p-file-canwrite.md) | 如果可以修改文件，则返回true。 |
| [存在](p-file-exists.md) | 如果存在具有此名称的文件或文件夹，则返回true。 |
| [全名](p-file-fullname.md) | 以绝对值返回文件的名称。 |
| [isDirectory](p-file-isdirectory.md) | 如果文件是目录，则返回true。 |
| [isFile](p-file-isfile.md) | 如果文件存在并且是文件，则返回true。 |
| [isOpen](p-file-isopen.md) | 如果文件处于打开状态，则返回true。 |
| [lastModified](p-file-lastmodified.md) | 以Date对象的形式返回上次修改日期。 |
| [名称](p-file-name.md) | 返回扩展名为，但不包含路径的文件名。 |
| [路径](p-file-path.md) | 返回以分隔符结尾的文件的完整路径。 |
| [大小](p-file-size.md) | 返回文件的大小（以字节为单位）。 |

## 功能

**可用位置：**

* 内容管理
* 投放属性
* 类型规则
* JSSP
* SOAP方法
* WebApp
* 工作流
