---
title: DM
description: Pattern Detector 代码帮助页面
exl-id: f077df57-f2bc-4875-a7de-41251a9d7f2f
source-git-commit: f1e833bea35ef3b412936d529b14bff6f1cb35c1
workflow-type: ht
source-wordcount: '201'
ht-degree: 100%

---

# DM {#dm}

Dynamic Media

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dm_overview"
>title="Dynamic Media"
>abstract="DM 代码标识在您当前实现中 AEM Assets Dynamic Media 的使用。Dynamic Media 模式由运行模式检测。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/developing/introduction/dev-guidelines-bestpractices.html" text="AEM 开发 - 准则和最佳实践"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html" text="AEM as a Cloud Service 开发准则"

`DM` 标识使用 AEM Assets Dynamic Media。Dynamic Media 模式由运行模式检测。

此代码使用了一个子类型：

* `dynamic.media.runmode`：此子类型的关联值，如果提供，可以为：
   * `dynamicmedia`：Dynamic Media - 混合模式
   * `dynamicmedia_scene7`：Dynamic Media - 场景 7 模式

## 可能的后果和风险 {#implications-and-risks}

* `dynamic.media.runmode`
   * 可能会有与 Dynamic Media 相关的升级问题。

## 可采用的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_dm_guidance"
>title="实施指南"
>abstract="AEM as a Cloud Service 仅支持 dynamicmedia_scene7 运行模式。请查看当前设置并联系 Adobe 支持团队获取帮助和说明。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/dynamicmedia/administering-dynamic-media.html" text="设置 Dynamic Media"
>additional-url="https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支持"


* `dynamic.media.runmode`
   * 在[设置 Dynamic Media](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/dynamicmedia/administering-dynamic-media.html) 中查找更多信息。

* 请联系我们的 [AEM 支持团队](https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html)获取说明或解决问题。
