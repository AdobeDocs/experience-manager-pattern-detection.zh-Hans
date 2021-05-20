---
title: 工作
description: 模式检测器代码帮助页
exl-id: 1be1db54-fc91-45d0-80b5-b2978eee1da8
source-git-commit: 54b121a6ec29ba6ff6fb33b402f1821c34d0763f
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 1%

---

# 工作 {#wrk}

工作流

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_wrk_overview"
>title="工作流"
>abstract="WRK代码标识与工作流模型或启动器相关的发现结果。 之所以会报告这些事件，是因为在升级到AEM as a Cloud Service时，必须迁移自定义资产工作流模型。 现在，将AEM作为Cloud Service，资产处理由资产微服务执行。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/asset-microservices-overview.html" text="资产微服务"

`WRK` 标识与工作流模型或启动器相关的发现结果。之所以会报告这些事件，是因为在升级到AEM as a Cloud Service时，必须迁移自定义资产工作流模型。

子类型用于标识当前检测到的工作流问题类型。

* `custom.asset.workflow`:检测自定义资产工作流模型或启动器。

## 可能的影响和风险{#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_wrk_guidance"
>title="实施指南"
>abstract="由于标准资产工作流自动受我的资产微服务支持，因此最佳实践是检查所有自定义资产工作流模型或启动器，以查看在我们迁移到AEM as a Cloud Service后是否需要这些工作流。 资产工作流的自定义需要迁移，才能在资产工作流迁移工具的帮助下将AEM作为Cloud Service使用"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/asset-microservices-configure-and-use.html" text="入门 — 资产微服务"

* 资产处理传统上通过在AEM创作实例上执行资产工作流来执行。 现在，将AEM作为Cloud Service，资产处理由资产微服务执行。 (有关更多信息，请参阅[资产微服务概述](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/asset-microservices-overview.html) 。
* 我的资产微服务自动支持标准资产工作流。
* 为了将AEM用作Cloud Service，资产工作流的自定义需要迁移。

## 可能的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_wrk_tools"
>title="工具和资源"
>abstract="查看并计划在确定自定义资产工作流模型或启动器后运行资产工作流迁移工具。 联系Adobe支持以获取帮助和说明"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/refactoring-tools/asset-workflow-migration-tool.html" text="资产工作流迁移工具"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud支持"

* 如果已识别自定义资产工作流模型或启动器，请计划运行[资产工作流迁移工具](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/refactoring-tools/asset-workflow-migration-tool.html)。
* 有关更多信息，请参阅[资产微服务入门](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/asset-microservices-configure-and-use.html)。
* 请联系我们的[AEM支持团队](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以获得说明或解决问题。
