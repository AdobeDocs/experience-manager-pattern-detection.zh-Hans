---
title: URC
description: Pattern Detector 代码帮助页面
exl-id: 1be61351-3e3e-4e51-973f-93f8bf9bf932
source-git-commit: f1e833bea35ef3b412936d529b14bff6f1cb35c1
workflow-type: ht
source-wordcount: '319'
ht-degree: 100%

---

# URC {#urc}

不受支持的 Runmode 配置

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urc_overview"
>title="不受支持的 Runmode 配置"
>abstract="URC 标识使用了配置，而这些配置基于 AEM as a Cloud Service 中不支持的运行模式名称。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html#custom-runmodes" text="支持的运行模式"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html#runmodes" text="运行模式"

`URC` 标识使用了配置，而这些配置基于 AEM as a Cloud Service 中不支持的运行模式名称。

## 可能的后果和风险 {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urc_guidance"
>title="实施指南"
>abstract="最佳实践是审查是否支持您的应用程序中使用的所有运行模式，确保它们遵循运行模式解决方法准则"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/configuring-osgi.html#deploying" text="运行模式解决方法准则"

* 可以用于运行模式的一组名称在 AEM as a Cloud Service 中是有限的。
* 基于不支持运行模式的配置在部署到 AEM as a Cloud Service 时将不起作用。

## 可采用的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urc_tools"
>title="工具和资源"
>abstract="审查 WKND 旧版项目，了解如何使 URC 违规与 AEM Cloud Service 兼容。此外，查看 Github 上的 URC 违规示例，了解如何更新基于自定义运行模式的 OSGi 配置以使其遵循 AEM as a Cloud Service。"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/tree/code/urc" text="WKND 旧版项目"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/urc" text="URC 违规示例 - Github"

* 审查此配置的使用，确定是否必需。
* 重命名配置以使用支持的[运行模式名称](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html#custom-runmodes)之一并遵循[运行模式解决方法准则](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/configuring-osgi.html#runmode-resolution)。
* 审查 [wknd 旧版](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/urc)项目，了解如何更正 [URC 违规](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/urc)，使其与 AEM as a Cloud Service 兼容。
* 请联系我们的 [AEM 支持团队](https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html)获取说明或解决问题。
