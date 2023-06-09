---
title: OU
description: Pattern Detector 代码帮助页面
exl-id: 6ec96fab-dd6e-46af-864f-05dad387cbb6
source-git-commit: f1e833bea35ef3b412936d529b14bff6f1cb35c1
workflow-type: ht
source-wordcount: '290'
ht-degree: 100%

---

# OU {#ou}

过时使用

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ou_overview"
>title="过时使用"
>abstract="OU 标识的情况是，以不兼容的方式更改或删除了一些 JCR 节点，例如 Sling 或 AEM 组件或者 API OSGi 导出。客户在升级之前可能未注意到这种更改。它们可能会升级到不兼容版本或者完全不可用。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html" text="显著更改 - AEM as a Cloud Service"

`OU` 标识的情况是，以不兼容的方式更改或删除了一些 JCR 节点，例如 Sling 或 AEM 组件或者 API OSGi 导出。客户在升级之前可能未注意到这种更改。它们可能会升级到不兼容版本或者完全不可用。

由于默认情况下未安装旧版本，客户应用程序可能无法正常工作。

## 可能的后果和风险 {#implications-and-risks}

* 依赖于使用已弃用组件或 API 的任意组件的功能可能会受损，并且在升级后可能无法正确解决。
* 客户应用程序的某些功能或者某些 AEM 功能在升级之后可能无法正确工作或者不活动。

## 可采用的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ou_guidance"
>title="实施指南"
>abstract="最佳实践是审查并调整客户的代码，使用 AEM 组件或 API 的最新版本。请联系 Adobe 支持部门获取帮助或说明。"
>additional-url="https://javadoc.io/doc/com.adobe.aem/aem-sdk-api/latest/index.html" text="Adobe Experience Manager SDK API"
>additional-url="https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支持"

* 短期：安装兼容性包可能会有帮助。
* 长期：调整客户的代码，使用 AEM 组件或 API 的最新版本。
* 请联系我们的 [AEM 支持团队](https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html)获取说明或解决问题。
