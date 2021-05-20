---
title: DG
description: 模式检测器代码帮助页
exl-id: 7ee3b177-bd79-41cd-abaf-ece3ae98ce03
source-git-commit: 4ad2fe0fa05b8252112df8a94958e65bb882482d
workflow-type: tm+mt
source-wordcount: '569'
ht-degree: 1%

---

# DG {#dg}

开发人员指南

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dg_overview"
>title="开发人员准则"
>abstract="DG代码可识别AEM 6.5和AEM作为Cloud Service的选定开发准则的偏差。 遵循最佳做法可以提高系统的可维护性和性能。 虽然这些偏差中的某些部分在其他应用程序环境中(包括以前版本的AEM)可能不是问题，但在将AEM用作Cloud Service时，它们可能会导致问题。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/developing/introduction/dev-guidelines-bestpractices.html" text="AEM开发 — 准则和最佳实践"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html" text="AEM as a Cloud Service 开发准则"


`DG` 标识AEM 6.5 [和](https://experienceleague.adobe.com/docs/experience-manager-65/developing/introduction/dev-guidelines-bestpractices.html) AEM as a  [Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html)的选定开发准则的偏差。遵循最佳做法可以提高系统的可维护性和性能。 虽然这些偏差中的某些部分在其他应用程序环境中(包括以前版本的AEM)可能不是问题，但在将AEM用作Cloud Service时，它们可能会导致问题。

子类型用于识别不同类型的检测到的违规：

* `java.io.inputstream`:在应用程序 `java.io.InputStream` 代码中的使用。
* `maintenance.task.configuration`:特定定期维护活动的配置。
* `sling.commons.scheduler`:将Sling Commons调度程序API用于计划任务。

## 可能的影响和风险{#implications-and-risks}

* `java.io.inputstream`
   * 使用`java.io.InputStream`流式传输二进制数据可能会消耗内存资源，直至影响性能。 由于AEM用作Cloud Service的容器中可用的内存有限，因此这尤其是一个问题。

* `maintenance.task.configuration`
   * 以前需要显式配置的某些维护任务现在会在AEM中自动配置和管理，作为Cloud Service。
   * AEM as aCloud Service中的维护任务配置必须移入源代码管理中。

* `sling.commons.scheduler`
   * 依赖于使用[Sling Commons Scheduler](https://sling.apache.org/documentation/bundles/scheduler-service-commons-scheduler.html)的后台任务的应用程序可能无法按预期工作，因为无法保证在AEM中作为Cloud Service执行。
   * AEM as a Cloud Service开发指南（用于[后台任务和长时间运行的作业](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html#background-tasks-and-long-running-jobs)）建议，作为计划任务执行的代码必须假定它正在运行的实例可以随时关闭。 因此，代码必须具有可恢复性。

## 可能的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dg_guidance"
>title="实施指南"
>abstract="按照AEM开发准则和最佳实践，客户应审查其实施中使用Sling Commons Scheduler的情况，并将其重构为Sling作业，重构其系统维护任务，审核任何二进制数据的流，并重构其代码以与AEM as a Cloud Service兼容。"
>additional-url="https://sling.apache.org/documentation/bundles/apache-sling-eventing-and-job-handling.html#jobs-guarantee-of-processing" text="Sling 作业"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/maintenance.html" text="AEM as aCloud Service中的维护任务"

* `java.io.inputstream`
   * 使用直接二进制上传方法，其中将二进制文件直接添加到数据存储中。
   * 对于资产用例，请使用[aem-upload](https://github.com/adobe/aem-upload)。 对于其他类型的二进制文件，可以采用此相同模式来建模自定义上传逻辑。

* `maintenance.task.configuration`
   * 查看AEM as aCloud Service[维护任务](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/maintenance.html)文档。
   * 确保[维护任务配置](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html#maintenance-tasks-configuration-in-source-control)处于源代码管理中。

* `sling.commons.scheduler`
   * 将[Sling Commons Scheduler](https://sling.apache.org/documentation/bundles/scheduler-service-commons-scheduler.html)的使用替换为[Sling作业](https://sling.apache.org/documentation/bundles/apache-sling-eventing-and-job-handling.html#jobs-guarantee-of-processing)，后者至少具有一次执行保证。
   * 如果可能，应避免长时间运行的作业。

* 请联系我们的[AEM支持团队](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以获得说明或解决问题。
