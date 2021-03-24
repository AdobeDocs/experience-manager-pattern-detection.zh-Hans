---
title: REP
description: 图案检测器代码帮助页
translation-type: tm+mt
source-git-commit: 7d05067fc624571e6fe520e2a1addd5dff8acbd8
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 2%

---


# [!DNL REP] {#rep}

复制代理

## 背景 {#background}

`REP` 标识已启用的复制代理。由于升级到AEM作为Cloud Service时可能会解决一些问题，因此会报告这些问题。

AEM作为Cloud Service使用[Sling内容分发](https://sling.apache.org/documentation/bundles/content-distribution.html)从作者分发内容以发布环境。 这是在AEM运行时之外使用Adobe I/O的管道服务完成的。这在预配的AEM中自动配置为Cloud Service环境。

## 可能的影响和风险{#implications-and-risks}

* 将AEM作为Cloud Service时，复制的配置已更改。 应查看所有当前复制代理，以查看哪些被标准功能替换，哪些配置必须移动到代码，哪些不受支持。
* 在作为Cloud Service升级到AEM时，应查看在自定义代码或工作流中对复制代理的任何使用。
* 在AEM中，反向复制最初不作为Cloud Service受支持。
* 无需配置单独的调度程序刷新代理。 这在AEM中自动配置为Cloud Service环境。

## 可能的解决方案{#solutions}

* 请参见AEM作为[复制代理](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html#replication-agents)的Cloud Service[开发指南](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html#no-reverse-replication-agents)和发行说明。
* 直接依赖复制代理来检查、重构和优化功能以执行业务任务。
* 了解作为Cloud Service在AEM中部署对[复制](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html#replication)的影响。
* 请联系我们的[AEM支持团队](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以获得说明或解决问题。
