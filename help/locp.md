---
title: LOCP
description: 图案检测器代码帮助页
exl-id: a9993b58-7925-47c0-b774-b9ca8a4ee052
translation-type: tm+mt
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
>abstract="LOCP可识别向/libs发送内容的自定义包的检测，该包是反模式（ACL除外）。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/deploying/upgrading/sustainable-upgrades.html" text="可持续升级"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/sling-resource-merger.html#platform" text="Sling Resource Mearge"

`LOCP` 标识将内容发送到的自定义包的 `/libs`检测，这是一种反模式（ACL除外）。

## 可能的影响和风险{#implications-and-risks}

* 对于任何CFP、SP或主要AEM升级，可能会删除或替换客户代码。
* 在某些情况下，新内容可能未正确安装。

## 可能的解决方案{#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_locp_guidance"
>title="实施指南"
>abstract="客户应查看其自定义代码和包，以确定是否将内容交付到/lib，并重新调整它以依赖在/apps下叠加内容并使其作为Cloud Service与AEM兼容。 联系Adobe支持以获得帮助和说明"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/overlays.html#platform" text="叠加"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud支持"

* 客户包应将内容部署到`/apps`，而不是`/libs`。
* 请联系我们的[AEM支持团队](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以获得说明或解决问题。
