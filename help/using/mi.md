---
title: MI
description: Pattern Detector 代码帮助页面。
exl-id: fa47ac63-1b5d-43b3-8acd-4a71c3fa714e
source-git-commit: 0d693e3ccadc81b59852914f115bb2fa2ea166b0
workflow-type: ht
source-wordcount: '199'
ht-degree: 100%

---

# MI {#mi}

配置不当问题

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_mi_overview"
>title="配置不当问题"
>abstract="MI 可标识 AEM 实例上的配置问题"

`MI`（配置不当问题）标识 AEM 实例上的配置问题。

子类型用于标识不同类型的信息，例如：

* `sling.job.max.parallel`：标识最大并行配置被设置为 -1 的 Sling 作业。
* `missing.maintenance.configuration`：标识缺少的维护任务配置。

## 可能产生的后果和风险 {#implications-and-risks}

* `sling.job.max.parallel`
   * -1 的值被替换为可用的处理器数量。因此，这可能在 AEM 实例上导致性能问题。
* `missing.maintenance.configuration`
   * 缺少维护任务配置可能会导致性能损失或实例损坏。

## 可采用的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_mi_guidance"
>title="实施指南"
>abstract="联系客户关怀部门寻求帮助。"
>additional-url="https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支持"

* `sling.job.max.parallel`
   * Adobe 建议将该值设置为 0.5，以利用一半的可用处理器。
* `missing.maintenance.configuration`
   * Revision Clean Up：参见 [修订清理](https://experienceleague.adobe.com/zh-hans/docs/experience-manager-65/content/implementing/deploying/deploying/revision-cleanup)。以下是关于配置的重要部分：[修订版清理 - 配置尾部压缩和完全压缩](https://experienceleague.adobe.com/zh-hans/docs/experience-manager-65/content/implementing/deploying/deploying/revision-cleanup)。
   * Lucene Binaries Cleanup：请参阅 [操作仪表板 - Lucene 二进制清理](https://experienceleague.adobe.com/zh-hans/docs/experience-manager-65/content/sites/administering/operations/operations-dashboard#lucene-binaries-cleanup)。
   * Data Store Garbage Collection：请参阅[数据存储垃圾收集](https://experienceleague.adobe.com/zh-hans/docs/experience-manager-65/content/sites/administering/operations/data-store-garbage-collection)。
   * Workflow Purge：请参阅[定期清除工作流实例](https://experienceleague.adobe.com/zh-hans/docs/experience-manager-65/content/sites/administering/operations/workflows-administering#regular-purging-of-workflow-instances)。
   * AuditLog Maintenance Task：请参阅[审核日志维护](https://experienceleague.adobe.com/zh-hans/docs/experience-manager-65/content/sites/administering/operations/operations-audit-log)。
* 请联系我们的 [Experience Manager 客户服务团队](https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html)进行澄清或解决疑惑。
