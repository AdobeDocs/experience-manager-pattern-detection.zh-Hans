---
title: 麻生
description: 模式检测器代码帮助页
exl-id: 2ba416b7-80c1-4ec5-a6bf-d80f6d625b07
source-git-commit: 3e05ecb2c78b0ebf97d334cf592347b54255c75f
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 4%

---

# 麻生 {#aso}

AEM系统概述

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_aso_overview"
>title="AEM系统概述"
>abstract="ASO代码标识有关AEM实例的常规信息。 每个发现结果都提供特定类型系统信息的一个值，可帮助您进行迁移规划和重构工作。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html" text="AEMas a Cloud Service — 发行说明"

`ASO` 标识有关AEM实例的常规信息。 每个发现结果都提供特定类型系统信息的一个值。

子类型用于标识不同类型的信息：

* `aem.version`:AEM版本。
* `aem.product`:检测AEM产品(商务、Forms等)的使用情况。
* `node.count`:特定类型（页面、资产等）的近似节点计数 和节点总数。
* `node.store`:节点存储实现类型(SegmentNodeStore、DocumentNodeStore)及其大小。
* `data.store`:数据存储实施类型(FileDataStore、S3DataStore、AzureDataStore)。
* `maintenance.task`:维护任务。
* `slow.query`:查询速度慢。
* `group.membership`:组中的用户和子组（仅直接/声明的成员）数。

## 可能的影响和风险 {#implications-and-risks}

* AEM版本、节点计数、组成员资格、节点存储和数据存储实施类型仅供参考。
* 自定义应用程序可能依赖于AEMas a Cloud Service中不可用的产品或功能。
* 使用不支持的功能进行升级可能会导致升级失败和应用程序无法正常工作。

## 可能的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_aso_guidance"
>title="实施指南"
>abstract="通过ASO代码公开的信息提供了AEM环境的一般信息，包括版本、产品附加组件、系统级别信息，应对AEMas a Cloud Service中任何不支持的产品或功能进行审查。 联系Adobe支持以获取帮助和说明。"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud支持"

* 不建议使用不受支持的产品或功能进行AEM升级，因此可能不受支持。
* 查看 [发行说明](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html?lang=zh-Hans) 以了解AEM as a Cloud Service中的最新更改。
* 请联系我们的 [AEM支持团队](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) 澄清或解决问题。
