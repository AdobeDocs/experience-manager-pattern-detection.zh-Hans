---
title: CDW
description: Pattern Detector 代码帮助页面。
exl-id: a9e9dae8-0aa2-4679-a3c1-418cab01cfda
source-git-commit: d1c652a8a45a081661ffe4443f85fcc932947541
workflow-type: tm+mt
source-wordcount: '139'
ht-degree: 100%

---

# CDW {#cdw}

自定义对话框构件

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cdw_overview"
>title="自定义对话框构件"
>abstract="CDW 标识应更新的自定义对话框构件，以使其与 AEM as a Cloud Service 兼容。"

`CDW`  (`Custom Dialog Widgets`) 标识自定义经典对话框构件。应更新这些构件，以使其与 AEM as a Cloud Service 兼容。

子类型用于标识相关信息，例如：

* `custom.classic.widget`：标识基于 ExtJ 的自定义对话框构件。

## 可能产生的后果和风险 {#implications-and-risks}

* 经典 UI 在 AEM as a Cloud Service 中不再可用。用于创作的标准界面是支持触摸的 UI。

## 可采用的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cdw_guidance"
>title="实施指南"
>abstract="联系客户关怀部门寻求帮助。"
>additional-url="https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支持"

* 应将自定义 Classic 对话框构件从 ExtJS 转换为 [CoralUI](https://developer.adobe.com/experience-manager/reference-materials/6-5/coral-ui/coralui3/getting-started.html)。
* 请联系我们的 [Experience Manager 客户服务团队](https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html)进行澄清或解决疑惑。
