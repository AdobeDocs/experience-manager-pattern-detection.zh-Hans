---
title: DG
description: Pattern Detector 代码帮助页面
exl-id: 7ee3b177-bd79-41cd-abaf-ece3ae98ce03
source-git-commit: f1e833bea35ef3b412936d529b14bff6f1cb35c1
workflow-type: ht
source-wordcount: '667'
ht-degree: 100%

---

# DG {#dg}

开发人员指南

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dg_overview"
>title="开发人员指南"
>abstract="DG 代码标识 AEM 6.5 和 AEM as a Cloud Service 的所选开发准则的偏差。遵循最佳实践可以改进系统的可维护性和性能。虽然一些偏差在其他应用程序上下文中可能不是问题，包括在以前版本的 AEM 中，但它们在与 AEM as a Cloud Service 一起使用时可能导致问题。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/developing/introduction/dev-guidelines-bestpractices.html" text="AEM 开发 - 准则和最佳实践"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html" text="AEM as a Cloud Service 开发准则"


`DG` 代码标识 [AEM 6.5](https://experienceleague.adobe.com/docs/experience-manager-65/developing/introduction/dev-guidelines-bestpractices.html) 和 [AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html) 的所选开发准则的偏差。遵循最佳实践可以改进系统的可维护性和性能。虽然一些偏差在其他应用程序上下文中可能不是问题，包括在以前版本的 AEM 中，但它们在与 AEM as a Cloud Service 一起使用时可能导致问题。

子类型用于标识所检测偏差的不同类型，例如：

* `java.io.inputstream`：在应用程序代码中使用 `java.io.InputStream`。
* `maintenance.task.configuration`：特定定期维护活动的配置。
* `sling.commons.scheduler`：为调度的任务使用 Sling Commons Scheduler API。
* `unsupported.asset.api`：在应用程序代码中使用不支持的 Asset Manager API。
* `javax.jcr.observation.EventListener`：在应用程序代码中使用事件侦听器。

## 可能的后果和风险 {#implications-and-risks}

* `java.io.inputstream`
   * 使用 `java.io.InputStream` 流式传输二进制数据占用的内存资源造成了性能影响。由于在 AEM as a Cloud Service 中使用的容器的可用内存有限，这个问题尤为明显。

* `maintenance.task.configuration`
   * 以前需要明确配置的一些维护任务现在可在 AEM as a Cloud Service 中自动配置和管理。
   * AEM as a Cloud Service 中的维护任务配置必须移动到源控件中。

* `sling.commons.scheduler`
   * 由于在 AEM as a Cloud Service 中无法保证执行，依赖于使用 [Sling Commons Scheduler](https://sling.apache.org/documentation/bundles/scheduler-service-commons-scheduler.html) 的后台任务的应用程序可能无法正常工作。
   * [后台任务和长时间运行作业](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html#background-tasks-and-long-running-jobs)的 AEM as a Cloud Service 开发准则建议，作为计划任务执行的代码，必须假定运行它的实例可以随时关闭。因此，代码必须具有弹性且可恢复。

* `unsupported.asset.api`
   * 以下 AssetManager API 在 AEM as a Cloud Service 中被标记为不受支持。
      * createAssetForBinary
      * getAssetForBinary
      * removeAssetForBinary
      * createAsset

* `javax.jcr.observation.EventListener`
   * 依赖于事件侦听器的应用程序可能无法按预期工作，因为无法保证执行。


## 可采用的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dg_guidance"
>title="实施指南"
>abstract="遵循 AEM 开发准则和最佳实践，客户应审查其实现对 Sling Commons Scheduler 的使用并将其重构为 Sling 作业，重构其系统维护任务，审核任意二进制数据的流式传输，并重构其代码以便与 AEM as a Cloud Service 兼容。"
>additional-url="https://sling.apache.org/documentation/bundles/apache-sling-eventing-and-job-handling.html#jobs-guarantee-of-processing" text="Sling 作业"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/maintenance.html" text="AEM as a Cloud Service 中的维护任务"

* `java.io.inputstream`
   * 使用直接二进制上传方法，这种方法直接将二进制数据添加到数据存储。
   * 对于资源用例，请使用 [aem-upload](https://github.com/adobe/aem-upload)。对于其他类型的二进制数据，可以在此相同的模式之后对自定义上传逻辑建模。

* `maintenance.task.configuration`
   * 审查 AEM as a Cloud Service [维护任务](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/maintenance.html)文档。
   * 确保[维护任务配置](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html#maintenance-tasks-configuration-in-source-control)位于源控件中。

* `sling.commons.scheduler`
   * 将使用的 [Sling Commons Scheduler](https://sling.apache.org/documentation/bundles/scheduler-service-commons-scheduler.html) 替换为 [Sling 作业](https://sling.apache.org/documentation/bundles/apache-sling-eventing-and-job-handling.html#jobs-guarantee-of-processing)，这具有至少一次执行保证。
   * 应尽可能避免长时间运行作业。

* `unsupported.asset.api`
   * 请使用 [aem-upload](https://github.com/adobe/aem-upload) 代替使用不支持的 Asset Manager API。

* `javax.jcr.observation.EventListener`
   * 建议将事件处理机制重构为 [Sling 任务](https://sling.apache.org/documentation/bundles/apache-sling-eventing-and-job-handling.html#jobs-guarantee-of-processing)，而不是使用事件监听器，因为这些任务可以保证进行处理。
* 请联系我们的 [AEM 支持团队](https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html)以获得澄清或解决关切。
