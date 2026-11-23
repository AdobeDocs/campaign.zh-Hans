---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 73%
---
# 生成器

应用程序服务器的生成服务

## 方法

| 方法 | 描述 |
| --- | --- |
| [BuildOutputNavTree](sm-builder-buildoutputnavtree.md) | 将在数据库中找到的导航树定义与参数中给定的导航树定义合并。 |
| [BuildOutputSchema](sm-builder-buildoutputschema.md) | 从源架构生成架构。 |
| [BuildSchema](sm-builder-buildschema.md) | 从源架构生成架构。 |
| [BuildSchemaFromId](sm-builder-buildschemafromid.md) | 从源架构标识符生成架构。 |
| [BuildSqlSchemaDiff](sm-builder-buildsqlschemadiff.md) | 生成文档，其中描述了实际数据库结构与其逻辑描述之间的差异。 |
| [BuildUpdateOneSchemaDiff](sm-builder-buildupdateoneschemadiff.md) | 生成文档，其中描述了物理数据库中的表与该表的逻辑描述之间的差异。 |
| [BuildUpdateSchemaDiff](sm-builder-buildupdateschemadiff.md) | 生成文档，其中描述了实际数据库结构与其逻辑描述之间的差异。 |
| [检查表存在](sm-builder-checktableexists.md) | 验证数据库中是否存在表 |
| [CreateDb](sm-builder-createdb.md) | 创建数据库 |
| [EvaluateJavaScript](sm-builder-evaluatejavascript.md) | 评估 JavaScript 代码。 |
| [EvaluateJavaScriptTemplate](sm-builder-evaluatejavascripttemplate.md) | JavaScript 模板 (JST) 评估。 |
| [ExecSql](sm-builder-execsql.md) | 执行 SQL 语句 |
| [ExecSqlScript](sm-builder-execsqlscript.md) | 执行 SQL 脚本 |
| [GenCreateDbDDL](sm-builder-gencreatedbddl.md) | 生成用于创建数据库结构的 SQL 脚本。 |
| [GenCreateOrUpdateSchemaSequenceDDL](sm-builder-gencreateorupdateschemasequenceddl.md) | 生成用于创建或更新 autoPk 架构序列的 SQL 脚本 |
| [GenerateNavTree](sm-builder-generatenavtree.md) | 合并所有导航树定义并将结果保存为“xtk:merged”。 |
| [GenerateSchema](sm-builder-generateschema.md) | 使用高级参数生成架构代码。 |
| [GetDbParams](sm-builder-getdbparams.md) | 检索数据源的当前参数。 |
| [GetDefaultNamespace](sm-builder-getdefaultnamespace.md) | 检索默认命名空间。 |
| [InstallPackage](sm-builder-installpackage.md) | 安装包。 |
| [InstallPackageImpl](sm-builder-installpackageimpl.md) | 安装包（内部方法，不要使用）。 |
| [InstallVendorPackages](sm-builder-installvendorpackages.md) | 安装一个或多个标准包。 |
| [RemoveSchemaLinkRef](sm-builder-removeschemalinkref.md) | 删除架构和引用它的反向链接。 |
| [解析包引用](sm-builder-resolvepackagereferences.md) | 解决包中的依赖项 |
| [UpdateDb](sm-builder-updatedb.md) | 数据库结构更新。 |
| [UpdateSchemaFromDatabase](sm-builder-updateschemafromdatabase.md) | 根据架构在数据库中的物理呈现更新架构集。 |
| [UpdateTempSchemasFromDatabase](sm-builder-updatetempschemasfromdatabase.md) | 根据架构在数据库中的物理呈现更新架构收藏集。 |

## 常规方法

| 方法 | 描述 |
| --- | --- |
| [创建](f-create.md) | 创建与给定架构对应的新实体。 |
| [加载](f-load.md) | 加载并返回与给定架构和键对应的实体。 |
| [保存](m-entity-save.md) | 在数据库中保存实体。 |
