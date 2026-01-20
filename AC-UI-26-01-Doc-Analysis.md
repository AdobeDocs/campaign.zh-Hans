---
source-git-commit: 548b4be24e26a6970f953f92af1f89d829689592
workflow-type: tm+mt
source-wordcount: '1522'
ht-degree: 0%

---
# AC-UI-26-01文档分析

## 下一版本内容

本文档分析AC-UI-26-01和AC-UI-25-11月度版本的产品JIRA以计划文档行动。

### JIRA过滤器

1. **[AC-UI-26-01-Monthly Stories](https://jira.corp.adobe.com/issues/?jql=project%20%3D%20NEO%20AND%20fixVersion%20%3D%20AC-UI-26-01-Monthly%20and%20type%20%3D%20story%20order%20by%20status)** — 主要版本故事
2. **[NEO-92400改进](https://jira.corp.adobe.com/issues/?jql=issueFunction%20in%20linkedIssuesOf(%27key%3DNEO-92400%27%2C%20%27is%20implemented%20by%27))** — 版本改进链接问题
3. **[AC-UI-25-11-Monthly Stories](https://jira.corp.adobe.com/issues/?jql=project%20%3D%20NEO%20AND%20fixVersion%20%3D%20AC-UI-25-11-Monthly%20and%20type%20%3D%20story%20order%20by%20status)** — 上一版本转接
4. **[AC-UI-25-11，不包括8.8.2](https://jira.corp.adobe.com/issues/?jql=project%20%3D%20NEO%20AND%20fixVersion%20%3D%20AC-UI-25-11-Monthly%20and%20fixVersion%20!%3D%208.8.2%20and%20type%20%3D%20story%20order%20by%20status)** — 已过滤以前的版本

---

## 🟢创建DOCAC

### [NEO-91565](https://jira.corp.adobe.com/browse/NEO-91565) — 添加对个性化字段的支持(高级AEM集成)
**状态：**&#x200B;已解决\
**需要文档：**&#x200B;是\
**现有DOCAC：**&#x200B;无\
**操作：**&#x200B;创建DOCAC

**范围：**
- 文档支持高级AEM集成中的个性化字段
- UI工作流和配置步骤
- AEM多语言集成功能

**功能描述：**
支持使用高级AEM集成在投放中添加个性化字段，支持将来自Campaign数据的动态内容插入到AEM创作的电子邮件模板中。

**上下文：** ACS到ACC的奇偶校验，特定于MSFT的要求

**引用：** [AEM多语言Wiki](https://wiki.corp.adobe.com/pages/viewpage.action?pageId=2988189953)

---

### [NEO-93487](https://jira.corp.adobe.com/browse/NEO-93487) — 投放计划计算进程（ACS奇偶校验）
**状态：**&#x200B;新\
**需要文档：**&#x200B;是\
**现有DOCAC：**&#x200B;无\
**操作：**&#x200B;创建DOCAC

**范围：**
- 推送通知的文档投放计划计算流程
- 基于时区的计划公式
- 多时区定位的文件上传

**功能描述：**
启用基于文件的OOTB投放计划，其中计算出了基于收件人时区的发送时间，从而允许跨多个时区进行单次投放定位，并优化了每个区域的发送时间。

**上下文：**&#x200B;客户驱动(H&amp;M)，ACS到ACC奇偶校验要求

**引用：** [ACS文档](https://experienceleague.adobe.com/en/docs/campaign-standard/using/testing-and-sending/scheduling-messages/computing-the-sending-date)

---

## 🔄更新DOCAC

### [NEO-80973](https://jira.corp.adobe.com/browse/NEO-80973) — 所有Web UI用户的动态报告可用性
**状态：**&#x200B;正在进行中\
**需要文档：**&#x200B;是\
**现有DOCAC：** [DOCAC-11070](https://jira.corp.adobe.com/browse/DOCAC-11070)（已关闭），[DOCAC-13432](https://jira.corp.adobe.com/browse/DOCAC-13432)（已解决）\
**操作：**&#x200B;审阅DOCAC

**范围：**
- 更新可用性信息（现在适用于所有Web UI用户，而不仅仅是8.7）
- 文档语言限制
- 阐明与旧版报表显示的冲突量度

**功能描述：**
现在，所有Campaign Web UI用户（以前限制为ACC客户使用8.7个ACS）都可以使用动态报告，通过ACS样式的界面提供高级分析和自定义报告功能。

**上下文：**&#x200B;功能扩展，后端生成依赖项(8.8.1)

**引用：** [维客 — 报表比较](https://wiki.corp.adobe.com/display/~kumarvishal/Reports+-+Client+console+vs+WebUI)

---

### [NEO-86754](https://jira.corp.adobe.com/browse/NEO-86754) - A/B测试
**状态：**&#x200B;正在进行中\
**需要文档：**&#x200B;是\
**现有DOCAC：** [DOCAC-13104](https://jira.corp.adobe.com/browse/DOCAC-13104)（新）\
**操作：**&#x200B;更新DOCAC

**范围：**
- 完成A/B测试工作流文档
- 内容试验设置和变量配置
- 样本比例定义和入选者选择标准
- 统计资料的收集和评估

**功能描述：**
针对电子邮件投放的内容试验和A/B测试，使营销人员能够测试不同的内容变体、定义样本大小、收集性能统计数据并自动将入选变体发送给其余收件人。

**上下文：** Europa项目，Microsoft要求，已启用功能标记

**引用：** [维基](https://wiki.corp.adobe.com/pages/viewpage.action?pageId=3017705719)，[Figma模拟](https://www.figma.com/design/4EfXEaA6OIV0D8rauuXSWX/A-B-Testing)

---

### [NEO-76126](https://jira.corp.adobe.com/browse/NEO-76126) — 架构创作（创建新表、扩展架构、访问外部数据库）
**状态：**&#x200B;正在进行中\
**需要文档：**&#x200B;是\
**现有DOCAC：** [DOCAC-13826](https://jira.corp.adobe.com/browse/DOCAC-13826)（新）\
**操作：**&#x200B;更新DOCAC

**范围：**
- 文档架构创作工作流（仅3个选项：创建表、扩展架构、访问外部数据库）
- 自定义实体的表单定义
- 对自定义架构执行导航和CRUD操作
- 第2阶段和第3阶段功能

**功能描述：**
Web UI中的模式创作功能允许管理员创建新的数据库表、使用自定义字段扩展现有模式以及连接到外部数据库 — 对于数据模型自定义至关重要。

**上下文：** Microsoft要求，Europa项目，分阶段交付（阶段2处于活动状态，阶段3于2月底结束）

**引用：** [PRD](https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=neolane&title=AC+Web+UI+-+Schemas+PRD)，[Figma](https://www.figma.com/design/lZkJso2HvXPbNjG0TmQTrC/Schemas)

---

### [NEO-92668](https://jira.corp.adobe.com/browse/NEO-92668) — 网站分析
**状态：**&#x200B;新\
**需要文档：**&#x200B;是\
**现有DOCAC：**&#x200B;无\
**操作：**&#x200B;创建DOCAC

**范围：**
- 网站分析外部帐户配置
- 集成设置和身份验证
- 营销活动中的Analytics数据使用

**功能描述：**
Web Analytics集成允许连接到Web Analytics平台，以便跟踪和报告营销活动效果和网站访客行为。

**上下文：**&#x200B;客户请求(P2E-RSC)，挂起的环境可用性

**引用：**&#x200B;未提供

---

### [NEO-86753](https://jira.corp.adobe.com/browse/NEO-86753) — 活动副本/语言副本的AEM集成
**状态：**&#x200B;新\
**需要文档：**&#x200B;是\
**现有DOCAC：** [DOCAC-13829](https://jira.corp.adobe.com/browse/DOCAC-13829)（已解决）\
**操作：**&#x200B;审阅DOCAC

**范围：**
- 浏览AEM投放模板
- 只需单击一下即可创建活动副本和语言副本
- 多语言内容变量创建工作流

**功能描述：**
简化的AEM集成允许从AEM投放模板一键创建活动副本和语言副本，从而简化AEM用户的多语言活动创建。

**上下文：** Microsoft要求，工作已转移到喜曼舒的团队

**引用：** [ACS文档](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/working-with-campaign-and-experience-manager/creating-multilingual-email-aem.html)

---

### [NEO-88838](https://jira.corp.adobe.com/browse/NEO-88838) — 内容编辑器：在片段中使用主题变量
**状态：**&#x200B;新\
**需要文档：**&#x200B;是\
**现有DOCAC：** [DOCAC-12941](https://jira.corp.adobe.com/browse/DOCAC-12941)（新）\
**操作：**&#x200B;更新DOCAC

**范围：**
- 电子邮件设计器(Beta)中的主题变量
- 在片段中使用主题
- Acrite功能激活

**功能描述：**
支持在内容片段中使用主题变量，从而能够通过集中的主题管理跨电子邮件组件实现一致的品牌推广和设计系统应用程序。

**上下文：**&#x200B;已搁置，要重新访问的Acrite功能

**引用：** [ATU-5460](https://jira.corp.adobe.com/browse/ATU-5460)

---

## ➕创建DOCAC（改进）

### [NEO-92942](https://jira.corp.adobe.com/browse/NEO-92942) — 预定义过滤器 — 共享选项
**状态：**&#x200B;已解决\
**需要文档：**&#x200B;是\
**现有DOCAC：** [DOCAC-13697](https://jira.corp.adobe.com/browse/DOCAC-13697)（代码审阅），[DOCAC-13522](https://jira.corp.adobe.com/browse/DOCAC-13522)（已关闭 — 帮助程序）\
**操作：**&#x200B;审阅DOCAC

**范围：**
- 预定义过滤器的共享选项
- 与其他操作员的过滤器可见性(ACC与品牌历程行为)
- 共享过滤器的用户管理

**功能描述：**
现在，可以将预定义过滤器标记为“共享”，以便其他操作员能够看到这些过滤器，对于ACC（默认）和品牌历程（特定于用户的过滤），这些过滤器的行为会有所不同。

**上下文：**&#x200B;规则生成器增强，功能标志： enable-query-filter-shared

**引用：**&#x200B;与[NEO-88441](https://jira.corp.adobe.com/browse/NEO-88441)相关

---

### [NEO-91299](https://jira.corp.adobe.com/browse/NEO-91299) — 持续传递活动
**状态：**&#x200B;已关闭\
**需要文档：**&#x200B;是\
**现有DOCAC：** [DOCAC-13586](https://jira.corp.adobe.com/browse/DOCAC-13586)（新），[DOCAC-13808](https://jira.corp.adobe.com/browse/DOCAC-13808)（已关闭 — 上下文帮助）\
**操作：**&#x200B;更新DOCAC

**范围：**
- 连续投放工作流活动
- 投放模板选取器配置
- 自动出站过渡生成
- 定位选项（无内容访问权限）

**功能描述：**
工作流的连续投放活动支持从模板重复投放执行，无需修改内容即可自动为工作流编排生成叫客过渡。

**上下文：**&#x200B;功能标志： enable-continuous-delivery

**引用：**&#x200B;相关史诗[NEO-67972](https://jira.corp.adobe.com/browse/NEO-67972)

---

### [NEO-90130](https://jira.corp.adobe.com/browse/NEO-90130) — 为多语言推送通知启用OOTB文件上载
**状态：**&#x200B;已关闭\
**需要文档：**&#x200B;是\
**现有DOCAC：** [DOCAC-13606](https://jira.corp.adobe.com/browse/DOCAC-13606)（新）\
**操作：**&#x200B;更新DOCAC

**范围：**
- 多语言推送通知的文件上传(iOS和Android)
- CSV格式和字段映射
- 具有多语言功能的富推送支持

**功能描述：**
OOTB文件上传功能，用于通过CSV导入创建多语言推送通知投放，匹配ACS功能并启用高效的多语言活动配置。

**上下文：**&#x200B;客户驱动(H&amp;M)，ACS到ACC奇偶校验，对于迁移至关重要

**引用：** [ACS文档](https://experienceleague.adobe.com/en/docs/campaign-standard/using/communication-channels/push-notifications/generating-csv-multilingual-push)

---

## ❌已取消/不再适用

### [NEO-91566](https://jira.corp.adobe.com/browse/NEO-91566) — 在webui中支持CTA跟踪
**状态：**&#x200B;已关闭（不再适用）\
**需要文档：**&#x200B;否\
**现有DOCAC：** [DOCAC-13821](https://jira.corp.adobe.com/browse/DOCAC-13821)（新）\
**操作：**&#x200B;关闭DOCAC

**原因：**&#x200B;支持MSFT的新ACS功能 — 未启动，来自MSFT的待处理信息，没有预期的UI工作

**上下文：**&#x200B;特定于Microsoft的CTA跟踪要求

---

### [NEO-91564](https://jira.corp.adobe.com/browse/NEO-91564) - AEM多语言UI支持
**状态：**&#x200B;已关闭（不再适用）\
**需要文档：**&#x200B;否\
**现有DOCAC：** [DOCAC-13822](https://jira.corp.adobe.com/browse/DOCAC-13822)（新）\
**操作：**&#x200B;关闭DOCAC

**原因：** UI工作由Himanshu的团队管理（不同的故事）

**上下文：** Microsoft要求，工作已转移

---

### [NEO-91567](https://jira.corp.adobe.com/browse/NEO-91567) — 添加对NRT功能的支持
**状态：**&#x200B;已解决（不再适用）\
**需要文档：**&#x200B;否\
**现有DOCAC：** [DOCAC-13824](https://jira.corp.adobe.com/browse/DOCAC-13824)（新）\
**操作：**&#x200B;关闭DOCAC

**原因：**&#x200B;针对MSFT的新ACS特定功能 — 规范可用，但对Web UI没有影响

**上下文：** Microsoft要求，事务型消息传递

---

### [NEO-91563](https://jira.corp.adobe.com/browse/NEO-91563) — 用于基于用户档案的扩充的事务性Rest API
**状态：**&#x200B;已解决（不再适用）\
**需要文档：**&#x200B;否\
**现有DOCAC：** [DOCAC-13825](https://jira.corp.adobe.com/browse/DOCAC-13825)（新）\
**操作：**&#x200B;关闭DOCAC

**原因：**&#x200B;没有Web UI工作，挂起的升级实例需要版本升级

**上下文：** REST API终结点功能

---

### [NEO-92151](https://jira.corp.adobe.com/browse/NEO-92151) — 基于用户档案的扩充事务型消息传递阶段2
**状态：**&#x200B;已解决（不再适用）\
**需要文档：**&#x200B;否\
**现有DOCAC：** [DOCAC-13823](https://jira.corp.adobe.com/browse/DOCAC-13823)（新）\
**操作：**&#x200B;关闭DOCAC

**原因：**&#x200B;故事没有任务，标记为“不再适用”

**上下文：** Microsoft要求，Europa项目

---

## 🟢文档就绪（从AC-UI-25-11）

### [NEO-90183](https://jira.corp.adobe.com/browse/NEO-90183) — 多语言富推送 — UI
**状态：**&#x200B;已关闭\
**需要文档：**&#x200B;是\
**现有DOCAC：** [DOCAC-13565](https://jira.corp.adobe.com/browse/DOCAC-13565)（新）\
**操作：**&#x200B;审阅DOCAC

**范围：**
- 多语言投放的富推送字段
- iOS和Android平台支持
- 模板和内容配置

**功能描述：**
富推送通知支持具有多语言功能，可让营销人员为iOS和Android创建具有图像、按钮和富媒体的增强型推送通知，并使用多种语言。

**上下文：**&#x200B;客户驱动型(H&amp;M)，25-11交付，后端工作已完成

**引用：** [维客](https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=neolane&title=Rich+push+fields+in+multilingual)

---

### [NEO-84916](https://jira.corp.adobe.com/browse/NEO-84916) — 设置和管理审批流程
**状态：**&#x200B;已解决\
**需要文档：**&#x200B;是\
**现有DOCAC：** [DOCAC-13827](https://jira.corp.adobe.com/browse/DOCAC-13827)（新）\
**操作：**&#x200B;更新DOCAC

**范围：**
- 在投放/营销活动中配置验证运算符
- 审批工作流设置
- 内容和目标审批流程
- 多渠道支持（电子邮件、短信、推送、直邮、呼叫中心、自定义）

**功能描述：**
批准流程管理允许使用验证工作流来交付内容和定位，操作员可跨所有交付渠道进行分配和批准跟踪。

**上下文：**&#x200B;客户驱动(Pierre Fabre)，Microsoft要求，开发完成和正在测试

**引用：** [经典文档](https://experienceleague.adobe.com/en/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-approval)，[Figma模拟](https://www.figma.com/design/r2vpqXoVyI3aucKgkt8TLN/Approvals)

---

## 按操作显示的📊摘要

| 操作 | 计数 |
|--------|-------|
| 🟢创建DOCAC | 3 |
| 🔄更新DOCAC | 6 |
| ✅审阅DOCAC | 3 |
| ❌关闭DOCAC | 5 |
| **总计** | **17** |

---

## ⚠️个未完成的问题

1. Neo-93487 - H&amp;M提升 — 需要紧急关注计算流程的时间安排
2. Neo-92668 - Web Analytics — 等待环境可用性，然后才能完成文档
3. Neo-76126 — 架构第3阶段 — ETA 2月底结束，需要单独的文档故事
4. Neo-88838 — 主题变量 — 已搁置，等待Acrite功能修订
5. 动态报告 — 通过旧版报告阐明冲突量度显示指导

---

## 🔗个相关Epic

- Neo-85263 - ACS到ACC (EUROPA)父级epic
- Neo-67972 — 工作流改进
- Neo-87980 — 高级AEM集成
- Neo-90199 - Dynamic Reporting版本准备工作
- Neo-63067 — 内容试验UX/UI
- Neo-67726 - A/B测试和内容实验
- Neo-85274 — 架构和表单（阶段2）
- Neo-87993 — 架构和表单（阶段3）
