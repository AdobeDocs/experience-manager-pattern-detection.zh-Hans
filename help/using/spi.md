---
title: SPI
description: Pattern Detector 代码帮助页面。
source-git-commit: e050b9190f67fd6ccfac31490c4bf2a60d47731f
workflow-type: tm+mt
source-wordcount: '91'
ht-degree: 8%

---

# SPI {#spi}

## 背景 {#background}

SIF标识使用的Search和Promote与AEM 6.5 LTS不兼容。

<!-- Alexandru: drafting for now ## Possible implications and risks {#implications-and-risks} -->

## 可采用的解决方案 {#solutions}

找到适用于不同子类型的可能解决方案，如下所示：

* `searchpromote.bundles.detected` — 将在升级期间卸载这些包
* `earchpromote.packages.detected` — 这些包将在升级期间删除
* `searchpromote.packages.dependency` — 删除您的自定义包可能具有的所有Search and Promote依赖关系
* `searchpromote.usage` — 从自定义代码中删除Search和Promote API
* `searchpromote.users.detected` — 请勿在自定义代码中使用Search and Promote服务用户
* `searchpromote.configs.detected` — 请勿在自定义代码中使用Search和Promote配置属性。