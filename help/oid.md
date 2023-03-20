---
title: OID
description: Pattern Detector 代码帮助页面
exl-id: 500e0d32-e75e-4abe-a96b-0692ce40c086
source-git-commit: 71fd8c278f5fa2c44e489316be36d7d0376fe695
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 100%

---

# OID {#oid}

Oak 索引定义

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oid_overview"
>title="Oak 索引定义"
>abstract="OID 标识与 Oak 索引定义关联的问题。它定义已经对标准 Oak 索引定义进行的修改。它还标识与 AEM as a Cloud Service 兼容的自定义 Oak 索引定义。每个 OID 发现的消息将标识索引并提供额外的信息。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/indexing.html#how-to-use" text="内容索引准则"

`OID` 标识与 Oak 索引定义关联的问题。它定义已经对标准 Oak 索引定义进行的修改。它还标识与 AEM as a Cloud Service 兼容的自定义 Oak 索引定义。每个 `OID` 发现的消息将标识索引并提供额外的信息。

子类型用于标识信息的不同类型：

* `index.rule.violation`：自定义 Oak 索引与 AEM as a Cloud Service 不兼容。
* `standard.index.modification`：对标准 Oak 索引的修改。

## 可能的后果和风险 {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oid_guidance"
>title="实施指南"
>abstract="最佳实践是查看所有自定义索引并根据内容索引准则重构。利用索引转换器，将现有自定义 Oak 索引定义迁移到与 AEM as a Cloud Service 兼容的自定义 Oak 索引定义"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html#oak-indexes" text="打包准则"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/refactoring-tools/index-converter.html#refactoring-tools" text="索引转换器"

* AEM 升级期间，对标准 Oak 索引定义的修改可能会丢失。
* Oak 定义不可变，应该与客户项目代码一起打包，并且只应使用 Cloud Manager 部署。
* 所有 Oak 索引定义应该遵循 AEM as Cloud Service 中 Oak 索引的命名约定和其他规则。未遵循这些准则可能会导致意外的行为。

## 可采用的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oid_tools"
>title="工具和资源"
>abstract="审查 WKND 旧版项目，了解如何解决项目中的 OID 违规。此外，查看 Github 上的 OID 违规示例，了解如何使用索引转换器工具转换旧版索引并使其与 AEM as a Cloud Service 兼容。"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/tree/code/oid" text="WKND 旧版项目"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/oid" text="OID 违规示例 - Github"

* 解决消息中标识的索引规则违规。
* 遵循 AEM as a Cloud Service [打包准则](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html)以部署新的或自定义的 Oak 索引定义。
* 自定义 AEM 标准索引和新的自定义 Oak 索引定义应该遵循 AEM as Cloud Service 的[内容索引指南](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/indexing.html#preparing-the-new-index-definition)。
* 审查 [wknd 旧版](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/oid)项目，了解如何更正 [OID 违规](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/oid)，使其与 AEM as a Cloud Service 兼容。
* 请联系我们的 [AEM 支持团队](https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html)获取说明或解决问题。
* 利用[索引转换器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/refactoring-tools/index-converter.html#refactoring-tools)，将现有自定义 Oak 索引定义迁移到与 AEM as a Cloud Service 兼容的自定义 Oak 索引定义。
