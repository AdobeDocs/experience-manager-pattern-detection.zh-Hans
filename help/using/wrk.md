---
title: WRK
description: Pattern Detector代码帮助页面。
exl-id: 1be1db54-fc91-45d0-80b5-b2978eee1da8
source-git-commit: 616fa84f6237893243cffc8af28c7cbe76bf32d7
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 62%

---

# WRK {#wrk}

工作流

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_wrk_overview"
>title="工作流"
>abstract="WRK 代码标识与工作流模型或启动器相关的发现。报告这些信息是因为在升级到 AEM as a Cloud Service 时，必须迁移自定义资源工作流模型。使用 AEM as a Cloud Service，资源处理现在由资源微服务执行。"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/assets/asset-microservices-overview" text="资源微服务"

WRK标识与工作流模型或启动器相关的发现。 报告这些信息是因为在升级到 AEM as a Cloud Service 时，必须迁移自定义资源工作流模型。

使用了子类型来标识当前检测到的工作流问题的类型：

* `custom.asset.workflow`：检测自定义资源工作流模型或启动器。

## 可能的后果和风险 {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_wrk_guidance"
>title="实施指南"
>abstract="我的资源微服务自动支持标准资源工作流。 因此，最佳实践是审查所有自定义资源工作流模型或启动器，查看在迁移到AEMas a Cloud Service后是否需要它们。 对资源工作流的自定义设置需要在AEM Workflow Migration Tool的帮助下迁移以用于as a Cloud Service"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/assets/manage/asset-microservices-configure-and-use" text="开始使用 - 资源微服务"

* 传统上，资源处理由资源工作流在 AEM Author 实例上执行。使用 AEM as a Cloud Service，资源处理现在由资源微服务执行。请参阅 [资源微服务概述](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/assets/asset-microservices-overview) 以了解更多信息。
* 我的资源微服务自动支持标准资源工作流。
* 对资源工作流的自定义设置需要迁移才能与AEMas a Cloud Service配合使用。

## 可采用的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_wrk_tools"
>title="工具和资源"
>abstract="审查并计划在标识了自定义资源工作流模型或启动器之后，运行资源工作流迁移工具。请联系Adobe支持部门以获取帮助或说明。"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/migration-journey/refactoring-tools/asset-workflow-migration-tool" text="资源工作流迁移工具"
>additional-url="https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支持"

* 如果标识了自定义资源工作流模型或启动器，则计划运行[资源工作流迁移工具](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/migration-journey/refactoring-tools/asset-workflow-migration-tool)。
* 有关更多信息，请查看[开始使用资源微服务](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/assets/manage/asset-microservices-configure-and-use)。
* 联系 [AEM支持团队](https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html) 以澄清或解决问题。
