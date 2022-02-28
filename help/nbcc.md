---
title: NBCC
description: Pattern Detector 代码帮助页面
exl-id: fa6bdd3c-4deb-41ec-878d-4ea5dc1ddf60
source-git-commit: fdc3e8bdef27de971743a9ecb04d3912cf8e60ad
workflow-type: ht
source-wordcount: '233'
ht-degree: 100%

---

# NBCC {#nbcc}

已弃用：不向后兼容的更改（取代为 NCC，即不兼容更改）

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_nbcc_overview"
>title="不向后兼容的更改"
>abstract="NBCC 标识的情况是，以不兼容的方式更改了一些 JCR 节点或捆绑包。客户在升级之前可能未注意到这种更改。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html" text="显著更改 - AEM as a Cloud Service"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html" text="发行说明 - AEM as a Cloud Service"

`NBCC` 标识的情况是，以不兼容的方式更改了一些 JCR 节点或捆绑包。客户在升级之前可能未注意到这种更改。

## 可能的后果和风险 {#implications-and-risks}

* 依赖于使用不向后兼容更改的任意组件的功能可能会受损，并且可能无法正确解决。
* 客户应用程序的某些功能或者某些 AEM 功能在升级之后可能无法正确工作。

## 可采用的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_nbcc_guidance"
>title="实施指南"
>abstract="最佳实践是审核自定义代码并确保仅叠加或引用向后兼容的 Sling 组件。请联系 Adobe 支持部门获取帮助或说明"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/overlays.html#platform" text="叠加"
>additional-url="https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支持"

* 仅叠加或引用向后兼容的 Sling 组件。
* 考虑在 AEM 升级后调整来自 `/libs` 或捆绑包的资源。
* 请联系我们的 [AEM 支持团队](https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html)获取说明或解决问题。
