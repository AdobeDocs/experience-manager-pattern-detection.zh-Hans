---
title: PCX
description: 模式检测器代码帮助页
exl-id: 7e3c1142-c349-4bce-b8de-8e91528f80a0
source-git-commit: 4ad2fe0fa05b8252112df8a94958e65bb882482d
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 3%

---

# PCX {#pcx}

页面复杂性

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_pcx_overview"
>title="页面复杂性"
>abstract="PCX标识结构中包含大量节点的页面。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html" text="显着更改 — AEM作为Cloud Service"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html?lang=zh-Hans" text="AEM as aCloud Service — 发行说明"

`PCX` 标识结构中包含大量节点的页面。

子类型用于标识不同类型的信息：

* `page.complexity.medium`:页面包含的节点数量适中，可能会影响渲染性能。
* `page.complexity.high`:页面包含的节点数量非常多，可能会影响渲染性能。

## 可能的影响和风险{#implications-and-risks}

* 页面中的大量节点可能会影响其渲染性能。

## 可能的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_pcx_guidance"
>title="实施指南"
>abstract="最佳做法是查看内容结构以降低页面复杂性，这反过来有助于提高页面渲染性能。 联系Adobe支持以获取帮助和说明"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud支持"

* 采取措施减少页面中的节点总数，包括：
   * 确认没有不必要的容器。
   * 测试是否可以使用较少的容器实现相同的布局。
   * 简化页面内容。
   * 减小节点结构的深度。
   * 为简单起见，请重新构建任何包含的体验片段。
* 请联系我们的[AEM支持团队](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以获得说明或解决问题。
