---
title: DM
description: 了解模式检测器代码如何识别AEM Assets - Dynamic Media的使用。
exl-id: f077df57-f2bc-4875-a7de-41251a9d7f2f
source-git-commit: 84c193b66fbf9c41f546e8575a0aa17e94043b9a
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 52%

---

# DM {#dm}

Dynamic Media

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dm_overview"
>title="Dynamic Media"
>abstract="DM 代码标识在您当前实现中 AEM Assets Dynamic Media 的使用。Dynamic Media 模式由运行模式检测。"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/developing/introduction/dev-guidelines-bestpractices" text="AEM 开发 - 准则和最佳实践"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/implementing/developing/development-guidelines" text="AEM as a Cloud Service 开发准则"

`DM` (Dynamic Media)标识使用AEM Assets Dynamic Media。 Dynamic Media模式由运行模式检测。

此代码使用了一个子类型：

* `dynamic.media.runmode`：此子类型的关联值，如果提供，可以为：
   * `dynamicmedia`：Dynamic Media - 混合模式
   * `dynamicmedia_scene7`：Dynamic Media - Scene7模式

## 可能的后果和风险 {#implications-and-risks}

* `dynamic.media.runmode`
   * 可能会有与 Dynamic Media 相关的升级问题。

## 可采用的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dm_guidance"
>title="实施指南"
>abstract="AEMas a Cloud Service仅支持dynamicmedia_scene7运行模式。 查看当前设置并联系Adobe支持团队寻求帮助或说明。"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/assets/dynamicmedia/administering-dynamic-media" text="设置 Dynamic Media"
>additional-url="https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支持"


* `dynamic.media.runmode`
   * 欲知更多信息，请访问 [设置Dynamic Media](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/assets/dynamicmedia/administering-dynamic-media).

* 联系 [AEM支持团队](https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html) 如果您需要澄清或解决问题，请执行以下操作：
