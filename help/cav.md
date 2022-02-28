---
title: CAV
description: Pattern Detector 代码帮助页面
exl-id: b2282da2-a028-4be7-914c-17dcd5d2902a
source-git-commit: 1966a3e83ab6b2247d9f1095c8965eac399e3b6e
workflow-type: ht
source-wordcount: '366'
ht-degree: 100%

---

# CAV {#cav}

内容领域违规

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cav_overview"
>title="内容领域违规"
>abstract="CAV 代码标识这样一种模式，不同内容领域的使用方式违反了内容分类规则。此违规会向您提供叠加的概览，限制在迁移到 AEM as a Cloud Service 后可能需要更改的内容。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/sling-resource-merger.html#platform" text="Sling 资源管理器"

`CAV` 标识这样一种模式，不同内容领域的使用方式违反了内容分类规则。

Sling 请求处理定义如何使用资源的内容（具体而言是其 `sling:resourceType` 属性）确定将用于呈现内容的脚本。有关更多信息，请参阅[定位脚本](https://experienceleague.adobe.com/docs/experience-manager-65/developing/introduction/the-basics.html#locating-the-script)。Sling 还提供了通过“叠加”和“覆盖”来访问及合并资源的技术。这些内容在 [Sling 资源合并器](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/sling-resource-merger.html)和[叠加](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/overlays.html)中介绍。

为了让客户更快速更安全地理解 `/libs` 的哪些领域可以安全使用和叠加，`/libs` 中的内容使用“mixin”属性进行分类：Public、Abstract、Final 和 Internal。每个分类都暗示了有关如何使用、继承或覆盖内容的规则。有关详细说明，请参阅[可持续升级](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/upgrading/sustainable-upgrades.html)。

## 可能的后果和风险 {#implications-and-risks}

* AEM 升级可能导致页面渲染问题或其他意外行为。
* 安全更新不生效。

## 可采用的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cav_guidance"
>title="实施指南"
>abstract="由 CAS 标识的模式，其中存在不同内容领域违规，应进行审查。应避免 Final 和 Internal 内容分类领域。请联系 Adobe 支持部门获取帮助或说明。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/deploying/upgrading/sustainable-upgrades.html" text="可持续升级"
>additional-url="https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支持"

* 尽可能减少内容叠加的使用，仅限那些需要的用例。
* 特别是，避免叠加限制的内容（Final 和 Internal 分类）。
* 在 AEM 升级、ServicePack 或 CumulativeFixPack 安装后，请考虑采用来自 `/libs` 的更改。
* 请联系我们的 [AEM 支持团队](https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html)获取说明或解决问题。
