---
title: AC
description: Pattern Detector 代码帮助页面。
source-git-commit: 8dd9a42a3bba63d62fa2469b0f78ca15a608b4f9
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 7%

---

# AC {#ac}

## 背景 {#background}

AC标识使用的Assets捆绑包与AEM 6.5 LTS不兼容

<!-- Alexandru: drafting for now ## Possible implications and risks {#implications-and-risks} -->

## 可采用的解决方案 {#solutions}

找到适用于不同子类型的可能解决方案，如下所示：

* `asset.bundles.detected` — 此包将在升级期间卸载。
* `asset.usage` — 从自定义代码中删除任何资产评级和资产目录组件依赖项。 在适用的情况下，更改代码以使用新的API `List<Scene7ConfigSetting>` `com.day.cq.dam.scene7.api.model.Scene7ViewerConfig#getSettingsList()`。
* `asset.overlays.detected` — 需要删除在Assets评分和目录组件上创建的叠加。
* `asset.resource.type.detected` — 在您的自定义代码中删除对Assets评级组件resourcetype的任何使用。
* `asset.paths.detected` — 移动这些路径下的任何客户内容，并在确保这些路径未在AEM中使用后将其删除。