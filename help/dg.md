---
title: DG
description: 图案检测器代码帮助页
translation-type: tm+mt
source-git-commit: a2c7137dd5cb2479bc0c6134d3afa58111049a68
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 0%

---


# DG {#dg}

开发人员指南

## 背景 {#background}

`DG` 确定AEM 6.5和AEM作 [为Cloud Service的选](https://experienceleague.adobe.com/docs/experience-manager-65/developing/introduction/dev-guidelines-bestpractices.html) 定 [开发指南的偏差](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html)。遵循最佳做法可以提高系统的可维护性和性能。 尽管这些偏差中的某些部分在其他应用程序上下文(包括早期版本的AEM)中可能不是问题，但在将AEM用作Cloud Service时，它们可能会导致问题。

子类型用于识别不同类型的检测到的违规：

* `java.io.inputstream`:在应用程 `java.io.InputStream` 序代码中的使用。
* `maintenance.task.configuration`:某个定期维护活动的配置。
* `sling.commons.scheduler`:将Sling Commons调度程序API用于计划任务。

## 可能的影响和风险{#implications-and-risks}

* `java.io.inputstream`
   * 使用`java.io.InputStream`的二进制数据流会消耗内存资源，直至影响性能。 由于AEM用作Cloud Service的容器中的可用内存有限，这尤其是一个问题。

* `maintenance.task.configuration`
   * 某些以前需要显式配置的维护任务现在在AEM中自动配置为Cloud Service。
   * AEM中作为Cloud Service的维护任务配置必须移入源控件中。

* `sling.commons.scheduler`
   * 依赖于使用[Sling Commons调度程序](https://sling.apache.org/documentation/bundles/scheduler-service-commons-scheduler.html)的后台任务的应用程序可能无法按预期工作，因为无法保证在AEM中作为Cloud Service执行。
   * AEM作为[后台任务和长运行作业的Cloud Service开发准则](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html#background-tasks-and-long-running-jobs)建议，作为计划任务执行的代码必须假设它正在运行的实例可以随时关闭。 因此，代码必须具有弹性并且可恢复。

## 可能的解决方案{#solutions}

* `java.io.inputstream`
   * 使用直接二进制上载方法，其中将二进制直接添加到数据存储中。
   * 对于资产使用案例，请使用[aem-upload](https://github.com/adobe/aem-upload)。 对于其他类型的二进制文件，自定义上载逻辑可以基于此相同模式建模。

* `maintenance.task.configuration`
   * 将AEM作为Cloud Service[维护任务](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/maintenance.html)文档审阅。
   * 确保[维护任务配置](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html#maintenance-tasks-configuration-in-source-control)处于源代码控制中。

* `sling.commons.scheduler`
   * 将使用[Sling Commons调度程序](https://sling.apache.org/documentation/bundles/scheduler-service-commons-scheduler.html)替换为[Sling Jobs](https://sling.apache.org/documentation/bundles/apache-sling-eventing-and-job-handling.html#jobs-guarantee-of-processing)，后者具有至少一次执行保证。
   * 如果可能，应避免长时间运行的作业。

* 请联系我们的[AEM支持团队](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以获得说明或解决问题。
