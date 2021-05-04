---
title: CAV
description: 图案检测器代码帮助页
exl-id: b2282da2-a028-4be7-914c-17dcd5d2902a
translation-type: tm+mt
source-git-commit: 1966a3e83ab6b2247d9f1095c8965eac399e3b6e
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 0%

---

# CAV {#cav}

内容区域冲突

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cav_overview"
>title="内容区域冲突"
>abstract="CAV代码标识以违反内容分类规则的方式使用不同内容区域的模式。 此违规将概述叠加和受限内容，当我们作为Cloud Service移动到AEM时，这些内容可能需要更改。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/sling-resource-merger.html#platform" text="Sling Resource Mearge"

`CAV` 标识以违反内容分类规则的方式使用不同内容区域的模式。

Sling请求处理定义如何使用资源的内容（尤其是其`sling:resourceType`属性）来确定用于呈现内容的脚本。 有关详细信息，请参阅[查找脚本](https://experienceleague.adobe.com/docs/experience-manager-65/developing/introduction/the-basics.html#locating-the-script)。 Sling还提供通过“叠加”和“覆盖”访问和合并资源的技术。 这些描述是[Sling资源合并](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/sling-resource-merger.html)和[Overlays](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/overlays.html)中的一部分。

为了使客户更安全、更轻松地了解`/libs`的哪些区域是安全的，并覆盖`/libs`中的内容已使用“mixin”属性分类：公共、抽象、最终和内部。 每个分类都暗含有关内容可能是用户、继承还是覆盖方式的规则。 有关详细说明，请参阅[可持续升级](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/upgrading/sustainable-upgrades.html)。

## 可能的影响和风险{#implications-and-risks}

* AEM升级可能导致页面渲染问题和其他不需要的行为。
* 安全更新无效。

## 可能的解决方案{#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cav_guidance"
>title="实施指南"
>abstract="应审查与CAS确定的存在不同内容区域违规的模式。 应避免最终内容和内部内容分类区域。 联系Adobe支持以获得帮助和说明。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/deploying/upgrading/sustainable-upgrades.html" text="可持续升级"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud支持"

* 在需要内容叠加的情况下将内容叠加的使用降至最低。
* 尤其要避免覆盖受限内容（最终和内部分类）。
* 请考虑在AEM升级、ServicePack或CumulativeFixPack安装后调整来自`/libs`的更改。
* 请联系我们的[AEM支持团队](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以获得说明或解决问题。
