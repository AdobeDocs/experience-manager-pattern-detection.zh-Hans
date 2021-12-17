---
title: NCC
description: 模式检测器代码帮助页
source-git-commit: fdc3e8bdef27de971743a9ecb04d3912cf8e60ad
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 3%

---

# NCC {#ncc}

不兼容的更改

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ncc_overview"
>title="不兼容的更改"
>abstract="NCC会根据某些JCR节点或包以不兼容的方式发生更改的情况进行标识。 客户在升级前可能不知道此更改。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html" text="显着更改 — AEMas a Cloud Service"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html?lang=zh-Hans" text="发行说明 — AEMas a Cloud Service"

`NCC` 标识某些JCR节点或包以不兼容方式发生更改的情况。 客户在升级前可能不知道此更改。

## 可能的影响和风险 {#implications-and-risks}

* 依赖于任何使用不兼容更改的组件的功能可能会损坏，并且可能无法正确解析。
* 升级后，客户应用程序的某些功能或某些AEM功能可能无法正常工作。

## 可能的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ncc_guidance"
>title="实施指南"
>abstract="最佳实践是查看自定义代码，并确保仅覆盖或引用兼容的Sling组件。 联系Adobe支持以获取帮助和说明"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/overlays.html#platform" text="叠加"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud支持"

* 仅覆盖或引用兼容的Sling组件。
* 考虑调整来自 `/libs` 或AEM升级后的包。
* 请联系我们的 [AEM支持团队](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) 澄清或解决问题。
