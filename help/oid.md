---
title: OID
description: 图案检测器代码帮助页
translation-type: tm+mt
source-git-commit: 5a83dd8d08da974a5d775032b8dbea2593be9d15
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 0%

---


# OID {#oid}

Oak索引定义

## 背景 {#background}

`OID` 发现与Oak索引定义相关的问题。它标识了对标准Oak索引定义所做的修改。 它还将与AEM不兼容的自定义Oak索引定义标识为Cloud Service。 每个`OID`查找结果的消息将标识索引并提供其他信息。

子类型用于标识不同类型的信息：

* `custom.index.violation`:自定义Oak索引与AEM作为Cloud Service不兼容。
* `standard.index.modification`:对标准Oak指数的修改。

## 可能的影响和风险{#implications-and-risks}

* 在AEM升级过程中，对标准Oak索引定义的修改可能会丢失。
* Oak定义是不可变的，应与客户项目代码一起打包，并且仅应使用Cloud Manager进行部署。
* 所有Oak索引定义都应遵循命名惯例和AEM中Oak索引的其他规则作为Cloud Service。 那些不会导致意外行为的行为。

## 可能的解决方案{#solutions}

* 解决消息中标识的索引规则违规。
* 按照AEM的Cloud Service[打包指南](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html)部署新的或自定义的Oak索引定义。
* 自定义AEM标准索引和新的自定义Oak索引定义应遵循AEM的[内容索引准则](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/indexing.html#preparing-the-new-index-definition)作为Cloud Service。
* 查看[wknd-legacy](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/oid)项目并了解如何更正[OID违规](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/oid)并使其与作为Cloud Service的AEM兼容。
* 请联系我们的[AEM支持团队](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以获得说明或解决问题。
* 利用[索引转换器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/refactoring-tools/index-converter.html#refactoring-tools)将现有的自定义Oak索引定义迁移到AEM作为与Cloud Service兼容的自定义Oak索引定义。