---
title: PCX
description: 图案检测器代码帮助页
translation-type: tm+mt
source-git-commit: 2391ad7851d4e6634a7bacd684b08db44a9c78e8
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 0%

---


# PCX {#pcx}

页面复杂性

## 背景 {#background}

`PCX` 标识结构中包含大量节点的页面。

子类型用于标识不同类型的信息：

* `page.complexity.medium`:页面包含的节点数量适中，可能会影响渲染性能。
* `page.complexity.high`:页面包含很多可能会影响渲染性能的节点。

## 可能的影响和风险{#implications-and-risks}

* 页面中的大量节点可能会影响其呈现性能。

## 可能的解决方案{#solutions}

* 采取措施减少页面内的节点总数，包括：
   * 确认没有不必要的容器。
   * 测试是否可以用更少的容器实现相同的布局。
   * 简化页面内容。
   * 降低节点结构的深度。
   * 重新构建任何包含的体验片段，以实现简单性。
* 请联系我们的[AEM支持团队](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以获得说明或解决问题。
