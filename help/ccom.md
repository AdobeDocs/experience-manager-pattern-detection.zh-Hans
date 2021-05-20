---
title: CCOM
description: 模式检测器代码帮助页
exl-id: 59071538-56ec-44e7-8196-56e6525bb4b9
source-git-commit: 4ad2fe0fa05b8252112df8a94958e65bb882482d
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 6%

---

# CCOM {#ccom}

自定义组件

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ccom_overview"
>title="自定义组件"
>abstract="CCOM标识已在AEM上安装的自定义组件。 此信息的提供是为了最佳做法评估"

`CCOM` 标识已在AEM上安装的自定义组件。此信息的提供是为了最佳做法评估。

子类型与此代码一起使用来标识组件的类别：

* `custom.core`:组件超类型链中的超类型包含“core/wcm/components/”，表示该超类型继承自核心组件。
* `custom.foundation`:组件超类型链中的超类型包含“core/wcm/components/”，表示该超类型继承自核心组件。
* `custom.overlay.foundation`:组件路径包含“wcm/foundation/components/”或“foundation/components/”，表示该路径覆盖了基础组件。
* `custom`:自定义组件不会继承或叠加核心组件或基础组件。

## 可能的影响和风险{#implications-and-risks}

* 最佳实践是最大限度地减少自定义组件的数量，利用核心组件，并将核心组件与样式系统结合使用以减少技术负担。

## 可能的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ccom_guidance"
>title="实施指南"
>abstract="最佳实践是最大限度地减少自定义组件的数量，利用核心组件，并将核心组件与样式系统结合使用以减少技术负担。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-core-components/using/introduction.html" text="核心组件"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-learn/sites/page-authoring/style-system-feature-video-use.html?lang=en#page-authoring" text="样式系统"

* 有关核心组件的更多信息，请参阅[核心组件简介](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/introduction.html?lang=zh-Hans)。
* 在[使用样式系统](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/page-authoring/style-system-feature-video-use.html?lang=en#page-authoring)中查找有关样式系统的详细信息。
* 请联系我们的[AEM支持团队](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以获得说明或解决问题。
