---
title: LOCP
description: Pattern Detector 代码帮助页面
exl-id: a9993b58-7925-47c0-b774-b9ca8a4ee052
source-git-commit: 54b121a6ec29ba6ff6fb33b402f1821c34d0763f
workflow-type: ht
source-wordcount: '203'
ht-degree: 100%

---

# LOCP {#locp}

/libs 覆盖自定义软件包

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_locp_overview"
>title="/libs 覆盖自定义软件包"
>abstract="LOCP 标识检测到向 /libs 提供内容的自定义软件包，这是一种反模式（除了在 ACL 的情况下）。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/deploying/upgrading/sustainable-upgrades.html" text="可持续升级"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/sling-resource-merger.html#platform" text="Sling 资源管理器"

`LOCP` 标识检测到向 `/libs` 提供内容的自定义软件包，这是一种反模式（除了在 ACL 的情况下）。

## 可能的后果和风险 {#implications-and-risks}

* 对于任何 CFP、SP 或主要版本的 AEM 升级，可能会删除或替换客户代码。
* 在某些情况下，可能无法正确安装新内容。

## 可采用的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_locp_guidance"
>title="实施指南"
>abstract="客户应该审查其自定义代码和软件包，标识是否向 /libs 提供内容，并重构它们来依靠叠加 /apps 下的内容，使其与 AEM as a Cloud Service 兼容。请联系 Adobe 支持部门获取帮助或说明"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/overlays.html#platform" text="叠加"
>additional-url="https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支持"

* 客户软件包应部署内容到 `/apps` 而不是 `/libs`。
* 请联系我们的 [AEM 支持团队](https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html)获取说明或解决问题。
