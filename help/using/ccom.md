---
title: CCOM
description: Pattern Detector 代码帮助页面。
exl-id: 59071538-56ec-44e7-8196-56e6525bb4b9
source-git-commit: 84c193b66fbf9c41f546e8575a0aa17e94043b9a
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 84%

---

# CCOM {#ccom}

自定义组件

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ccom_overview"
>title="自定义组件"
>abstract="CCOM 标识 AEM 上已安装的自定义组件。提供此类信息是为了进行最佳实践评估"

`CCOM` 标识AEM上已安装的自定义组件。 提供此类信息是为了进行最佳实践评估。

此代码使用了子类型来标识组件的类别：

* `custom.core`：组件的超类型链中的一个超类型包含“core/wcm/components/”，指示它继承自核心组件。
* `custom.foundation`：组件的超类型链中的一个超类型包含“core/wcm/components/”，指示它继承自核心组件。
* `custom.overlay.foundation`：组件路径包含“wcm/foundation/components/”或“foundation/components/”，指示它叠加了基础组件。
* `custom`：自定义组件未继承或叠加核心组件或基础组件。

## 可能产生的后果和风险 {#implications-and-risks}

* 最佳实践为最大限度地减少自定义组件的数量，使用核心组件，并将核心组件与样式系统结合使用，以便您可以减少技术债务。

## 可采用的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ccom_guidance"
>title="实施指南"
>abstract="最佳做法是尽可能减少自定义组件的数量，利用核心组件，并将核心组件与样式系统结合使用来减少技术债务。"
>additional-url="https://experienceleague.adobe.com/zh-hans/docs/experience-manager-core-components/using/introduction" text="核心组件"
>additional-url="https://experienceleague.adobe.com/en/docs/zh-hans/experience-manager-learn/sites/page-authoring/style-system-feature-video-use#page-authoring" text="样式系统"

* 在[核心组件简介](https://experienceleague.adobe.com/zh-hans/docs/experience-manager-core-components/using/introduction)可找到有关核心组件的更多信息。
* 在[使用样式系统](https://experienceleague.adobe.com/en/docs/zh-hans/experience-manager-learn/sites/page-authoring/style-system-feature-video-use#page-authoring)中可查找有关样式系统的更多信息。
* 请联系 [AEM 支持团队](https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html) 进行澄清或解决疑惑。
