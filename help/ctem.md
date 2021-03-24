---
title: CTEM
description: 图案检测器代码帮助页
translation-type: tm+mt
source-git-commit: a2c7137dd5cb2479bc0c6134d3afa58111049a68
workflow-type: tm+mt
source-wordcount: '140'
ht-degree: 4%

---


# CTEM {#ctem}

自定义模板

## 背景 {#background}

`CTEM` 标识已安装在AEM上的自定义模板。提供此信息是为了进行最佳做法评估。

模板由主类型值“cq:Template”标识。 子类型与此代码一起使用，以标识模板的类别:

* `custom.editable.template`:模板的路径不与“/apps”开始。
* `custom.static.template`:具有“/apps”的模板开始的路径。

## 可能的影响和风险{#implications-and-risks}

* 最佳实践是将所有静态模板移动到可编辑的模板。

## 可能的解决方案{#solutions}

* 利用[AEM Moderization Tools](https://opensource.adobe.com/aem-modernize-tools/)将静态模板迁移到可编辑模板。
* 在[Templates](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/templates/templates.html)中查找有关可编辑模板的更多信息。
* 请联系我们的[AEM支持团队](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以获得说明或解决问题。
