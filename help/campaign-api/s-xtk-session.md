---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 73%
---
# session

应用程序服务器的会话

## 方法

| 方法 | 描述 |
| --- | --- |
| [ApplyDuplicateRules](sm-session-applyduplicaterules.md) | 将复制设置（包括默认值）应用于指定文档 |
| [BearerTokenLogon](sm-session-bearertokenlogon.md) | 连接令牌 |
| [更改密码](sm-session-changepassword.md) | 更改当前密码 |
| [DeleteCollection](sm-session-deletecollection.md) | 根据条件删除实体列表 |
| [差异](sm-session-diff.md) | 返回文档的当前版本和原始版本。 |
| [重复](sm-session-duplicate.md) | 从源文档创建新文档 |
| [复制到](sm-session-duplicateto.md) | 将源自源文档的新文档复制到给定文件夹 |
| [DuplicateWithMappingId](sm-session-duplicatewithmappingid.md) | 使用 ID 映射从源文档复制新文档 |
| [加密](sm-session-encrypt.md) | 使用实例密钥对字符串进行加密。 |
| [EncryptServerPassword](sm-session-encryptserverpassword.md) | 使用服务器密钥对字符串进行加密。 |
| [FormatDataPolicy](sm-session-formatdatapolicy.md) | 根据作为参数传递的数据策略，将转换应用于字符串。 如果失败，则保留字符串不变。 |
| [GetActiveApplicationMenus](sm-session-getactiveapplicationmenus.md) | 返回文档，其中包含为当前登录启用的应用程序的菜单 |
| [GetCnxInfo](sm-session-getcnxinfo.md) | 从当前连接中恢复信息。 |
| [GetDefaultEntity](sm-session-getdefaultentity.md) | 返回一个包含具有默认值的空实体的文档 |
| [GetDirtyCacheEntities](sm-session-getdirtycacheentities.md) | 返回脏缓存实体 |
| [GetEntityIfMoreRecent](sm-session-getentityifmorerecent.md) | 如果实体的 MD5 键与作为参数给出的键不同，则加载实体 |
| [获取图像](sm-session-getimages.md) | 加载图像列表 |
| [GetNewIds](sm-session-getnewids.md) | 收集数据库的内部键标识符列表。 |
| [GetNewIdsEx](sm-session-getnewidsex.md) | 给定序列名称的情况下从数据库中获取唯一标识符列表。 |
| [GetOption](sm-session-getoption.md) | 返回存储在数据库中的选项的值。 |
| [GetPkList](sm-session-getpklist.md) | 获取实例标识符的列表 |
| [GetServerTime](sm-session-getservertime.md) | 返回服务器日期和时间 |
| [GetUserInfo](sm-session-getuserinfo.md) | 有关当前操作员的信息 |
| [HashPassword](sm-session-hashpassword.md) | 使用服务器密钥对密码进行散列。 |
| [ImportCollection](sm-session-importcollection.md) | 使用导入更新实体列表 |
| [终止会话](sm-session-killsession.md) | 关闭指定的会话 |
| [加载](sm-session-load.md) | 加载实体 |
| [LoadAsText](sm-session-loadastext.md) | 检索文本形式的实体内容 |
| [LoadIfExist](sm-session-loadifexists.md) | 加载实体（如果存在） |
| [注销](sm-session-logoff.md) | 关闭当前会话 |
| [登录](sm-session-logon.md) | 打开会话 |
| [NewInstance](sm-session-newinstance.md) | 新文档创建，已预初始化但未保存 |
| [移除](sm-session-remove.md) | 删除实体 |
| [服务器关机](sm-session-servershutdown.md) | 请求服务器关闭 |
| [设置默认值](sm-session-setdefaultvalues.md) | 默认情况下根据 xpath 修复值 |
| [SetDefaults](sm-session-setdefaults.md) | 设置默认值 |
| [TestCnx](sm-session-testcnx.md) | 测试连接。 |
| [写入](sm-session-write.md) | 更新实体 |
| [WriteCollection](sm-session-writecollection.md) | 更新实体列表 |

## 常规方法

| 方法 | 描述 |
| --- | --- |
| [创建](f-create.md) | 创建与给定架构对应的新实体。 |
| [加载](f-load.md) | 加载并返回与给定架构和键对应的实体。 |
| [保存](m-entity-save.md) | 在数据库中保存实体。 |
