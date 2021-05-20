---
title: LOCP
description: 模式检测器代码帮助页
exl-id: a9993b58-7925-47c0-b774-b9ca8a4ee052
source-git-commit: 54b121a6ec29ba6ff6fb33b402f1821c34d0763f
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 0%

---

# LOCP {#locp}

/libs覆盖自定义包

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_locp_overview"
>title="/libs覆盖自定义包"
>abstract="LOCP可识别将内容传送到/libs的自定义包的检测，这是一种反模式（ACL除外）。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/deploying/upgrading/sustainable-upgrades.html" text="可持续升级"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/sling-resource-merger.html#platform" text="Sling资源合并器"

`LOCP` 标识将内容交付到的自定义包 `/libs`的检测，这是一种反模式（ACL除外）。

## 可能的影响和风险{#implications-and-risks}

* 对于任何CFP、SP或主要AEM升级，都可能会删除或替换客户代码。
* 在某些情况下，新内容可能无法正确安装。

## 可能的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_locp_guidance"
>title="实施指南"
>abstract="客户应查看其自定义代码和包，以确定内容是否已交付到/libs，并重构它以依赖于/apps下的叠加内容，使其与AEM as a Cloud Service兼容。 联系Adobe支持以获取帮助和说明"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/overlays.html#platform" text="叠加"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud支持"

* 客户包应将内容部署到`/apps`，而不是`/libs`。
* 请联系我们的[AEM支持团队](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以获得说明或解决问题。
