---
title: 工作
description: 图案检测器代码帮助页
translation-type: tm+mt
source-git-commit: 2391ad7851d4e6634a7bacd684b08db44a9c78e8
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 1%

---


# 工作{#wrk}

工作流

## 背景 {#background}

`WRK` 标识与工作流模型或启动程序相关的查找结果。报告这些工作流是因为在作为Cloud Service升级到AEM时必须迁移自定义资产工作流模型。

子类型用于标识当前检测到的工作流问题的类型。

* `custom.asset.workflow`:检测自定义资源工作流模型或启动器。

## 可能的影响和风险{#implications-and-risks}

* 资产处理通常是通过在AEM作者实例上执行资产工作流来执行的。 以AEM为Cloud Service，资产处理现在由asset microservices执行。 (有关详细信息，请参阅[asset microservices overview](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/asset-microservices-overview.html)。
* 标准资产工作流会自动支持我的资产微服务。
* 对资产工作流的自定义需要迁移，才能将AEM用作Cloud Service。

## 可能的解决方案{#solutions}

* 如果已识别自定义资产工作流模型或启动程序，计划运行[资产工作流迁移工具](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/refactoring-tools/asset-workflow-migration-tool.html)。
* 有关详细信息，请查看[使用资产microservices](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/asset-microservices-configure-and-use.html)快速入门。
* 请联系我们的[AEM支持团队](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以获得说明或解决问题。
