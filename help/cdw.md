---
title: CDW
description: Pattern Detector 代码帮助页面
source-git-commit: 04709ba74eedad903669aae589c605542e1e3b09
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 44%

---

# CDW {#cdw}

自定义对话框小组件

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cdw_overview"
>title="自定义对话框小组件"
>abstract="CDW标识了自定义对话框小组件，该小组件应进行更新，以便与AEMas a Cloud Service兼容。"

`CDW`  自定义对话框小组件可标识自定义CoralUI和经典对话框小组件。 应更新这些参数，以便与AEMas a Cloud Service兼容。

子类型用于标识信息的不同类型，例如：

* `custom.coral.widget`:识别基于CoralUI 2或CoralUI 3的自定义对话框小组件。
* `custom.classic.widget`:识别基于ExtJs的自定义对话框小组件。

## 可能的后果和风险 {#implications-and-risks}

* 经典 UI 在 AEM as a Cloud Service 中不再可用。用于创作的标准界面是支持触摸的 UI。

## 可采用的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_cdw_guidance"
>title="实施指南"
>abstract="联系客户关怀部门寻求帮助。"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支持"

* 自定义经典对话框小组件应从ExtJS转换为 [CoralUI](https://developer.adobe.com/experience-manager/reference-materials/6-5/coral-ui/coralui3/getting-started.html).
* 应评估自定义Coral对话框小组件，以更新到CoralUI 3。
* 请联系我们的 [Experience Manager 客户关怀团队](https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html)获取说明或解决问题。
