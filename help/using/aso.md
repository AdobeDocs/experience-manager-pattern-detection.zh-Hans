---
title: ASO
description: Pattern Detector代码帮助页面。
exl-id: 2ba416b7-80c1-4ec5-a6bf-d80f6d625b07
source-git-commit: 616fa84f6237893243cffc8af28c7cbe76bf32d7
workflow-type: tm+mt
source-wordcount: '474'
ht-degree: 52%

---

# ASO {#aso}

AEM 系统概述

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_aso_overview"
>title="AEM 系统概述"
>abstract="ASO 代码标识有关 AEM 实例的一般信息。每个发现提供一个特定类型系统信息的值，为您的迁移规划和重构工作提供帮助。"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/release-notes/release-notes/release-notes-current" text="AEM as a Cloud Service - 发行说明"

ASO标识有关AEM实例的一般信息。 每个发现提供一个特定类型系统信息的值。

子类型用于标识信息的不同类型：

* `aem.version`：AEM 版本。
* `aem.product`：检测使用的AEM产品(Commerce、Forms等)。
* `node.count`：特定类型的大约节点数（Page、Asset等）以及节点总数。
* `node.store`：节点存储实现类型（SegmentNodeStore、DocumentNodeStore）及其大小。
* `data.store`：数据存储实现类型（FileDataStore、S3DataStore、AzureDataStore）。
* `maintenance.task`：维护任务。
* `slow.query`：查询缓慢。
* `group.membership`：组中的用户和子组数（仅限直接成员/声明的成员）。
* `cqtag.count`：CQ 标记的资源数。
* `smarttag.count`：智能标记的资源数。
* `ccom.version`：核心组件软件包的版本。
* `instance.type`：AEM 实例类型（author|publish）。
* `unprocessed.asset.count`：未处理的资源数。
* `vanity.url.count`：虚 URL 的数量。
* `index.size`：可迁移的 Lucene 索引总大小。
* `workflow.count`：处于正在运行和过时状态的创作工作流的数量。
* `jvm.arguments`：启动 AEM 时添加到命令行的 JVM 参数。

## 可能产生的后果和风险 {#implications-and-risks}

* 提供了AEM版本、节点计数、组成员资格、节点存储、数据存储实现类型、CQ标记计数、智能标记计数、核心组件版本、AEM实例类型和未处理的资源计数用于信息目的。
* 数量较多的虚名 URL（超过 1000）会延长查询时间，从而增加 Dispatcher 和 Publish 服务器的负载。
* 自定义应用程序可能依赖于 AEM as a Cloud Service 中不可用的产品或特性。
* 升级不支持的功能可能会导致升级失败以及应用程序无法使用。
* 大量处于正在运行或过时状态的创作工作流程可能会降低性能。
* 查询速度慢可能会降低系统的性能。

## 可采用的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_aso_guidance"
>title="实施指南"
>abstract="通过ASO代码公开的信息可提供您的AEM环境的一般信息，包括版本、产品加载项和系统级别信息。 查看AEMas a Cloud Service中任何不支持的产品或功能。 请联系Adobe支持部门以获取帮助或说明。"
>additional-url="https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支持"

* 不建议对不支持的产品或功能进行AEM升级，这可能不受支持。
* 必须处理未处理的资源，并且 `dam:assetState` 上的属性 `jcr:content` 必须将资源的节点设置为“已处理”。 或者，在迁移到AEMaaCS之前，您应该从迁移集中删除这些资产。
* 可使用 Apache Rewrite 替换虚名 URL。
* 请参阅 [文档](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/developing/bestpractices/troubleshooting-slow-queries) 用于解决查询速度较慢的问题。
* 请参阅 [发行说明](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/release-notes/release-notes/release-notes-current) 如果您想详细了解AEMas a Cloud Service中的最新更改。
* 联系 [AEM支持团队](https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html) 以澄清或解决问题。
