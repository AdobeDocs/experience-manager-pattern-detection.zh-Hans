---
title: WRK
description: Pattern Detector 代码帮助页面。
exl-id: 1be1db54-fc91-45d0-80b5-b2978eee1da8
source-git-commit: 58fdb55e1f0c067dacf6825c4076465bc8c5d821
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 92%

---

# WRK {#wrk}

工作流

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_wrk_overview"
>title="工作流"
>abstract="WRK 代码标识与工作流模型或启动器相关的发现。报告这些信息是因为在升级到 AEM as a Cloud Service 时，必须迁移自定义资源工作流模型。使用 AEM as a Cloud Service，资源处理现在由资源微服务执行。"
>additional-url="https://experienceleague.adobe.com/zh-hans/docs/experience-manager-cloud-service/content/assets/asset-microservices-overview" text="资源微服务"

`WRK`  标识与工作流模型或启动器相关的发现。报告这些信息是因为在升级到 AEM as a Cloud Service 时，必须迁移自定义资源工作流模型。

使用了子类型来标识当前检测到的工作流问题的类型：

* `custom.asset.workflow`：检测自定义资源工作流模型或启动器。

## 可能产生的后果和风险 {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_wrk_guidance"
>title="实施指南"
>abstract="我的资源微服务自动支持标准资源工作流。因此，最佳做法是检查所有自定义资产工作流模型或启动器，查看在转换到 AEM as a Cloud Service 后是否需要它们。对资源工作流的定制设置需要在资源工作流迁移工具的帮助下迁移，以与 AEM as a Cloud Service 配合使用"
>additional-url="https://experienceleague.adobe.com/zh-hans/docs/experience-manager-cloud-service/content/assets/manage/asset-microservices-configure-and-use" text="开始使用 - 资源微服务"

* 传统上，资源处理由资源工作流在 AEM Author 实例上执行。使用 AEM as a Cloud Service，资源处理现在由资源微服务执行。请参阅[资产微服务概述](https://experienceleague.adobe.com/zh-hans/docs/experience-manager-cloud-service/content/assets/asset-microservices-overview)，了解更多信息。
* 我的资源微服务自动支持标准资源工作流。
* 对资源工作流的定制设置需要迁移，以便与 AEM as a Cloud Service 配合使用。

## 可采用的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_wrk_tools"
>title="工具和资源"
>abstract="审查并计划在标识了自定义资源工作流模型或启动器后，运行资源工作流迁移工具。 联系 Adobe 支持获取帮助或说明。"
>additional-url="https://experienceleague.adobe.com/zh-hans/docs/experience-manager-cloud-service/content/migration-journey/refactoring-tools/asset-workflow-migration-tool" text="资源工作流迁移工具"
>additional-url="https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支持"

* 如果标识了自定义资源工作流模型或启动器，则计划运行[资源工作流迁移工具](https://experienceleague.adobe.com/zh-hans/docs/experience-manager-cloud-service/content/migration-journey/refactoring-tools/asset-workflow-migration-tool)。
* 有关更多信息，请查看[开始使用资源微服务](https://experienceleague.adobe.com/zh-hans/docs/experience-manager-cloud-service/content/assets/manage/asset-microservices-configure-and-use)。
* 请联系 [AEM 支持团队](https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html) 进行澄清或解决疑惑。
