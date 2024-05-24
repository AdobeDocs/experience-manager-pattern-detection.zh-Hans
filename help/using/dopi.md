---
title: DOPI
description: Pattern Detector 代码帮助页面。
exl-id: ae4df44d-43ca-438c-8373-11381b916af3
source-git-commit: dd60fb9fb21d534e7b6f264826d3cc1477def421
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 91%

---

# DOPI {#dopi}

已弃用 Ordered Property 索引

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dopi_overview"
>title="已弃用 Ordered Property 索引"
>abstract="DOPI 代码标识有序属性索引定义（`primaryType=oak:QueryIndexDefinition` AND `type="ordered"`）的使用。该定义在 AEM 6.1 中已被弃用，并在 AEM 6.2 中被删除。"
>additional-url="https://experienceleague.adobe.com/zh-hans/docs/experience-manager-65/content/implementing/deploying/deploying/queries-and-indexing#the-ordered-index" text="排序索引 - 已弃用"
>additional-url="https://experienceleague.adobe.com/zh-hans/docs/experience-manager-cloud-service/content/operations/indexing" text="索引 - AEM as a Cloud Service"

`DOPI`  标识使用了Ordered Property索引定义(`primaryType=oak:QueryIndexDefinition` 和 `type="ordered"`)。 这些定义在AEM 6.1中已弃用，在AEM 6.2中已移除。

## 可能产生的后果和风险 {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dopi_guidance"
>title="实施指南"
>abstract="最佳实践是审查所有已弃用排序索引并将其迁移到支持的 Lucene 索引形式，以避免重大的性能问题或者无法工作的客户请求。"
>additional-url="https://experienceleague.adobe.com/zh-hans/docs/experience-manager-65/content/implementing/deploying/practices/best-practices-for-queries-and-indexing" text="最佳实践 - 查询和索引"

* 一些查询可能不响应。
* 客户功能可能未正确工作。
* 由于已弃用的索引没有效果，遍历警告甚至是错误，并有显著的性能影响。

## 可采用的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dopi_tools"
>title="工具和资源"
>abstract="审查 WKND 旧版项目，了解如何使 DOPI 违规与 AEM Cloud Service 兼容。另外，请查看 GitHub 上的 DOPI 违规示例。它可以帮助您了解如何将传统的有序索引转换为 AEM as a Cloud Service 支持的基于 Lucene 的索引。"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/tree/code/dopi" text="WKND 旧版项目"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/dopi" text="DOPI 违规示例 - GitHub"

* 编辑索引定义以使其成为支持的索引定义，或者用支持的索引定义替换索引。（请参阅 [Oak 查询和索引](https://experienceleague.adobe.com/zh-hans/docs/experience-manager-65/content/implementing/deploying/deploying/queries-and-indexing)）。
* 审查 [wknd 旧版](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/dopi)项目，了解如何更正 [DOPI 违规](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/dopi)，使其与 AEM as a Cloud Service 兼容。
* 请联系 [AEM 支持团队](https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html) 进行澄清或解决疑惑。
