---
title: CTEM
description: 图案检测器代码帮助页
exl-id: cd70486c-8e21-4c31-89bf-928b80fa8772
translation-type: tm+mt
source-git-commit: 4ad2fe0fa05b8252112df8a94958e65bb882482d
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 5%

---

# CTEM {#ctem}

自定义模板

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ctem_overview"
>title="自定义模板"
>abstract="CTEM标识已安装在AEM上的自定义组件。 提供此信息是为了进行最佳做法评估"

`CTEM` 标识已安装在AEM上的自定义模板。提供此信息是为了进行最佳做法评估。

模板由主类型值“cq:Template”标识。 子类型与此代码一起使用，以标识模板的类别:

* `custom.editable.template`:模板的路径不与“/apps”开始。
* `custom.static.template`:具有“/apps”的模板开始的路径。

## 可能的影响和风险{#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ctem_guidance"
>title="实施指南"
>abstract="最佳实践是将所有静态模板移动到可编辑的模板。 客户可以利用现有的AEM现代化工具将静态模板迁移到可编辑模板。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/templates/templates.html" text="可编辑的模板"
>additional-url="https://opensource.adobe.com/aem-modernize-tools/" text="AEM 现代化工具"

* 最佳实践是将所有静态模板移动到可编辑的模板。

## 可能的解决方案{#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ctem_tools"
>title="工具和资源"
>abstract="借助AEM Moderization Suite，客户可以处理页面结构（从静态定义到可编辑模板）。 其目的是帮助客户从传统功能的有限功能转向强大的现代AEM产品。 这些工具可配置、可感知配置且可扩展。 联系Adobe支持以获得帮助和说明"
>additional-url="https://opensource.adobe.com/aem-modernize-tools/pages/tools/page-structure.html" text="页面结构转换器"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud支持"

* 利用[AEM Moderization Tools](https://opensource.adobe.com/aem-modernize-tools/)将静态模板迁移到可编辑模板。
* 在[Templates](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/templates/templates.html)中查找有关可编辑模板的更多信息。
* 请联系我们的[AEM支持团队](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以获得说明或解决问题。
