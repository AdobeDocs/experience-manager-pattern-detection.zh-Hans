---
title: CIF
description: Pattern Detector 代码帮助页面
exl-id: cf9d5f62-c9dd-4f56-982c-1b5b19c81506
source-git-commit: f1e833bea35ef3b412936d529b14bff6f1cb35c1
workflow-type: ht
source-wordcount: '338'
ht-degree: 100%

---

# CIF {#cif}

Commerce Integration Framework 经典版

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cif_overview"
>title="Commerce Integration Framework 经典版"
>abstract="CIF 标识使用的 Commerce Integration Framework 经典版本与 AEM as a Cloud Service 不兼容。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content-and-commerce/introduction.html" text=" Content and Commerce"

`CIF`CIF 标识使用的 Commerce Integration Framework 经典版本与 AEM as a Cloud Service 不兼容。每个 `CIF` 发现的消息将标识使用情况并提供额外的信息。

子类型用于标识信息的不同类型：

* `commerce.integration.framework.detected`：Commerce Integration Framework 的经典版本与 AEM as a Cloud Service 不兼容。


## 可能的后果和风险 {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cif_guidance"
>title="实施指南"
>abstract="最佳实践是审查使用的所有 Commerce Integration Framework 经典版本。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content-and-commerce/changes.html" text="对 CIF 的显著更改"

* AEM as a Cloud Service 上不再支持 Commerce Integration Framework 的经典版本。它会阻止升级到 AEM as a Cloud Service。

## 可采用的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cif_tools"
>title="工具和资源"
>abstract="本指南帮助确定您需要为 Experience Manager Cloud Service 迁移而更新的领域。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content-and-commerce/migration.html" text="CIF 迁移指南"

* 对于 Experience Manager as a Cloud Service，CIF 加载项是 Adobe Commerce 和第三方 Commerce 唯一支持的 Commerce 集成解决方案。CIF 加载项自动为 Experience Manager as a Cloud Service 上的客户部署，无需手动部署。请参阅 [AEM Commerce as a Cloud Service 快速入门](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content-and-commerce/storefront/getting-started.html)。
* 为支持部署 CIF 的项目，Adobe 提供了 [AEM CIF 核心组件](https://github.com/adobe/aem-core-cif-components)。
* CIF 加载项可用于 AEM 6.5 以及通过[软件分发门户](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html)使用。它是兼容的，提供了与 Experience Manager as a Cloud Service 的 CIF 加载项相同的功能，无需调整。
* Classic CIF 及其依赖项不再可用。对于代码，如果依赖于使用 com.adobe.cq.commerce.api Java API 的此 CIF 版本，则必须根据 CIF 加载项及其准则进行调整。
