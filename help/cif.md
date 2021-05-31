---
title: CIF
description: 模式检测器代码帮助页
exl-id: 500e0d32-e75e-4abe-a96b-0692ce40c086
source-git-commit: 84aea5b24e51ce5672826bad4ec126074bf24a09
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 0%

---

# CIF {#cif}

Commerce Integration Framework Classic

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cif_overview"
>title="Commerce Integration Framework Classic"
>abstract="CIF标识与AEM作为Cloud Service不兼容的商务集成框架使用的经典版本。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content-and-commerce/introduction.html" text=" 内容和商务"

`CIF` CIF标识与AEM作为Cloud Service不兼容的商务集成框架使用的经典版本。每个`CIF`发现结果的消息将标识使用情况并提供其他信息。

子类型用于标识不同类型的信息：

* `commerce.integration.framework.detected`:经典版本的商务集成框架与AEM as a A Sa Commerce不兼容。


## 可能的影响和风险{#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cif_guidance"
>title="实施指南"
>abstract="最佳实践是查看商务集成框架使用的所有经典版本。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content-and-commerce/changes.html" text="对CIF的显着更改"

* AEM as a Cloud Service不再支持商务集成框架的经典版本。 它将阻止升级到AEM as aCloud Service。

## 可能的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cif_tools"
>title="工具和资源"
>abstract="本指南可帮助确定您需要更新哪些区域才能进行Experience Manager Cloud Service迁移。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content-and-commerce/migration.html" text="CIF迁移指南"

* 对于Experience Manager作为Cloud Service,CIF加载项是Adobe商务和第三方商务解决方案唯一支持的商务集成解决方案。 CIF附加组件是作为Cloud Service在Experience Manager时自动为客户部署的，无需手动部署。 请参阅[AEM Commerce as a Cloud Service入门](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content-and-commerce/storefront/getting-started.html)。
* 要支持部署CIFAdobe的项目，请提供[AEM CIF核心组件](https://github.com/adobe/aem-core-cif-components)。
* AEM 6.5也可通过[软件分发门户](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html)获取CIF附加组件。 它兼容，并且提供与Experience Manager的CIF加载项相同的功能 — 无需任何调整。
* 经典CIF及其依赖项不再可用。 必须根据CIF附加组件及其原则调整使用com.adobe.cq.commerce.api Java API依赖此CIF版本的代码。
