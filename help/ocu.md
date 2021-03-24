---
title: OCU
description: 图案检测器代码帮助页
translation-type: tm+mt
source-git-commit: 4f94d4a1e0b8eb7bedbedba2c8a683f34655b527
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 0%

---


# OCU {#ocu}

代码使用过时

## 背景 {#background}

`OCU` 标识某些JCR节点(如Sling或AEM组件或API OSGi导出)以不兼容方式更改或删除的情况。在升级前，客户可能不知道此更改。 它们可能已升级到不兼容版本，或者根本不可用。

由于默认情况下未安装旧版本，因此客户应用程序可能无法正常工作。

## 可能的影响和风险{#implications-and-risks}

* 依赖于使用已弃用的组件或API的任何组件的功能可能会中断，并且在升级后可能无法正确解析。
* 客户应用程序的某些功能或某些AEM功能可能无法正常工作，或在升级后可能不处于活动状态。

## 可能的解决方案{#solutions}

* 短期：安装兼容性包可能会有所帮助。
* 长期：调整客户代码以使用最新版AEM组件或API。
* 请联系我们的[AEM支持团队](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以获得说明或解决问题。
