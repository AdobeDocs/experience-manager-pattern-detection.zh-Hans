---
title: DM
description: 模式检测器代码帮助页
exl-id: f077df57-f2bc-4875-a7de-41251a9d7f2f
source-git-commit: 54b121a6ec29ba6ff6fb33b402f1821c34d0763f
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 7%

---

# DM {#dm}

Dynamic Media

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dm_overview"
>title="Dynamic Media"
>abstract="DM代码可识别AEM Assets Dynamic Media在当前实施中的使用情况。 运行模式会检测到Dynamic Media模式。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/developing/introduction/dev-guidelines-bestpractices.html" text="AEM开发 — 准则和最佳实践"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html" text="AEM as a Cloud Service 开发准则"

`DM` 标识AEM Assets Dynamic Media的使用。运行模式会检测到Dynamic Media模式。

子类型与以下代码一起使用：

* `dynamic.media.runmode`:如果提供了此子类型的关联值，则其值为：
   * `dynamicmedia`:Dynamic Media — 混合模式
   * `dynamicmedia_scene7`:Dynamic Media - Scene 7模式

## 可能的影响和风险{#implications-and-risks}

* `dynamic.media.runmode`
   * 可能存在与Dynamic Media相关的升级问题。

## 可能的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dm_guidance"
>title="实施指南"
>abstract="AEM as aCloud Service仅支持dynamicmedia_scene7运行模式。 请查看当前设置，并联系Adobe支持团队以获取帮助和说明。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/dynamicmedia/administering-dynamic-media.html" text="设置 Dynamic Media"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud支持"


* `dynamic.media.runmode`
   * 有关更多信息，请参阅[设置Dynamic Media](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/dynamicmedia/administering-dynamic-media.html)。

* 请联系我们的[AEM支持团队](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以获得说明或解决问题。
