---
title: ASO
description: 图案检测器代码帮助页
exl-id: 2ba416b7-80c1-4ec5-a6bf-d80f6d625b07
translation-type: tm+mt
source-git-commit: 449288e567adda9998a89e0ad5198fd5a4e93f35
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 5%

---

# ASO {#aso}

AEM系统概述

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_aso_overview"
>title="AEM系统概述"
>abstract="ASO代码标识有关AEM实例的常规信息。 每个查找结果都提供特定类型系统信息的一个值，有助于您进行迁移规划和重构工作。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html" text="AEM as a Cloud Service — 发行说明"

`ASO` 标识有关AEM实例的常规信息。每个查找都提供特定类型系统信息的一个值。

子类型用于标识不同类型的信息：

* `aem.version`:AEM版本。
* `aem.product`:检测AEM产品(商务、Forms等)的使用。
* `node.count`:特定类型（页面、资产等）的近似节点计数。
* `node.store`:节点存储实现类型(SegmentNodeStore、DocumentNodeStore)。
* `data.store`:数据存储实现类型(FileDataStore、S3DataStore、AzureDataStore)。
* `maintenance.task`:维护任务。
* `slow.query`:慢查询。

## 可能的影响和风险{#implications-and-risks}

* AEM版本、节点计数、节点存储和数据存储实现类型被提供用于信息目的。
* 自定义应用程序可能依赖于AEM中没有的产品或功能作为Cloud Service。
* 使用不支持的功能进行升级可能导致升级失败和应用程序无法正常工作。

## 可能的解决方案{#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_aso_guidance"
>title="实施指南"
>abstract="通过ASO代码公开的信息为您的AEM环境提供了一般信息，包括版本、产品附加组件、系统级别信息，应对AEM中作为Cloud Service的任何不受支持的产品或功能进行审查。 联系Adobe支持以获得帮助和说明。"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud支持"

* 不建议使用不支持的产品或功能进行AEM升级，可能不支持。
* 查看[发行说明](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html?lang=zh-Hans)，了解作为Cloud Service的AEM中的最新更改。
* 请联系我们的[AEM支持团队](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以获得说明或解决问题。
