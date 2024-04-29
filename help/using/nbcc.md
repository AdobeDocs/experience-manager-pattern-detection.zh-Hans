---
title: NBCC
description: Pattern Detector 代码帮助页面。
exl-id: fa6bdd3c-4deb-41ec-878d-4ea5dc1ddf60
source-git-commit: 84c193b66fbf9c41f546e8575a0aa17e94043b9a
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 88%

---

# NBCC {#nbcc}

已弃用：不向后兼容的更改（取代为 NCC，即不兼容更改）

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_nbcc_overview"
>title="不向后兼容的更改"
>abstract="NBCC 标识的情况是，以不兼容的方式更改了一些 JCR 节点或捆绑包。在升级之前，客户可能没有意识到这一变化。"
>additional-url="https://experienceleague.adobe.com/zh-hans/docs/experience-manager-cloud-service/content/release-notes/aem-cloud-changes" text="显著更改 - AEM as a Cloud Service"
>additional-url="https://experienceleague.adobe.com/zh-hans/docs/experience-manager-cloud-service/content/release-notes/release-notes/release-notes-current" text="发行说明 - AEM as a Cloud Service"

`NBCC`  标识的情况是，以不兼容的方式更改了一些JCR节点或捆绑包。 在升级之前，客户可能没有意识到这一变化。

## 可能产生的后果和风险 {#implications-and-risks}

* 依赖于使用不向后兼容更改的任意组件的功能可能会受损，并且可能无法正确解决。
* 客户应用程序的某些功能或者某些 AEM 功能在升级之后可能无法正确工作。

## 可采用的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_nbcc_guidance"
>title="实施指南"
>abstract="最佳做法是审核自定义代码并确保只叠加或引用向后兼容的 Sling 组件。联系 Adobe 支持获取帮助或说明。"
>additional-url="https://experienceleague.adobe.com/en/docs/zh-hans/experience-manager-65/content/implementing/developing/platform/overlays#platform" text="叠加"
>additional-url="https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支持"

* 仅叠加或引用向后兼容的Sling组件。
* 考虑在 AEM 升级后调整来自 `/libs` 或捆绑包的资源。
* 请联系 [AEM 支持团队](https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html) 进行澄清或解决疑惑。
