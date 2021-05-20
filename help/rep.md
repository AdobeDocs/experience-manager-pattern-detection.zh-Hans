---
title: 代表
description: 模式检测器代码帮助页
exl-id: e788deba-a301-404f-8e90-51f721409e69
source-git-commit: 4ad2fe0fa05b8252112df8a94958e65bb882482d
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 2%

---

# [!DNL REP] {#rep}

复制代理

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_rep_overview"
>title="复制代理"
>abstract="REP标识已启用的复制代理。 之所以会报告这些问题，是因为在升级到AEM as a Cloud Service时，可能会出现应该解决的问题。 AEM as aCloud Service使用Sling Content Distribution将内容从创作环境分发到发布环境。 这是在AEM运行时之外使用Adobe I/O的管道服务完成的。这会在配置的AEM中自动配置为Cloud Service环境。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html#replication-agents" text="显着更改 — AEM作为Cloud Service"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html#no-reverse-replication-agents" text="开发准则"

`REP` 标识已启用的复制代理。之所以会报告这些问题，是因为在升级到AEM as a Cloud Service时，可能会出现应该解决的问题。

AEM as aCloud Service使用[Sling Content Distribution](https://sling.apache.org/documentation/bundles/content-distribution.html)将内容从创作分发到发布环境。 这是在AEM运行时之外使用Adobe I/O的管道服务完成的。这会在配置的AEM中自动配置为Cloud Service环境。

## 可能的影响和风险{#implications-and-risks}

* 复制的配置已通过AEM as a Cloud Service进行更改。 应检查所有当前的复制代理，以查看哪些复制代理被标准功能取代，哪些配置必须移动到代码中，哪些配置不受支持。
* 在升级到AEM as aCloud Service时，应审核自定义代码或工作流中复制代理的任何使用情况。
* AEM as a Cloud Service最初不支持反向复制。
* 无需配置单独的调度程序刷新代理。 这会在AEM中自动配置为Cloud Service环境。

## 可能的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_rep_guidance"
>title="实施指南"
>abstract="最佳做法是直接依赖于复制代理来查看、重构和优化自定义功能，并使其与AEM as a Cloud Service兼容。 联系Adobe支持以获取帮助和说明"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html#replication" text="复制 — AEM as aCloud Service"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud支持"

* 请参阅AEM as a Ar Analytics [开发指南](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html#no-reverse-replication-agents)和[复制代理](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html#replication-agents)的发行说明。
* 直接依赖于复制代理来执行业务任务的功能，审查、重构和优化这些功能。
* 查看[replication](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html#replication)受AEM as a Cloud Service中部署的影响情况。
* 请联系我们的[AEM支持团队](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以获得说明或解决问题。
