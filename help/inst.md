---
title: INST
description: 模式检测器代码帮助页
exl-id: 9b8129d7-63d7-4975-a68b-9ba704d01532
source-git-commit: 54b121a6ec29ba6ff6fb33b402f1821c34d0763f
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 0%

---

# INST {#inst}

已安装的对象

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_inst_overview"
>title="已安装的对象"
>abstract="INST标识客户在AEM中安装的自定义和第三方包及包。 这些报告有助于描述系统状态和升级工作的一般范围。 任何第三方包都必须遵循AEM as a Cloud Service开发和打包准则。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html" text="开发准则 — AEM as aCloud Service"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/repository-structure-package.html" text="打包准则 — AEM as aCloud Service"

`INST` 标识客户在AEM中安装的自定义和第三方包及包。这些报告有助于描述系统状态和升级工作的一般范围。

安装包的多个版本后，只会报告最新版本。

检测到的包和包未必已针对AEM as aCloud Service进行优化。 任何第三方包都应与其创建者或Adobe一起进行验证，以确保与AEM作为Cloud Service的兼容性。

子类型用于标识不同类型的信息：

* `custom.bundle`:已安装在AEM中的包。
* `custom.package`:已在AEM中安装的包。

## 可能的影响和风险{#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_inst_guidance"
>title="实施指南"
>abstract="客户无法再使用CRX包管理器安装第三方包。 客户应该查看这些已安装的工件，并需要对其进行结构优化，以便与AEM作为Cloud Service一起使用。 任何第三方包都应与其创建者或Adobe一起进行验证，以确保与AEM作为Cloud Service的兼容性。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html#embeddeds" text="在容器包中嵌入子包"


* 在AEM中，无法使用CRX包管理器安装第三方包作为Cloud Service。
* 依赖于第三方包的应用程序在正确部署以与AEM作为Cloud Service配合使用之前可能无法按预期工作。
* 如果未针对AEM as a Cloud Service进行优化，则第三方供应商包可能会导致不希望的行为。

## 可能的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_inst_tools"
>title="工具和资源"
>abstract="查看WKND-legacy项目，了解如何使INST违规与AEMCloud Service兼容。 此外，请查看Github上的INST违规示例，了解如何更正该问题并将其作为Cloud Service部署在AEM中。"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/tree/code/inst" text="WKND旧版项目"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/inst" text="INST违规示例 — Github"

* 应使用Cloud Manager [部署过程](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/using-cloud-manager/deploy-code.html#deployment-process)将第三方包部署到AEM作为项目的一部分。
* 查看如何在您的项目中[嵌入第三方包](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html#embedding-3rd-party-packages)以将AEM作为Cloud Service。
* 第三方包必须遵循AEM as a A Compage [development](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html)和[打包](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/repository-structure-package.html)指南。
* 查看[wknd-legacy](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/inst)项目，并了解如何更正[INST违规](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/inst)并使其与作为Cloud Service的AEM兼容。
* 请联系我们的[AEM支持团队](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以获得说明或解决问题。
