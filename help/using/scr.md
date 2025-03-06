---
title: SCR
description: Pattern Detector 代码帮助页面。
source-git-commit: 8dd9a42a3bba63d62fa2469b0f78ca15a608b4f9
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 7%

---

# SCR {#scr}

## 背景 {#background}

SIF标识使用的AEM Screens与AEM 6.5 LTS不兼容。

<!-- Alexandru: drafting for now ## Possible implications and risks {#implications-and-risks} -->

## 可采用的解决方案 {#solutions}

找到适用于不同子类型的可能解决方案，如下所示：

* `screens.bundles.detected` — 将在升级期间卸载这些包。
* `screens.packages.detected` — 这些包将在升级期间删除。
* `screens.packages.dependency` — 从自定义包中删除对Screens的任何依赖关系。
* `screens.configs.detected` — 确保您的自定义代码中未使用任何Screens配置属性。
* `screens.users.detected` — 确保未在自定义代码中使用Screens服务用户。
* `screens.paths.detected` — 在确保Screens路径未在AEM中使用之后，请删除这些路径。
* `screens.resource.type.detected` — 删除Screens资源类型用法。
* `screens.usage` — 从自定义代码中删除Screens API。