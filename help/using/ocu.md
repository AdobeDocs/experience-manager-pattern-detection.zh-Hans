---
title: OCU
description: Pattern Detector 代码帮助页面。
exl-id: cb28c727-415d-436c-ab74-cf7f1f34f7c7
source-git-commit: 84c193b66fbf9c41f546e8575a0aa17e94043b9a
workflow-type: ht
source-wordcount: '277'
ht-degree: 100%

---

# OCU {#ocu}

已弃用：过时代码使用（替换为 OU，即过时使用）

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ocu_overview"
>title="过时代码使用"
>abstract="OCU 标识的情况是，以不兼容的方式更改或删除了一些 JCR 节点，例如 Sling 或 AEM 组件或者 API OSGi 导出。在升级之前，客户可能没有意识到这一变化。它们可能会升级到不兼容版本或者完全不可用。"
>additional-url="https://experienceleague.adobe.com/zh-hans/docs/experience-manager-cloud-service/content/release-notes/aem-cloud-changes" text="显著更改 - AEM as a Cloud Service"

`OCU`  标识某些 JCR 节点（如 Sling 或 AEM 组件或 API OSGi 导出）以不兼容的方式更改或删除的情况。在升级之前，客户可能没有意识到这一变化。它们可能会升级到不兼容版本或者完全不可用。

由于默认情况下未安装旧版本，客户应用程序可能无法正常工作。

## 可能产生的后果和风险 {#implications-and-risks}

* 依赖于使用已弃用组件或 API 的任意组件的功能可能会受损，并且在升级后可能无法正确解决。
* 客户应用程序的某些功能或者某些 AEM 功能在升级之后可能无法正确工作或者不活动。

## 可采用的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ocu_guidance"
>title="实施指南"
>abstract="最佳实践是审查并调整客户的代码，使用 AEM 组件或 API 的最新版本。联系 Adobe 支持获取帮助或说明。"
>additional-url="https://javadoc.io/doc/com.adobe.aem/aem-sdk-api/latest/index.html" text="Adobe Experience Manager SDK API"
>additional-url="https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支持"

* 短期：安装兼容性包可能会有帮助。
* 长期：调整客户的代码，使用 AEM 组件或 API 的最新版本。
* 请联系 [AEM 支持团队](https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html) 进行澄清或解决疑惑。
