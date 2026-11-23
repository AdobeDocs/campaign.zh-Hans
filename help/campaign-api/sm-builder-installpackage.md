---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '38'
ht-degree: 18%
---
# 安装包

安装包。

```text
InstallPackage ( XML parameters )
```

## 参数

**参数**&#x200B;包含要导入的包的XML元素。

## 返回值

无。

## 备注

由SpecFile.Generate()方法生成的包必须封装在生成器元素中。 示例：

```javascript
var params =
  {builder:
    {package:
      { ... }
    }
  }

NLWS.xtkBuilder.InstallPackage(params)
```

## 功能

**架构：** [xtk:builder](s-xtk-builder.md)

**静态：**

是
