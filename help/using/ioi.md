---
title: IOI
description: Pattern Detector代码帮助页面。
exl-id: b6c9d11f-5189-4799-98c0-c2699dfe3f40
source-git-commit: 84c193b66fbf9c41f546e8575a0aa17e94043b9a
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 64%

---

# IOI {#ioi}

内部 Oak 导入

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ioi_overview"
>title="内部 Oak 导入"
>abstract="IOI 代码标识客户使用内部 Oak 软件包，通过 OSGi 导入它们。它们导出时没有特定版本，仅供其他Oak捆绑包或低级AEM服务使用。"

`IOI`  标识客户使用内部Oak软件包，通过OSGi导入它们。 它们导出时没有特定版本，仅供其他Oak捆绑包或低级AEM服务使用。

其中一些由 `com.adobe.granite.repository` 使用，在启动期间为 AEM 设置存储库。另一个示例是 `com.adobe.granite.maintenance.oak` Adobe 捆绑包，打包并提供 Oak 维护任务。

## 可能的后果和风险 {#implications-and-risks}

* 在未来的 AEM 版本中，内部导出可能会移除，导致依赖关系中断以及直接依赖于 Oak 的捆绑包不活动。
* 内部导出中的 API 可能会更改。

## 可采用的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ioi_guidance"
>title="实施指南"
>abstract="客户应该审查其自定义代码，标识此类 API 的使用，并重构它们以便与 AEM as a Cloud Service 兼容。请联系Adobe支持部门以获取帮助或说明。"
>additional-url="https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支持"

* 使用 Sling 资源 API（或 JCR API）而不是低级访问。
* 避免依赖不属于任何公开 API 或 SPI 的内部软件包。
* 联系 [AEM支持团队](https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html) 以澄清或解决问题。
