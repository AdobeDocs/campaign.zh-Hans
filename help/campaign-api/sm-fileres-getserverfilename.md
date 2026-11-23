---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 51%
---
# GetServerFileName

如有必要，在上传文件夹中复制文件后返回服务器上文件的名称。

```text
String serverFileName = fileRes.GetServerFileName ()
```

## 参数

无。

## 返回值

**serverFileName**&#x200B;服务器上文件的全名（如果找不到文件，则为空）。

## 示例

```javascript
var query = xtk.queryDef.create(
  {queryDef: {schema: "xtk:fileRes", operation: "get", 
    select: {
      node: [
      {expr: "@label"}, 
      {expr: "@originalName"}, 
      {expr: "@storageType"}, 
      {expr: "@fileName"}, 
      {expr: "@md5"}]
    }, 
    where: {
      condition: {expr: "@id = 4216"}
    }
  }})

var fileRes = xtk.fileRes.create(query.ExecuteQuery())
var sFileName = fileRes.GetServerFileName();
        
```

## 功能

**架构：** [xtk:fileRes](s-xtk-fileres.md)

**静态：**

否

**常量：**

否

仅&#x200B;**键：**

否
