---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '35'
ht-degree: 54%
---
# GetEntityIfMoreRecent

如果实体的 MD5 键与作为参数给出的键不同，则加载实体

```text
XML doc = GetEntityIfMoreRecent ( String pk, String md5, Boolean mustExist )
```

## 参数

**pk**&#x200B;主键

**md5** MD5密钥

**mustExist**

## 返回值

**doc**&#x200B;结果

## 功能

**架构：** [xtk:session](s-xtk-session.md)

**静态：**

是
