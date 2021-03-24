---
title: 多皮
description: 图案检测器代码帮助页
translation-type: tm+mt
source-git-commit: ae3e162da40441fba39e6e9d283c495d15f40ba1
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 0%

---


# DOPI {#dopi}

已弃用的有序属性索引

## 背景 {#background}

`DOPI` 标识对有序属性索引定`primaryType=oak:QueryIndexDefinition` 义( `type="ordered"`AND)的使用，自6.1起已弃用，在6.2中已删除。

## 可能的影响和风险{#implications-and-risks}

* 一些查询可能不会回应。
* 客户功能可能工作不正确。
* 遍历警告、甚至错误，以及严重的性能惩罚，因为已弃用的索引没有任何效果。

## 可能的解决方案{#solutions}

* 修改索引定义，使其成为支持的索引定义或将索引替换为支持的索引定义。 (请参阅[Oak查询和索引](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/queries-and-indexing.html))。
* 查看[wknd-legacy](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/dopi)项目并了解如何更正[DOPI违规](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/dopi)并使其与作为Cloud Service的AEM兼容。
* 请联系我们的[AEM支持团队](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以获得说明或解决问题。
