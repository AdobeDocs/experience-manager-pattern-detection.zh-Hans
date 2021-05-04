---
title: 多皮
description: 图案检测器代码帮助页
exl-id: ae4df44d-43ca-438c-8373-11381b916af3
translation-type: tm+mt
source-git-commit: 54b121a6ec29ba6ff6fb33b402f1821c34d0763f
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 0%

---

# DOPI {#dopi}

已弃用的有序属性索引

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dopi_overview"
>title="已弃用的有序属性索引"
>abstract="DOPI代码标识了有序属性索引定义(primaryType=oak:QueryIndexDefinition AND type=&quot;ordered&quot;)的使用，这些定义自6.1起已弃用，在6.2中已删除。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/queries-and-indexing.html?lang=en#the-ordered-index" text="有序索引 — 已弃用"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/indexing.html" text="索引 — AEM作为Cloud Service"

`DOPI` 标识对有序属性索引定`primaryType=oak:QueryIndexDefinition` 义( `type="ordered"`AND)的使用，自6.1起已弃用，在6.2中已删除。

## 可能的影响和风险{#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dopi_guidance"
>title="实施指南"
>abstract="最佳实践是检查所有已弃用的有序索引，并将它们移动到支持的lucene索引形式，以避免出现严重的性能问题或客户要求不正常。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/deploying/practices/best-practices-for-queries-and-indexing.html" text="最佳实践 — 查询和索引"

* 一些查询可能不会回应。
* 客户功能可能工作不正确。
* 遍历警告、甚至错误，以及严重的性能惩罚，因为已弃用的索引没有任何效果。

## 可能的解决方案{#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dopi_tools"
>title="工具和资源"
>abstract="查看WKND-legacy项目，了解如何使DOPI违规与AEMCloud Service兼容。 另外，查看Github上的DOPI违规示例，了解如何将旧版有序索引转换为基于Lucene的索引，这些索引在AEM中作为Cloud Service受支持。"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/tree/code/dopi" text="WKND-Legacy Project"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/dopi" text="DOPI违规示例 — Github"

* 修改索引定义，使其成为支持的索引定义或将索引替换为支持的索引定义。 (请参阅[Oak查询和索引](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/queries-and-indexing.html))。
* 查看[wknd-legacy](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/dopi)项目并了解如何更正[DOPI违规](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/dopi)并使其与作为Cloud Service的AEM兼容。
* 请联系我们的[AEM支持团队](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以获得说明或解决问题。
