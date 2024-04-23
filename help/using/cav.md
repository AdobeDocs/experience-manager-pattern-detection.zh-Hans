---
title: CAV
description: Pattern Detector代码帮助页面。
exl-id: b2282da2-a028-4be7-914c-17dcd5d2902a
source-git-commit: 616fa84f6237893243cffc8af28c7cbe76bf32d7
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 45%

---

# CAV {#cav}

内容领域违规

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cav_overview"
>title="内容领域违规"
>abstract="CAV 代码标识这样一种模式，不同内容领域的使用方式违反了内容分类规则。此违规会向您提供叠加的概述，限制在将其移至AEMas a Cloud Service后可能需要更改的内容。"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/developing/platform/sling-resource-merger#platform" text="Sling 资源管理器"

CAV标识这样一种模式，不同内容领域的使用方式违反了内容分类规则。

Sling请求处理定义资源的内容、其 `sling:resourceType` 属性用于确定用于呈现内容的脚本。 有关更多信息，请参阅[定位脚本](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/developing/introduction/the-basics#locating-the-script)。Sling 还提供了通过“叠加”和“覆盖”来访问及合并资源的技术。这些内容在 [Sling 资源合并器](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/developing/platform/sling-resource-merger)和[叠加](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/developing/platform/overlays)中介绍。

使客户更安全、更轻松地了解 `/libs` 可以安全使用并覆盖中的内容 `/libs` 已使用“mixin”属性进行分类：Public、Abstract、Final和Internal。 每个分类都暗示了有关如何使用、继承或覆盖内容的规则。有关详细说明，请参阅[可持续升级](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/deploying/upgrading/sustainable-upgrades)。

## 可能的后果和风险 {#implications-and-risks}

* AEM 升级可能导致页面渲染问题或其他意外行为。
* 安全更新不生效。

## 可采用的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cav_guidance"
>title="实施指南"
>abstract="由CAS标识的模式，其中存在不同的内容领域违规，应进行审查。 应避免Final和Internal内容分类领域。 请联系Adobe支持部门以获取帮助或说明。"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/deploying/upgrading/sustainable-upgrades" text="可持续升级"
>additional-url="https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支持"

* 尽可能减少内容叠加的使用，仅限那些需要的用例。
* 特别是，避免叠加限制的内容（Final 和 Internal 分类）。
* 考虑调整来自的更改 `/libs` 安装AEM升级、Service Pack或累积修订包后。
* 联系 [AEM支持团队](https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html) 以澄清或解决问题。
