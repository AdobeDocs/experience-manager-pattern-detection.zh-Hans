---
title: URC
description: Pattern Detector 代码帮助页面。
exl-id: 1be61351-3e3e-4e51-973f-93f8bf9bf932
source-git-commit: 84c193b66fbf9c41f546e8575a0aa17e94043b9a
workflow-type: ht
source-wordcount: '261'
ht-degree: 100%

---

# URC {#urc}

不受支持的运行模式配置

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urc_overview"
>title="不受支持的运行模式配置"
>abstract="URC 标识使用了基于 AEM as a Cloud Service 中不支持的运行模式名称的配置。"
>additional-url="https://experienceleague.adobe.com/zh-hans/docs/experience-manager-cloud-service/content/release-notes/aem-cloud-changes#custom-runmodes" text="支持的运行模式"
>additional-url="https://experienceleague.adobe.com/zh-hans/docs/experience-manager-cloud-service/content/implementing/deploying/overview#runmodes" text="运行架构"

`URC`  标识使用了基于 AEM as a Cloud Service 中不支持的运行模式名称的配置。

## 可能产生的后果和风险 {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urc_guidance"
>title="实施指南"
>abstract="最佳实践审查应用程序中使用的所有运行模式是否都受支持，确保它们遵循运行模式解决方法准则"
>additional-url="https://experienceleague.adobe.com/zh-hans/docs/experience-manager-cloud-service/content/implementing/deploying/configuring-osgi#deploying" text="运行模式解决方法准则"

* 在 AEM as a Cloud Service 中可以用于运行各种模式的一组名称是有限的。
* 基于不支持运行模式名称的配置在部署到 AEM as a Cloud Service 时将不起作用。

## 可采用的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urc_tools"
>title="工具和资源"
>abstract="审查 WKND 旧版项目，了解如何使 URC 违规与 AEM Cloud Service 兼容。此外，查看 GitHub 上的 URC 违规示例，了解如何更新基于自定义运行模式的 OSGi 配置以使其遵循 AEM as a Cloud Service。"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/tree/code/urc" text="WKND 旧版项目"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/urc" text="URC 违规示例 - GitHub"

* 审查此配置的使用，确定其是否必需。
* 使用支持的[运行模式名称](https://experienceleague.adobe.com/zh-hans/docs/experience-manager-cloud-service/content/release-notes/aem-cloud-changes#custom-runmodes)之一重新命名配置并遵循[运行模式解决方法准则](https://experienceleague.adobe.com/zh-hans/docs/experience-manager-cloud-service/content/implementing/deploying/configuring-osgi#runmode-resolution)。
* 审查 [wknd 旧版](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/urc)项目，了解如何更正 [URC 违规](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/urc)，使其与 AEM as a Cloud Service 兼容。
* 请联系 [AEM 支持团队](https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html) 进行澄清或解决疑惑。
