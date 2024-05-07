---
title: INST
description: Pattern Detector 代码帮助页面。
exl-id: 9b8129d7-63d7-4975-a68b-9ba704d01532
source-git-commit: 84c193b66fbf9c41f546e8575a0aa17e94043b9a
workflow-type: ht
source-wordcount: '446'
ht-degree: 100%

---

# INST {#inst}

已安装构件

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_inst_overview"
>title="已安装构件"
>abstract="INST 标识已由客户安装在 AEM 中的自定义及第三方软件包和捆绑包。报告这些内容是为了帮助描述系统的状态和升级工作的一般范围。任何第三方软件包都必须遵守 AEM as a Cloud Service 开发和打包准则。"
>additional-url="https://experienceleague.adobe.com/zh-hans/docs/experience-manager-cloud-service/content/implementing/developing/development-guidelines" text="开发准则 - AEM as a Cloud Service"
>additional-url="https://experienceleague.adobe.com/zh-hans/docs/experience-manager-cloud-service/content/implementing/developing/repository-structure-package" text="打包准则 - AEM as a Cloud Service"

`INST`  标识已由客户安装在 AEM 中的自定义及第三方软件包和捆绑包。报告这些内容是为了帮助描述系统的状态和升级工作的一般范围。

在安装了某个软件包的多个版本时，只报告最新的版本。

软件包和捆绑包不一定针对 AEM as a Cloud Service 进行了优化。对于任何第三方软件包，应该与其创作者或者 Adobe 进行验证以确定与 AEM as a Cloud Service 的兼容性。

子类型用于标识信息的不同类型：

* `custom.bundle`：AEM 中安装了捆绑包。
* `custom.package`：AEM 中安装了软件包。

## 可能产生的后果和风险 {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_inst_guidance"
>title="实施指南"
>abstract="客户无法再使用 CRX 包管理器安装第三方软件包。客户应该审查这些已安装的构件，必须对其进行结构调整和优化以用于 AEM as a Cloud Service。对于任何第三方软件包，应该与其创作者或者 Adobe 进行验证以确定与 AEM as a Cloud Service 的兼容性。"
>additional-url="https://experienceleague.adobe.com/zh-hans/docs/experience-manager-cloud-service/content/implementing/developing/aem-project-content-package-structure#embeddeds" text="在容器软件包中嵌入子包"


* 在 AEM as a Cloud Service 中，无法使用 CRX 包管理器安装第三方软件包。
* 在正确部署以用于 AEM as a Cloud Service 之前，依赖于第三方软件包的应用程序可能无法正常工作。
* 第三方供应商软件包如果未针对 AEM as a Cloud Service 进行优化，可能会导致意外的行为。

## 可采用的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_inst_tools"
>title="工具和资源"
>abstract="审查 WKND 旧版项目，了解如何使 INST 违规与 AEM Cloud Service 兼容。此外，查看 GitHub 上的 INST 违规示例，了解如何在 AEM as a Cloud Service 中更正和部署它。"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/tree/code/inst" text="WKND 旧版项目"
>additional-url="https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/inst" text="INST 违规示例 - GitHub"

* 第三方软件包应该作为项目的一部分，使用 Cloud Manager [部署流程](https://experienceleague.adobe.com/zh-hans/docs/experience-manager-cloud-service/content/implementing/using-cloud-manager/deploy-code#deployment-process)部署到 AEM。
* 请查看如何在项目中为 AEM as a Cloud Service [嵌入第三方软件包](https://experienceleague.adobe.com/zh-hans/docs/experience-manager-cloud-service/content/implementing/developing/aem-project-content-package-structure#embedding-3rd-party-packages)。
* 第三方软件包必须遵守 AEM as a Cloud Service [开发](https://experienceleague.adobe.com/zh-hans/docs/experience-manager-cloud-service/content/implementing/developing/development-guidelines)和[打包](https://experienceleague.adobe.com/zh-hans/docs/experience-manager-cloud-service/content/implementing/developing/repository-structure-package)准则。
* 审查 [wknd 旧版](https://github.com/adobe/aem-guides-wknd-legacy/tree/code/inst)项目，了解如何更正 [INST 违规](https://github.com/adobe/aem-guides-wknd-legacy/compare/main...code/inst)，使其与 AEM as a Cloud Service 兼容。
* 请联系 [AEM 支持团队](https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html) 进行澄清或解决疑惑。
