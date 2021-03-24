---
title: ASO
description: 图案检测器代码帮助页
translation-type: tm+mt
source-git-commit: a2c7137dd5cb2479bc0c6134d3afa58111049a68
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 4%

---


# ASO {#aso}

AEM系统概述

## 背景 {#background}

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

* 不建议使用不支持的产品或功能进行AEM升级，可能不支持。
* 查看[发行说明](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html)，了解作为Cloud Service的AEM中的最新更改。
* 请联系我们的[AEM支持团队](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以获得说明或解决问题。
