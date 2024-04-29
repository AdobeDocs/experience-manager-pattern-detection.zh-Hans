---
title: CAV
description: Pattern Detector 代码帮助页面。
exl-id: b2282da2-a028-4be7-914c-17dcd5d2902a
source-git-commit: 84c193b66fbf9c41f546e8575a0aa17e94043b9a
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 93%

---

# CAV {#cav}

内容领域违规

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cav_overview"
>title="内容领域违规"
>abstract="CAV 代码标识这样一种模式，不同内容领域的使用方式违反了内容分类规则。此违规会向您提供叠加的概述，限制迁移到 AEM as a Cloud Service 后可能需要更改的内容。"
>additional-url="https://experienceleague.adobe.com/zh-hans/docs/experience-manager-65/content/implementing/developing/platform/sling-resource-merger#platform" text="Sling 资源管理器"

`CAV` 标识这样一种模式，不同内容领域的使用方式违反了内容分类规则。

Sling 请求处理定义如何使用资源的内容（特别是其 `sling:resourceType` 属性），用于确定将用于渲染内容的脚本。有关更多信息，请参阅[定位脚本](https://experienceleague.adobe.com/zh-hans/docs/experience-manager-65/content/implementing/developing/introduction/the-basics#locating-the-script)。Sling 还提供了通过“叠加”和“覆盖”来访问及合并资源的技术。这些内容在 [Sling 资源合并器](https://experienceleague.adobe.com/zh-hans/docs/experience-manager-65/content/implementing/developing/platform/sling-resource-merger)和[叠加](https://experienceleague.adobe.com/zh-hans/docs/experience-manager-65/content/implementing/developing/platform/overlays)中介绍。

为了让客户`/libs`更安全、更轻松地了解哪些区域可以安全使用和叠加内容，我们`/libs`使用 &quot;混合 &quot;属性对这些区域进行了分类：公共、抽象、最终和内部。每个分类都暗示了有关如何使用、继承或覆盖内容的规则。有关详细说明，请参阅[可持续升级](https://experienceleague.adobe.com/zh-hans/docs/experience-manager-65/content/implementing/deploying/upgrading/sustainable-upgrades)。

## 可能产生的后果和风险 {#implications-and-risks}

* AEM 升级可能导致页面渲染问题或其他意外行为。
* 安全更新不生效。

## 可采用的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cav_guidance"
>title="实施指南"
>abstract="应审查 CAS 标识的在不同内容领域存在违规行为的模式。应避开 Final 和 Internal 内容分类区域。联系 Adobe 支持获取帮助或说明。"
>additional-url="https://experienceleague.adobe.com/zh-hans/docs/experience-manager-65/content/implementing/deploying/upgrading/sustainable-upgrades" text="可持续升级"
>additional-url="https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支持"

* 尽可能减少内容叠加的使用，仅限那些需要的用例。
* 特别是，避免叠加限制的内容（Final 和 Internal 分类）。
* 在升级 AEM 、Service Pack 或安装 Cumulative Fix Pack 后，请考虑采用来自 `/libs` 的更改。
* 请联系 [AEM 支持团队](https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html) 进行澄清或解决疑惑。
