---
title: URC
description: 模式检测器代码帮助页
exl-id: 1be61351-3e3e-4e51-973f-93f8bf9bf932
source-git-commit: 54b121a6ec29ba6ff6fb33b402f1821c34d0763f
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 0%

---

# URC {#urc}

不支持的运行模式配置

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urc_overview"
>title="不支持的运行模式配置"
>abstract="URC标识对基于AEM中不支持的运行模式名称的配置的使用Cloud Service。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html#custom-runmodes" text="支持的运行模式"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html#runmodes" text="运行模式"

`URC` 标识基于AEM中不支持的runmode名称的配置作为Cloud Service的使用。

## 可能的影响和风险{#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urc_guidance"
>title="实施指南"
>abstract="最佳实践是检查应用程序中使用的所有运行模式是否都受支持，并确保它们遵循运行模式解决准则"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/configuring-osgi.html#deploying" text="Runmode解析准则"

* 可用于AEM as a Cloud Service中运行模式的名称集是有限的。
* 部署到AEM作为Cloud Service时，基于不受支持的运行模式名称的配置将不会产生任何影响。

## 可能的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urc_tools"
>title="工具和资源"
>abstract="查看WKND-legacy项目，了解如何使URC违规与AEMCloud Service兼容。 此外，查看Github上的URC违规示例，了解如何更新基于自定义运行模式的OSGi配置，以便与AEM as a ACloud Service一起使用。"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/tree/code/urc" text="WKND旧版项目"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/urc" text="URC违规示例 — Github"

* 查看此配置的使用情况，确定是否需要。
* 重命名配置以使用支持的[runmode名称](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html#custom-runmodes)之一，并遵循[runmode分辨率指南](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/configuring-osgi.html#runmode-resolution)。
* 查看[wknd-legacy](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/urc)项目，并了解如何更正[URC违规](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/urc)并使其与作为Cloud Service的AEM兼容。
* 请联系我们的[AEM支持团队](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以获得说明或解决问题。
