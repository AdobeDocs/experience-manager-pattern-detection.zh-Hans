---
title: PCX
description: Pattern Detector 代码帮助页面
exl-id: 7e3c1142-c349-4bce-b8de-8e91528f80a0
source-git-commit: f1e833bea35ef3b412936d529b14bff6f1cb35c1
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 100%

---

# PCX {#pcx}

页面复杂性

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_pcx_overview"
>title="页面复杂性"
>abstract="PCX 标识其结构中包含大量节点的页面。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html" text="显著更改 - AEM as a Cloud Service"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html?lang=zh-Hans" text="AEM as a Cloud Service - 发行说明"

`PCX` 标识其结构中包含大量节点的页面。

子类型用于标识信息的不同类型：

* `page.complexity.medium`：页面包含略高数量的节点，可能会影响渲染性能。
* `page.complexity.high`：页面包含极高数量的节点，很可能会影响渲染性能。

## 可能的后果和风险 {#implications-and-risks}

* 页面中的大量节点会影响其渲染性能。

## 可采用的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_pcx_guidance"
>title="实施指南"
>abstract="最佳实践是审查内容结构，减少页面复杂性，这随之有助于改善页面渲染性能。请联系 Adobe 支持部门获取帮助或说明"
>additional-url="https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支持"

* 采取步骤来减少页面中的节点总数，包括：
   * 验证没有不必要的容器。
   * 测试是否可以使用较少的容器实现相同的版面。
   * 简化页面内容。
   * 减少节点结构的深度。
   * 重构包含的任何体验片段以进行简化。
* 请联系我们的 [AEM 支持团队](https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html)获取说明或解决问题。
