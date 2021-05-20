---
title: 密送
description: 模式检测器代码帮助页
exl-id: fa6bdd3c-4deb-41ec-878d-4ea5dc1ddf60
source-git-commit: 4ad2fe0fa05b8252112df8a94958e65bb882482d
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 3%

---

# 密送 {#nbcc}

不向后兼容的更改

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_nbcc_overview"
>title="不向后兼容的更改"
>abstract="NBCC标识某些JCR节点或包以不兼容方式发生更改的情况。 客户在升级前可能不知道此更改。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html" text="显着更改 — AEM作为Cloud Service"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html?lang=zh-Hans" text="发行说明 — AEM as aCloud Service"

`NBCC` 标识某些JCR节点或包以不兼容方式发生更改的情况。客户在升级前可能不知道此更改。

## 可能的影响和风险{#implications-and-risks}

* 依赖于任何使用不向后兼容更改的组件的功能可能会损坏，并且可能无法正确解析。
* 升级后，客户应用程序的某些功能或某些AEM功能可能无法正常工作。

## 可能的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_nbcc_guidance"
>title="实施指南"
>abstract="最佳实践是查看自定义代码，并确保只覆盖或引用向后兼容的Sling组件。 联系Adobe支持以获取帮助和说明"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/overlays.html#platform" text="叠加"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud支持"

* 仅覆盖或引用向后兼容的Sling组件。
* 请考虑调整AEM升级后`/libs`或包中的资源。
* 请联系我们的[AEM支持团队](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以获得说明或解决问题。
