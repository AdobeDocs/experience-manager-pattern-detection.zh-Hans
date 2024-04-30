---
title: CIF
description: Pattern Detector 代码帮助页面。
exl-id: cf9d5f62-c9dd-4f56-982c-1b5b19c81506
source-git-commit: 84c193b66fbf9c41f546e8575a0aa17e94043b9a
workflow-type: tm+mt
source-wordcount: '307'
ht-degree: 66%

---

# CIF {#cif}

Commerce Integration Framework 经典版

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cif_overview"
>title="Commerce Integration Framework 经典版"
>abstract="CIF 标识了与 AEM as a Cloud Service 不兼容的 Commerce Integration Framework 经典版本用法。"
>additional-url="https://experienceleague.adobe.com/zh-hans/docs/experience-manager-cloud-service/content/content-and-commerce/introduction" text=" Content and Commerce"

`CIF`  标识使用的Commerce integration framework的经典版本与AEMas a Cloud Service不兼容。 每个页面的消息 `CIF` 发现结果可标识使用情况并提供额外的信息。

子类型用于标识信息的不同类型：

* `commerce.integration.framework.detected`：Commerce Integration Framework 的经典版本与 AEM as a Cloud Service 不兼容。


## 可能产生的后果和风险 {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cif_guidance"
>title="实施指南"
>abstract="最佳实践是审查使用的所有 Commerce Integration Framework 经典版本。"
>additional-url="https://experienceleague.adobe.com/zh-hans/docs/experience-manager-cloud-service/content/content-and-commerce/changes" text="对 CIF 的显著更改"

* AEM as a Cloud Service 上不再支持 Commerce Integration Framework 的经典版本。它会阻止升级到 AEM as a Cloud Service。

## 可采用的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cif_tools"
>title="工具和资源"
>abstract="本指南帮助确定您必须为 Experience Manager Cloud Service 迁移而更新的领域。"
>additional-url="https://experienceleague.adobe.com/zh-hans/docs/experience-manager-cloud-service/content/content-and-commerce/migration" text="CIF 迁移指南"

* 对于Experience Manageras a Cloud Service，CIF加载项是唯一受Adobe Commerce和第三方商务解决方案支持的商务集成解决方案。 CIF 加载项自动为 Experience Manager as a Cloud Service 上的客户部署，无需手动部署。请参阅 [AEM Commerce as a Cloud Service 快速入门](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/content-and-commerce/storefront/getting-started)。
* 为了支持部署CIF的项目，Adobe提供了 [AEM CIF核心组件](https://github.com/adobe/aem-core-cif-components).
* CIF加载项可用于AEM 6.5，方式为 [软件分发门户](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html). 它是兼容的，提供了与 Experience Manager as a Cloud Service 的 CIF 加载项相同的功能，无需调整。
* Classic CIF 及其依赖项不再可用。对于代码，如果依赖于使用com.adobe.cq.commerce.api Java™ API的此CIF版本，则必须根据CIF加载项及其原理进行调整。
