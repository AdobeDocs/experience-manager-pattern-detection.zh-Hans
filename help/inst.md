---
title: INST
description: 图案检测器代码帮助页
translation-type: tm+mt
source-git-commit: ae3e162da40441fba39e6e9d283c495d15f40ba1
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 0%

---


# INST {#inst}

已安装的对象

## 背景 {#background}

`INST` 标识客户在AEM中安装的自定义和第三方包和捆绑包。这些报告有助于描述系统状态和升级工作的一般范围。

安装包的多个版本后，只报告最新版本。

检测到的包和包不一定已作为Cloud Service针对AEM进行优化。 任何第三方包都应与其创建者或Adobe一起验证，以确保与AEM作为Cloud Service的兼容性。

子类型用于标识不同类型的信息：

* `custom.bundle`:已安装在AEM中的捆绑包。
* `custom.package`:已在AEM中安装的包。

## 可能的影响和风险{#implications-and-risks}

* 使用CRX包管理器安装第三方包在AEM中不可能作为Cloud Service。
* 依赖第三方包的应用程序在正确部署以作为Cloud Service与AEM一起使用之前可能无法按预期工作。
* 第三方供应商程序包(如果未针对AEM作为云服务进行优化)可能会导致不期望的行为。

## 可能的解决方案{#solutions}

* 应使用Cloud Manager [部署过程](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/using-cloud-manager/deploy-code.html#deployment-process)将第三方包部署到AEM作为项目的一部分。
* 查看如何在您的项目中将[第三方包](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html#embedding-3rd-party-packages)嵌入AEM作为Cloud Service。
* 第三方包必须作为Cloud Service[development](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html)和[打包](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/repository-structure-package.html)准则遵循AEM。
* 查看[wknd-legacy](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/inst)项目并了解如何更正[INST违规](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/inst)并使其与作为Cloud Service的AEM兼容。
* 请联系我们的[AEM支持团队](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以获得说明或解决问题。
