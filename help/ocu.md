---
title: OCU
description: 图案检测器代码帮助页
exl-id: cb28c727-415d-436c-ab74-cf7f1f34f7c7
translation-type: tm+mt
source-git-commit: 76dc944f1592118920f89c513faf456b8aa443a9
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 0%

---

# OCU {#ocu}

代码使用过时

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ocu_overview"
>title="代码使用过时"
>abstract="OCU标识某些JCR节点(如Sling或AEM组件或API OSGi导出)以不兼容方式更改或删除的情况。 在升级前，客户可能不知道此更改。 它们可能已升级到不兼容版本，或者根本不可用。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html" text="显着变化 — AEM作为Cloud Service"

`OCU` 标识某些JCR节点(如Sling或AEM组件或API OSGi导出)以不兼容方式更改或删除的情况。在升级前，客户可能不知道此更改。 它们可能已升级到不兼容版本，或者根本不可用。

由于默认情况下未安装旧版本，因此客户应用程序可能无法正常工作。

## 可能的影响和风险{#implications-and-risks}

* 依赖于使用已弃用的组件或API的任何组件的功能可能会中断，并且在升级后可能无法正确解析。
* 客户应用程序的某些功能或某些AEM功能可能无法正常工作，或在升级后可能不处于活动状态。

## 可能的解决方案{#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ocu_guidance"
>title="实施指南"
>abstract="最佳实践是审阅并调整客户代码，以使用最新版AEM组件或API。 联系Adobe支持以获得帮助和说明。"
>additional-url="https://javadoc.io/doc/com.adobe.aem/aem-sdk-api/latest/index.html" text="Adobe Experience Manager SDK API"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud支持"

* 短期：安装兼容性包可能会有所帮助。
* 长期：调整客户代码以使用最新版AEM组件或API。
* 请联系我们的[AEM支持团队](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以获得说明或解决问题。
