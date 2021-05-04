---
title: 工作
description: 图案检测器代码帮助页
exl-id: 1be1db54-fc91-45d0-80b5-b2978eee1da8
translation-type: tm+mt
source-git-commit: 54b121a6ec29ba6ff6fb33b402f1821c34d0763f
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 1%

---

# 工作{#wrk}

工作流

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_wrk_overview"
>title="工作流"
>abstract="WRK代码标识与工作流模型或启动程序相关的查找结果。 报告这些工作流是因为在作为Cloud Service升级到AEM时必须迁移自定义资产工作流模型。 以AEM为Cloud Service，资产处理现在由asset microservices执行。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/asset-microservices-overview.html" text="Asset Microservices"

`WRK` 标识与工作流模型或启动程序相关的查找结果。报告这些工作流是因为在作为Cloud Service升级到AEM时必须迁移自定义资产工作流模型。

子类型用于标识当前检测到的工作流问题的类型。

* `custom.asset.workflow`:检测自定义资源工作流模型或启动器。

## 可能的影响和风险{#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_wrk_guidance"
>title="实施指南"
>abstract="由于标准资产工作流是自动支持我的资产微服务的，最佳实践是检查所有自定义资产工作流模型或启动程序，以查看在我们将AEM过渡为Cloud Service后是否需要它们。 对资产工作流的自定义需要迁移，才能借助资产工作流迁移工具将AEM作为Cloud Service使用"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/asset-microservices-configure-and-use.html" text="快速入门 — Asset Microservices"

* 资产处理通常是通过在AEM作者实例上执行资产工作流来执行的。 以AEM为Cloud Service，资产处理现在由asset microservices执行。 (有关详细信息，请参阅[asset microservices overview](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/asset-microservices-overview.html)。
* 标准资产工作流会自动支持我的资产微服务。
* 对资产工作流的自定义需要迁移，才能将AEM用作Cloud Service。

## 可能的解决方案{#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_wrk_tools"
>title="工具和资源"
>abstract="查看并计划在确定自定义资产工作流模型或启动程序后运行资产工作流迁移工具。 联系Adobe支持以获得帮助和说明"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/refactoring-tools/asset-workflow-migration-tool.html" text="资产工作流迁移工具"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud支持"

* 如果已识别自定义资产工作流模型或启动程序，计划运行[资产工作流迁移工具](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/refactoring-tools/asset-workflow-migration-tool.html)。
* 有关详细信息，请查看[使用资产microservices](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/asset-microservices-configure-and-use.html)快速入门。
* 请联系我们的[AEM支持团队](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以获得说明或解决问题。
