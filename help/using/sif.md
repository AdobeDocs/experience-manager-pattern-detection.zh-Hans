---
title: SIF
description: Pattern Detector 代码帮助页面。
source-git-commit: 8dd9a42a3bba63d62fa2469b0f78ca15a608b4f9
workflow-type: tm+mt
source-wordcount: '107'
ht-degree: 7%

---

# SIF {#sif}

## 背景 {#background}

SIF标识与AEM 6.5 LTS不兼容的社交使用。

<!-- Alexandru: drafting for now ## Possible implications and risks {#implications-and-risks} -->

## 可采用的解决方案 {#solutions}

找到适用于不同子类型的可能解决方案，如下所示：

* `social.bundles.detected` — 将在升级期间卸载这些包
* `social.packages.detected` — 将在升级期间删除这些包
* `social.packages.dependency` — 请从自定义包中删除社交包的依赖项
* `social.nodes.detected` — 更新自定义代码以不创建社交节点
* `social.configs.detected` — 请勿在自定义代码中使用社交配置属性
* `social.users.detected` — 请勿在自定义代码中使用社交用户
* `social.overlays.detected` — 删除社交叠加使用情况
* `social.paths.detected` — 在确保AEM中未使用这些路径后，删除社交路径
* `social.resource.type.detected` — 删除社交资源类型使用情况
* `social.usage` — 从自定义代码中删除社交API。