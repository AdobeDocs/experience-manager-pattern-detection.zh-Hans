---
title: MI
description: Pattern Detector 代码帮助页面
source-git-commit: aa05ebcb54c6945a903c76add4f31e3279cd05b5
workflow-type: tm+mt
source-wordcount: '255'
ht-degree: 26%

---

# MI {#mi}

配置错误问题

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_mi_overview"
>title="配置错误问题"
>abstract="MI标识AEM实例上的配置问题"

`MI`  配置错误问题标识了AEM实例上的配置问题。

子类型用于识别信息的不同类型，例如：

* `sling.job.max.parallel`：标识最大并行配置设置为–1的sling作业。
* `missing.maintenance.configuration`：识别缺少的维护任务配置。

## 可能的后果和风险 {#implications-and-risks}

* `sling.job.max.parallel`
   * 值–1被可用处理器数替换。 这可能会导致在AEM实例上出现性能问题。
* `missing.maintenance.configuration`
   * 缺少维护任务配置可能会导致性能下降或实例损坏。

## 可采用的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_mi_guidance"
>title="实施指南"
>abstract="联系客户关怀部门寻求帮助。"
>additional-url="https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支持"

* `sling.job.max.parallel`
   * 建议将该值设置为0.5，以便使用一半的可用处理器。
* `missing.maintenance.configuration`
   * 修订版清理：请参阅 [修订版清理](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/revision-cleanup.html). 有关配置的重要部分如下： [修订版清理 — 配置尾部和完全压缩](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/revision-cleanup.html#how-to-configure-full-and-tail-compaction).
   * Lucene二进制文件清理：请参阅 [操作功能板 — Lucene二进制文件清理](https://experienceleague.adobe.com/docs/experience-manager-65/administering/operations/operations-dashboard.html#lucene-binaries-cleanup).
   * 数据存储垃圾收集：请参阅 [数据存储垃圾收集](https://experienceleague.adobe.com/docs/experience-manager-65/administering/operations/data-store-garbage-collection.html).
   * 工作流清除：请参阅 [定期清除工作流实例](https://experienceleague.adobe.com/docs/experience-manager-65/administering/operations/workflows-administering.html#regular-purging-of-workflow-instances).
   * 审核日志维护任务：请参阅 [审核日志维护](https://experienceleague.adobe.com/docs/experience-manager-65/administering/operations/operations-audit-log.html).
* 请联系我们的 [Experience Manager 客户关怀团队](https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html)以获取说明或解决问题。