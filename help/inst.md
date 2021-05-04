---
title: INST
description: 图案检测器代码帮助页
exl-id: 9b8129d7-63d7-4975-a68b-9ba704d01532
translation-type: tm+mt
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
>abstract="INST标识客户在AEM中安装的自定义和第三方包和捆绑包。 这些报告有助于描述系统状态和升级工作的一般范围。 任何第三方软件包都必须遵守AEM作为Cloud Service开发和包装指南。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html" text="开发指南 — AEM作为Cloud Service"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/repository-structure-package.html" text="打包指南 — AEM作为Cloud Service"

`INST` 标识客户在AEM中安装的自定义和第三方包和捆绑包。这些报告有助于描述系统状态和升级工作的一般范围。

安装包的多个版本后，只报告最新版本。

检测到的包和包不一定已作为Cloud Service针对AEM进行优化。 任何第三方包都应与其创建者或Adobe一起验证，以确保与AEM作为Cloud Service的兼容性。

子类型用于标识不同类型的信息：

* `custom.bundle`:已安装在AEM中的捆绑包。
* `custom.package`:已在AEM中安装的包。

## 可能的影响和风险{#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_inst_guidance"
>title="实施指南"
>abstract="客户无法再使用CRX包管理器安装第三方包。 客户应查看这些已安装的对象，并需要进行结构化和优化，以便将AEM作为Cloud Service。 任何第三方包都应与其创建者或Adobe一起验证，以确保与AEM作为Cloud Service的兼容性。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html#embeddeds" text="在容器包中嵌入子包"


* 使用CRX包管理器安装第三方包在AEM中不可能作为Cloud Service。
* 依赖第三方包的应用程序在正确部署以作为Cloud Service与AEM一起使用之前可能无法按预期工作。
* 第三方供应商程序包(如果未针对AEM作为云服务进行优化)可能会导致不期望的行为。

## 可能的解决方案{#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_inst_tools"
>title="工具和资源"
>abstract="查看WKND-legacy项目，了解如何使INST违规与AEMCloud Service兼容。 另外，查看Github上的INST违规示例，了解如何更正此问题并在AEM中作为Cloud Service部署。"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/tree/code/inst" text="WKND-Legacy Project"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/inst" text="INST违规示例 — Github"

* 应使用Cloud Manager [部署过程](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/using-cloud-manager/deploy-code.html#deployment-process)将第三方包部署到AEM作为项目的一部分。
* 查看如何在您的项目中将[第三方包](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html#embedding-3rd-party-packages)嵌入AEM作为Cloud Service。
* 第三方包必须作为Cloud Service[development](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html)和[打包](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/repository-structure-package.html)准则遵循AEM。
* 查看[wknd-legacy](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/inst)项目并了解如何更正[INST违规](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/inst)并使其与作为Cloud Service的AEM兼容。
* 请联系我们的[AEM支持团队](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以获得说明或解决问题。
