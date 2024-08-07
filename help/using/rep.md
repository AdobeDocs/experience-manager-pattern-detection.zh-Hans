---
title: REP
description: Pattern Detector 代码帮助页面。
exl-id: e788deba-a301-404f-8e90-51f721409e69
source-git-commit: 2881b122773a8a5ad09fb9a14ae35b4a83dae20d
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 100%

---

# [!DNL REP] {#rep}

复制代理

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_rep_overview"
>title="复制代理"
>abstract="REP 标识已启用的复制代理。报告这些信息是因为在升级到 AEM as a Cloud Service 时，必须解决潜在问题。AEM as a Cloud Service 使用 Sling Content Distribution 将内容从作者分发到发布环境。此分发在 AEM 运行时之外使用 Adobe Developer 上的 Adobe I/O Runtime 管道服务完成。此工作流在 AEM as a Cloud Service 环境中自动配置。"
>additional-url="https://experienceleague.adobe.com/zh-hans/docs/experience-manager-cloud-service/content/release-notes/aem-cloud-changes#replication-agents" text="显著更改 - AEM as a Cloud Service"
>additional-url="https://experienceleague.adobe.com/zh-hans/docs/experience-manager-cloud-service/content/implementing/developing/development-guidelines#no-reverse-replication-agents" text="开发准则"

`REP`  标识已启用的复制代理。报告这些信息是因为在升级到 AEM as a Cloud Service 时，必须解决潜在问题。

子类型用于标识信息的不同类型：

* `forward.replication`：标识启用的转发复制代理。
* `reverse.replication`：标识启用的反向复制代理。
* `standard.replication.agent.modification`：标识启用的标准复制代理，这些代理已经过修改。
* `custom.replication.agent.detection`：标识启用的自定义复制代理。

AEM as a Cloud Service 使用 [Sling Content Distribution](https://sling.apache.org/documentation/bundles/content-distribution.html) 将内容从作者分发到发布环境。此分发在 AEM 运行时之外使用 Adobe Developer 上的 Adobe I/O Runtime 管道服务完成。此工作流在 AEM as a Cloud Service 环境中自动配置。

## 可能产生的后果和风险 {#implications-and-risks}

* 复制的配置已随 AEM as a Cloud Service 更改。需要审查所有当前的复制代理。审查可帮助您了解：
   * 哪些代理可以使用标准功能取代，
   * 哪些配置必须迁移到代码，
   * 以及哪些代理不受支持。
* 升级到 AEM as a Cloud Service 中时，需要审查在自定义代码或工作流中使用的任何复制代理。
* AEM as a Cloud Service 最初不支持反向复制。
* 无需配置单独的 Dispatcher Flush 代理。它会在 AEM as a Cloud Service 环境中自动配置。

## 可采用的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_rep_guidance"
>title="实施指南"
>abstract="最佳实践是审查、重构和优化直接依赖于复制代理的自定义功能，使其与 AEM as a Cloud Service 兼容。联系 Adobe 支持获取帮助或说明。"
>additional-url="https://experienceleague.adobe.com/zh-hans/docs/experience-manager-cloud-service/content/implementing/deploying/overview#replication" text="复制 - AEM as a Cloud Service"
>additional-url="https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支持"

* 请参阅 AEM as a Cloud Service [开发准则](https://experienceleague.adobe.com/zh-hans/docs/experience-manager-cloud-service/content/implementing/developing/development-guidelines#no-reverse-replication-agents)和发行说明中的[复制代理](https://experienceleague.adobe.com/zh-hans/docs/experience-manager-cloud-service/content/release-notes/aem-cloud-changes#replication-agents)。
* 审查、重构和优化直接依赖于复制代理执行业务任务的功能。
* 请参阅 AEM as a Cloud Service 中的部署对[复制](https://experienceleague.adobe.com/zh-hans/docs/experience-manager-cloud-service/content/implementing/deploying/overview#replication)有何影响。
* 请联系 [AEM 支持团队](https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html)进行澄清或解决疑惑。
