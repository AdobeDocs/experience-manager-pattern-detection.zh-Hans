---
title: DG
description: Pattern Detector 代码帮助页面。
exl-id: 7ee3b177-bd79-41cd-abaf-ece3ae98ce03
source-git-commit: 8dd9a42a3bba63d62fa2469b0f78ca15a608b4f9
workflow-type: tm+mt
source-wordcount: '737'
ht-degree: 80%

---

# DG {#dg}

开发人员指南

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dg_overview"
>title="开发人员指南"
>abstract="DG 代码标识 AEM 6.5 和 AEM as a Cloud Service 的所选开发准则的偏差。遵循最佳实践可以改进系统的可维护性和性能。虽然一些偏差在其他应用程序上下文中可能不是问题，包括在以前版本的 AEM 中，但它们在与 AEM as a Cloud Service 一起使用时可能导致问题。"
>additional-url="https://experienceleague.adobe.com/zh-hans/docs/experience-manager-65/content/implementing/developing/introduction/dev-guidelines-bestpractices" text="AEM 开发 - 准则和最佳实践"
>additional-url="https://experienceleague.adobe.com/zh-hans/docs/experience-manager-cloud-service/content/implementing/developing/development-guidelines" text="AEM as a Cloud Service 开发准则"


`DG`  标识 [AEM 6.5](https://experienceleague.adobe.com/zh-hans/docs/experience-manager-65/content/implementing/developing/introduction/dev-guidelines-bestpractices) 和 [AEM as a Cloud Service](https://experienceleague.adobe.com/zh-hans/docs/experience-manager-cloud-service/content/implementing/developing/development-guidelines) 的所选开发准则的偏差。遵循最佳实践可以改进系统的可维护性和性能。虽然一些偏差在其他应用程序上下文中可能不是问题，包括在以前版本的 AEM 中，但它们在与 AEM as a Cloud Service 一起使用时可能导致问题。

子类型用于标识所检测偏差的不同类型，例如：

* `java.io.inputstream`：在应用程序代码中使用 `java.io.InputStream`。
* `maintenance.task.configuration`：特定定期维护活动的配置。
* `sling.commons.scheduler`：为调度的任务使用 Sling Commons Scheduler API。
* `unsupported.asset.api`：在应用程序代码中使用不支持的 Asset Manager API。
* `javax.jcr.observation.EventListener`：在应用程序代码中使用事件侦听器。
* `custom.guava.cache`：在应用程序代码中使用 Guava 缓存。
* `java.api`：某些Java API已从Java 11移至Java 17。
* `configuration.admin`：将标记访问配置的自定义代码。
* `guava.api`：不支持AEM 6.5 LTS中开箱即用的Guava。
* `com.day.cq.dam.scene7.api.model`： `package com.day.cq.dam.scene7.api.model`有主要版本更改。

## 可能产生的后果和风险 {#implications-and-risks}

* `java.io.inputstream`
   * 使用 `java.io.InputStream` 流式传输二进制数据占用的内存资源造成了性能影响。这个问题的发生是由于在 AEM as a Cloud Service 中使用的容器的可用内存有限。

* `maintenance.task.configuration`
   * 以前需要明确配置的一些维护任务现在可在 AEM as a Cloud Service 中自动配置和管理。
   * AEM as a Cloud Service 中的维护任务配置必须移动到源控件中。

* `sling.commons.scheduler`
   * 由于在 AEM as a Cloud Service 中无法保证执行，依赖于使用 [Sling Commons Scheduler](https://sling.apache.org/documentation/bundles/scheduler-service-commons-scheduler.html) 的后台任务的应用程序可能无法正常工作。
   * 适用于[后台任务和长时间运行作业](https://experienceleague.adobe.com/zh-hans/docs/experience-manager-cloud-service/content/implementing/developing/development-guidelines#background-tasks-and-long-running-jobs)的准则建议，作为计划任务运行的代码，也必须假定运行它的实例可以随时关闭。因此，代码必须具有弹性且可恢复。

* `unsupported.asset.api`
   * 以下 AssetManager API 在 AEM as a Cloud Service 中被标记为不受支持。
      * createAssetForBinary
      * getAssetForBinary
      * removeAssetForBinary
      * createAsset

* `javax.jcr.observation.EventListener`
   * 依赖于事件侦听器的应用程序可能无法按预期工作，因为无法保证执行。

* `custom.guava.cache`
   * 使用 Guava 缓存可能会导致 AEM 中出现性能问题。

* `java.api`
   * 在JRE17上使用AEM 6.5 LTS时，这些已删除的Java API将不可用，并且其使用将失败。

* `configuration.admin`
   * 您应该查看自己的使用情况，以确保未使用任何不受支持的配置，例如social。

* `guava.api`
   * 由于AEM 6.5 LTS不支持Guava，因此使用Guava的自定义代码将处于非活动状态。

* `com.day.cq.dam.scene7.api.model`
   * 由于主要版本更改，无法解析自定义捆绑包中导入的包`com.day.cq.dam.scene7.api.model`。


## 可采用的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dg_guidance"
>title="实施指南"
>abstract="检查您对 Sling Commons Scheduler 的使用情况。将它们重组为 Sling Jobs，重组其系统维护任务，审查任何二进制数据的流式处理，并重构其代码以符合 AEM as a Cloud Service 的要求。"
>additional-url="https://sling.apache.org/documentation/bundles/apache-sling-eventing-and-job-handling.html#jobs-guarantee-of-processing" text="Sling 作业"
>additional-url="https://experienceleague.adobe.com/zh-hans/docs/experience-manager-cloud-service/content/operations/maintenance" text="AEM as a Cloud Service 中的维护任务"

* `java.io.inputstream`
   * 使用直接二进制上传方法，这种方法直接将二进制数据添加到数据存储。
   * 请参阅 [aem-upload](https://github.com/adobe/aem-upload)，了解资源用例。对于其他类型的二进制数据，可以在此相同的模式之后对自定义上传逻辑建模。

* `maintenance.task.configuration`
   * 审查 AEM as a Cloud Service [维护任务](https://experienceleague.adobe.com/zh-hans/docs/experience-manager-cloud-service/content/operations/maintenance)文档。
   * 确保[维护任务配置](https://experienceleague.adobe.com/zh-hans/docs/experience-manager-cloud-service/content/implementing/deploying/overview#maintenance-tasks-configuration-in-source-control)位于源控件中。

* `sling.commons.scheduler`
   * 将使用的 [Sling Commons Scheduler](https://sling.apache.org/documentation/bundles/scheduler-service-commons-scheduler.html) 替换为 [Sling 作业](https://sling.apache.org/documentation/bundles/apache-sling-eventing-and-job-handling.html#jobs-guarantee-of-processing)，这具有至少一次执行保证。
   * 应避免长时间运行作业。

* `unsupported.asset.api`
   * 请参阅 [aem-upload](https://github.com/adobe/aem-upload) 代替使用不支持的 Asset Manager API。

* `javax.jcr.observation.EventListener`
   * 建议将事件处理机制重构为 [Sling 任务](https://sling.apache.org/documentation/bundles/apache-sling-eventing-and-job-handling.html#jobs-guarantee-of-processing)，而不是使用事件监听器，因为这些任务可以保证进行处理。

* `custom.guava.cache`
   * 如果需要，应在 AEM 外部创建缓存。可以考虑外部缓存解决方案。
* 请联系 [AEM 支持团队](https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html) 进行澄清或解决疑惑。

* `configuration.admin`
   * 删除任何不受支持的功能（如Social）的配置用法。

* `guava.api`
   * 请安装Guava，如果自定义代码中使用了Guava，请删除用法。

* `com.day.cq.dam.scene7.api.model`
   * 将导入的包`com.day.cq.dam.scene7.api.model`的版本范围更新为&#x200B;**3.0.4**。