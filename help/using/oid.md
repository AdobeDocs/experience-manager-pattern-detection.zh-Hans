---
title: OID
description: Pattern Detector 代码帮助页面。
exl-id: 500e0d32-e75e-4abe-a96b-0692ce40c086
source-git-commit: 84c193b66fbf9c41f546e8575a0aa17e94043b9a
workflow-type: tm+mt
source-wordcount: '413'
ht-degree: 74%

---

# OID {#oid}

Oak 索引定义

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oid_overview"
>title="Oak 索引定义"
>abstract="OID 标识与 Oak 索引定义关联的问题。它定义已经对标准 Oak 索引定义进行的修改。它还标识与 AEM as a Cloud Service 兼容的自定义 Oak 索引定义。每个 OID 发现的消息标识索引并提供额外的信息。"
>additional-url="https://experienceleague.adobe.com/en/docs/zh-hans/experience-manager-cloud-service/content/operations/indexing#how-to-use" text="内容索引准则"

`OID`  标识与Oak索引定义相关的问题。 它定义已经对标准 Oak 索引定义进行的修改。它还标识与 AEM as a Cloud Service 兼容的自定义 Oak 索引定义。每个页面的消息 `OID` 发现结果可标识索引并提供额外的信息。

子类型用于标识信息的不同类型：

* `index.rule.violation`：自定义 Oak 索引与 AEM as a Cloud Service 不兼容
* `standard.index.modification`：对标准 Oak 索引的修改。

## 可能产生的后果和风险 {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oid_guidance"
>title="实施指南"
>abstract="最佳做法是查看所有自定义索引并根据内容索引指南进行重构。利用索引转换器，将现有自定义 Oak 索引定义迁移到与 AEM as a Cloud Service 兼容的自定义 Oak 索引定义"
>additional-url="https://experienceleague.adobe.com/en/docs/zh-hans/experience-manager-cloud-service/content/implementing/developing/aem-project-content-package-structure#oak-indexes" text="打包准则"
>additional-url="https://experienceleague.adobe.com/en/docs/zh-hans/experience-manager-cloud-service/content/migration-journey/refactoring-tools/index-converter#refactoring-tools" text="索引转换器"

* AEM 升级期间，对标准 Oak 索引定义的修改可能会丢失。
* Oak 定义不可变，应该与客户项目代码一起打包，并且只应使用 Cloud Manager 部署。
* 所有Oak索引定义都应遵循AEMas a Cloud Service中Oak索引的命名约定和其他规则。 否则，可能会导致意外行为。

## 可采用的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oid_tools"
>title="工具和资源"
>abstract="审查 WKND 旧版项目，了解如何解决项目中的 OID 违规。此外，查看 GitHub 上的 OID 违规示例，了解如何使用索引转换器工具转换旧版索引并使其与 AEM as a Cloud Service 兼容。"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/tree/code/oid" text="WKND 旧版项目"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/oid" text="OID 违规示例 - GitHub"

* 解决消息中标识的索引规则违规。
* 要部署新的或自定义的Oak索引定义，请按照AEMas a Cloud Service操作 [打包准则](https://experienceleague.adobe.com/en/docs/zh-hans/experience-manager-cloud-service/content/implementing/developing/aem-project-content-package-structure).
* 自定义AEM标准索引和新的自定义Oak索引定义应遵循 [内容索引准则](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/operations/indexing#preparing-the-new-index-definition) 用于AEMas a Cloud Service。
* 审查 [wknd 旧版](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/oid)项目，了解如何更正 [OID 违规](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/oid)，使其与 AEM as a Cloud Service 兼容。
* 请联系 [AEM 支持团队](https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html) 进行澄清或解决疑惑。
* 使用 [索引转换器](https://experienceleague.adobe.com/en/docs/zh-hans/experience-manager-cloud-service/content/migration-journey/refactoring-tools/index-converter#refactoring-tools) 将现有的自定义Oak索引定义迁移到与AEMas a Cloud Service兼容的自定义Oak索引定义。
