---
product: Adobe Campaign
title: Campaign v8 发行说明
description: 最新 Campaign v8 版本
feature: 概述
role: Data Engineer
level: Beginner
hidefromtoc: false
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471,a9d18e75-18e7-491e-bfc4-671c3600396e
source-git-commit: 328f1bca11f8554def6ad4ccb741a86695481e98
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 7%

---

# 最新版本{#latest-release}

本页列出了&#x200B;**最新Campaign v8版本**&#x200B;随附的新功能、改进和修复。

## 8.1.14 版 {#release-8-1-14}

_2021年7月23日_

**新增功能**

<table>
<thead>
<tr>
<th><strong>新的工作流活动：更改数据源</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>新的<b>更改数据源</b>工作流活动允许您更改工作流工作表的数据源。 这提高了跨不同数据源（FDA、FDDA和本地数据库）管理数据的灵活性。</p>
<p>在Adobe Campaign工作流中，使用工作（或临时）表管理数据。 工作流执行时，工作表会在工作流活动之间共享数据。 默认情况下，工作表创建在与我们查询的数据源相同的数据库中。</p>
<p>使用Campaign v8，主用户档案表直接存储在云数据库中。 因此，查询Profiles表也会在云数据库上创建一个工作表。 在某些情况下，将工作表移动到其他数据源以执行特定操作是有意义的。</p>
<p>有关详细信息，请参阅<a href="../config/workflows.md#change-data-source-activity">详细文档</a>。</p>
</td>
</tr>
</tbody>
</table>

<table> 
<thead>
<tr> 
<th> <strong>LINE渠道可用性</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p><a href="../send/line.md">LINE channel</a>现在可在Campaign v8中使用，包括与<a href="../send/transactional.md">事务性消息传递</a>模块结合使用时的以下增强功能：
<ul> 
<li><p>修复了可能会阻止在LINE投放中定位访客的问题。 
</p></li>
<li><p>修复了在从执行实例检索访客到营销实例时可能导致错误的问题。
</p></li>
<li><p>修复了实时事件处理过程中的问题。</p></li>
</ul>
</td> 
</tr> 
</tbody> 
</table>

**其他改进**

* 修复了可能阻止针对特定投放显示&#x200B;**热门点击**&#x200B;报表的问题。
* 修复了&#x200B;**重复数据删除**&#x200B;工作流活动中可能导致重复计数不准确的问题。
* 修复了在使用具有“ID不为空”过滤器的工作流查询时，可能会导致在过渡群体中显示空项目的问题。
* 修复了阻止在新目标映射中创建其他字段的问题。
