---
title: NCC
description: Pattern Detector代码帮助页面。
exl-id: 4a374956-c64e-43fc-8279-ed25f6ed5cb0
source-git-commit: 982ad1a6f43a29f2ee2284219757c8fc11b31ce0
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 91%

---

# NCC {#ncc}

不兼容更改

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ncc_overview"
>title="不兼容更改"
>abstract="NCC 标识的情况是，以不兼容的方式更改了一些 JCR 节点或捆绑包。客户在升级之前可能未注意到这种更改。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html" text="显著更改 - AEM as a Cloud Service"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html" text="发行说明 - AEM as a Cloud Service"

`NCC` 标识的情况是，以不兼容的方式更改了一些 JCR 节点或捆绑包。客户在升级之前可能未注意到这种更改。

## 可能的后果和风险 {#implications-and-risks}

* 依赖于使用不兼容更改的任意组件的功能可能会受损，并且可能无法正确解决。
* 客户应用程序的某些功能或者某些 AEM 功能在升级之后可能无法正确工作。

## 可采用的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ncc_guidance"
>title="实施指南"
>abstract="最佳实践是审核自定义代码并确保仅叠加或引用兼容的 Sling 组件。请联系 Adobe 支持部门获取帮助或说明"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/overlays.html#platform" text="叠加"
>additional-url="https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支持"

* 仅叠加或引用兼容的 Sling 组件。
* 考虑在 AEM 升级后调整来自 `/libs` 或捆绑包的资源。
* 联系 [AEM支持团队](https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html) 以澄清或解决问题。
