---
title: WRF
description: Pattern Detector 代码帮助页面。
source-git-commit: 8dd9a42a3bba63d62fa2469b0f78ca15a608b4f9
workflow-type: tm+mt
source-wordcount: '90'
ht-degree: 8%

---

# WRF {#wrf}

## 背景 {#background}

WRF标识使用的We-Retail与AEM 6.5 LTS不兼容。

<!-- Alexandru: drafting for now ## Possible implications and risks {#implications-and-risks} -->

## 可采用的解决方案 {#solutions}

找到适用于不同子类型的可能解决方案，如下所示：

* `weretail.bundles.detected` — 将在升级期间卸载这些包
* `weretail.packages.detected` — 将在升级期间删除这些包
* `weretail.configs.detected` — 请勿在您的自定义代码中使用We.Retail配置属性
* `weretail.packages.dependency` — 删除We.Retail上任何自定义包的依赖项
* `weretail.paths.detected` — 在确保您未使用Social之后，可以删除这些We.Retail路径
* `weretail.resource.type.detected` — 删除We.Retail资源类型使用情况
* `weretail.usage` — 从自定义代码中删除We.Retail API。