---
title: OID
description: 模式检测器代码帮助页
exl-id: 500e0d32-e75e-4abe-a96b-0692ce40c086
source-git-commit: 54b121a6ec29ba6ff6fb33b402f1821c34d0763f
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 0%

---

# OID {#oid}

Oak索引定义

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oid_overview"
>title="Oak索引定义"
>abstract="OID标识了与Oak索引定义相关的问题。 它标识对标准Oak索引定义所做的修改。 它还会识别与AEM作为Cloud Service不兼容的自定义Oak索引定义。 每个OID发现结果的消息将标识索引并提供其他信息。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/indexing.html#how-to-use" text="内容索引准则"

`OID` 识别与Oak索引定义相关的问题。它标识对标准Oak索引定义所做的修改。 它还会识别与AEM作为Cloud Service不兼容的自定义Oak索引定义。 每个`OID`发现结果的消息将标识索引并提供其他信息。

子类型用于标识不同类型的信息：

* `custom.index.violation`:自定义Oak索引与AEM as a A Sa Service不兼容。
* `standard.index.modification`:对标准Oak索引的修改。

## 可能的影响和风险{#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oid_guidance"
>title="实施指南"
>abstract="最佳做法是根据内容索引准则查看所有自定义索引和重组。 利用索引转换器将现有的自定义Oak索引定义作为与自定义Oak索引定义兼容的Cloud Service迁移到AEM"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html#oak-indexes" text="包装准则"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/refactoring-tools/index-converter.html#refactoring-tools" text="索引转换器"

* 在AEM升级过程中，对标准Oak索引定义的修改可能会丢失。
* Oak定义不可更改，应与客户项目代码一起打包，并且只应使用Cloud Manager进行部署。
* 所有Oak索引定义都应遵循命名规范和AEM中Oak索引的其他规则作为Cloud Service。 那些不会导致不希望的行为。

## 可能的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oid_tools"
>title="工具和资源"
>abstract="查看WKND-legacy项目，了解如何在您的项目中解决OID违规问题。 此外，查看Github上的OID违规示例，了解如何使用索引转换器工具转换旧版索引，并使其与AEM作为Cloud Service兼容。"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/tree/code/oid" text="WKND旧版项目"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/oid" text="OID违规示例 — Github"

* 解决消息中标识的索引规则违规问题。
* 按照AEM as a OakCloud Service[打包准则](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html)部署新的或自定义的Oak索引定义。
* 自定义的AEM标准索引和新的自定义Oak索引定义应遵循[内容索引准则](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/indexing.html#preparing-the-new-index-definition)，以便AEM作为Cloud Service。
* 查看[wknd-legacy](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/oid)项目，并了解如何更正[OID违规](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/oid)并使其与作为Cloud Service的AEM兼容。
* 请联系我们的[AEM支持团队](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以获得说明或解决问题。
* 利用[索引转换器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/refactoring-tools/index-converter.html#refactoring-tools)将现有的自定义Oak索引定义作为与Cloud Service兼容的自定义Oak索引定义迁移到AEM。
