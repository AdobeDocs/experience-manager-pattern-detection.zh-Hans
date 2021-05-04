---
title: DM
description: 图案检测器代码帮助页
exl-id: f077df57-f2bc-4875-a7de-41251a9d7f2f
translation-type: tm+mt
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
>abstract="DM代码标识AEM Assets Dynamic Media在当前实施中的使用。 Dynamic Media模式由运行模式检测。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/developing/introduction/dev-guidelines-bestpractices.html" text="AEM开发 — 准则和最佳实践"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html" text="AEM as a Cloud Service 开发准则"

`DM` 标识AEM Assets Dynamic Media的使用。Dynamic Media模式由运行模式检测。

子类型与以下代码一起使用：

* `dynamic.media.runmode`:提供此子类型的关联值为：
   * `dynamicmedia`:Dynamic Media — 混合模式
   * `dynamicmedia_scene7`:Dynamic Media - Scene 7模式

## 可能的影响和风险{#implications-and-risks}

* `dynamic.media.runmode`
   * 可能存在与Dynamic Media相关的升级问题。

## 可能的解决方案{#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dm_guidance"
>title="实施指南"
>abstract="AEM作为Cloud Service仅支持dynamicmedia_scene7运行模式。 请查看当前设置并联系Adobe支持团队寻求帮助和说明。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/dynamicmedia/administering-dynamic-media.html" text="设置 Dynamic Media"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud支持"


* `dynamic.media.runmode`
   * 有关详细信息，请访问[设置Dynamic Media](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/dynamicmedia/administering-dynamic-media.html)。

* 请联系我们的[AEM支持团队](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以获得说明或解决问题。
