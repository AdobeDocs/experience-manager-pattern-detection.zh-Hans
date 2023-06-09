---
title: DOPI
description: Pattern Detector 代码帮助页面
exl-id: ae4df44d-43ca-438c-8373-11381b916af3
source-git-commit: f1e833bea35ef3b412936d529b14bff6f1cb35c1
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 100%

---

# DOPI {#dopi}

已弃用 Ordered Property 索引

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dopi_overview"
>title="已弃用 Ordered Property 索引"
>abstract="DOPI 代码标识使用了 Ordered Property 索引定义 (primaryType=oak:QueryIndexDefinition AND type=&quot;ordered&quot;)，这已从 6.1 开始弃用，在 6.2 中已移除。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/queries-and-indexing.html?lang=zh-Hans#the-ordered-index" text="排序索引 - 已弃用"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/indexing.html" text="索引 - AEM as a Cloud Service"

`DOPI` 代码标识使用了 Ordered Property 索引定义 (`primaryType=oak:QueryIndexDefinition` AND `type="ordered"`)，这已从 6.1 开始弃用，在 6.2 中已移除。

## 可能的后果和风险 {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dopi_guidance"
>title="实施指南"
>abstract="最佳实践是审查所有已弃用排序索引并将其迁移到支持的 Lucene 索引形式，以避免重大的性能问题或者无法工作的客户请求。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/deploying/practices/best-practices-for-queries-and-indexing.html" text="最佳实践 - 查询和索引"

* 一些查询可能不响应。
* 客户功能可能未正确工作。
* 由于已弃用的索引没有效果，遍历警告甚至是错误，并有显著的性能影响。

## 可采用的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dopi_tools"
>title="工具和资源"
>abstract="审查 WKND 旧版项目，了解如何使 DOPI 违规与 AEM Cloud Service 兼容。此外，查看 Github 上的 DOPI 违规示例，了解如何使用旧版排序索引如何转换为 AEM as a Cloud Service 支持的基于 Lucene 的索引。"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/tree/code/dopi" text="WKND 旧版项目"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/dopi" text="DOPI 违规示例 - Github"

* 修改索引定义以使其成为支持的索引定义，或者替换索引为支持的索引定义。（请参阅 [Oak 查询和索引](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/queries-and-indexing.html)）。
* 审查 [wknd 旧版](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/dopi)项目，了解如何更正 [DOPI 违规](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/dopi)，使其与 AEM as a Cloud Service 兼容。
* 请联系我们的 [AEM 支持团队](https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html)获取说明或解决问题。
