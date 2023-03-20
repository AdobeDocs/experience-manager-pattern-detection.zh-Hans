---
title: ASO
description: Pattern Detector 代码帮助页面
exl-id: 2ba416b7-80c1-4ec5-a6bf-d80f6d625b07
source-git-commit: 9b46c353b052da43eca7ed636f62e08109f74aab
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 100%

---

# ASO {#aso}

AEM 系统概述

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_aso_overview"
>title="AEM 系统概述"
>abstract="ASO 代码标识有关 AEM 实例的一般信息。每个发现提供一个特定类型系统信息的值，为您的迁移规划和重构工作提供帮助。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html" text="AEM as a Cloud Service - 发行说明"

`ASO` 代码标识有关 AEM 实例的一般信息。每个发现提供一个特定类型系统信息的值。

子类型用于标识信息的不同类型：

* `aem.version`：AEM 版本。
* `aem.product`：检测使用的 AEM 产品（Commerce、Forms 等）。
* `node.count`：特定类型的大约节点计数（Page、Asset 等）和节点总数。
* `node.store`：节点存储实现类型（SegmentNodeStore、DocumentNodeStore）及其大小。
* `data.store`：数据存储实现类型（FileDataStore、S3DataStore、AzureDataStore）。
* `maintenance.task`：维护任务。
* `slow.query`：查询缓慢。
* `group.membership`：组中的用户数和子组数（仅限直接成员/声明的成员）。
* `cqtag.count`：CQ 标记的资源数。
* `smarttag.count`：智能标记的资源数。
* `ccom.version`：核心组件软件包的版本。
* `instance.type`：AEM 实例类型（author|publish）。
* `unprocessed.asset.count`：未处理的资源数。
* `vanity.url.count`：虚 URL 的数量。
* `index.size`：可迁移的 Lucene 索引总大小。

## 可能的后果和风险 {#implications-and-risks}

* 提供了 AEM 版本、节点计数、组成员资格、节点存储、数据存储实现类型、CQ 标记计数、智能标记计数、核心组件版本、AEM 实例类型和未处理的资源计数用于信息目的。
* 数量较多的虚名 URL（超过 1000）会延长查询时间，从而增加 Dispatcher 和 Publish 服务器的负载。
* 自定义应用程序可能依赖于 AEM as a Cloud Service 中不可用的产品或特性。
* 升级不支持的功能可能会导致升级失败以及应用程序无法使用。

## 可采用的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_aso_guidance"
>title="实施指南"
>abstract="通过 ASO 代码公开的信息向您提供 AEM 环境的一般信息，包括版本、产品加载项、系统级别信息，对于 AEM as a Cloud Service 中任何不支持的产品和功能，需要查看此信息。请联系 Adobe 支持部门获取帮助或说明。"
>additional-url="https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支持"

* 建议不要进行不支持的产品或功能的 AEM 升级，可能会不支持此操作。
* 必须对未处理资源进行处理，且将资源的 jcr:content 节点的 dam:assetState 属性设置为“已处理”，或者将这些资源从迁移集中移除，然后才能迁移到 AEMaaCS。
* 可使用 Apache Rewrite 替换虚名 URL。
* 查看[发行说明](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html)以了解 AEM as a Cloud Service 中的最新更改。
* 请联系我们的 [AEM 支持团队](https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html)获取说明或解决问题。
