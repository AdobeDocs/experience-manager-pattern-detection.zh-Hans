---
title: MI
description: Pattern Detector代码帮助页面。
exl-id: fa47ac63-1b5d-43b3-8acd-4a71c3fa714e
source-git-commit: 84c193b66fbf9c41f546e8575a0aa17e94043b9a
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 55%

---

# MI {#mi}

配置不当问题

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_mi_overview"
>title="配置不当问题"
>abstract="MI 可识别 AEM 实例上的配置问题"

`MI` （配置错误问题）标识AEM实例上的配置问题。

子类型用于识别不同类型的信息，如：

* `sling.job.max.parallel`：识别最大并行配置被设置为 -1 的 Sling 作业。
* `missing.maintenance.configuration`：识别缺少的维护任务配置。

## 可能产生的后果和风险 {#implications-and-risks}

* `sling.job.max.parallel`
   * -1 的值被替换为可用的处理器数量。这可能在 AEM 实例上导致性能问题。
* `missing.maintenance.configuration`
   * 缺少维护任务配置可能会导致性能损失或实例损坏。

## 可采用的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_mi_guidance"
>title="实施指南"
>abstract="联系客户关怀部门寻求帮助。"
>additional-url="https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支持"

* `sling.job.max.parallel`
   * Adobe建议将该值设置为0.5以充分利用一半的可用处理器。
* `missing.maintenance.configuration`
   * 修订版清理：请参阅 [修订清理](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/deploying/deploying/revision-cleanup). 以下是关于配置的重要部分：[修订版清理 - 配置尾部压缩和完全压缩](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/deploying/deploying/revision-cleanup)。
   * Lucene二进制文件清理：请参阅 [操作功能板 — Lucene二进制文件清理](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/sites/administering/operations/operations-dashboard#lucene-binaries-cleanup).
   * 数据存储垃圾收集：请参阅 [数据存储垃圾收集](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/sites/administering/operations/data-store-garbage-collection).
   * 工作流清除：请参阅 [定期清除工作流实例](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/sites/administering/operations/workflows-administering#regular-purging-of-workflow-instances).
   * AuditLog维护任务：请参阅 [审核日志维护](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/sites/administering/operations/operations-audit-log).
* 联系 [Experience Manager客户关怀团队](https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html) 以澄清或解决问题。
