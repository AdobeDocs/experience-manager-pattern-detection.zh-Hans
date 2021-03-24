---
title: URC
description: 图案检测器代码帮助页
translation-type: tm+mt
source-git-commit: ae3e162da40441fba39e6e9d283c495d15f40ba1
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 0%

---


# URC {#urc}

不支持的运行模式配置

## 背景 {#background}

`URC` 标识基于AEM中不支持的运行模式名称的配置作为Cloud Service的使用。

## 可能的影响和风险{#implications-and-risks}

* 在AEM中，作为Cloud Service，可用于运行模式的名称集是有限的。
* 作为Cloud Service部署到AEM时，基于不受支持的运行模式名称的配置不会有任何效果。

## 可能的解决方案{#solutions}

* 查看此配置的使用情况，以确定是否需要。
* 将配置重命名为使用支持的[runmode名称](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html#custom-runmodes)之一，并遵循[runmode分辨率准则](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/configuring-osgi.html#runmode-resolution)。
* 查看[wknd-legacy](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/urc)项目并了解如何更正[URC违规](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/urc)并使其与作为Cloud Service的AEM兼容。
* 请联系我们的[AEM支持团队](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以获得说明或解决问题。
