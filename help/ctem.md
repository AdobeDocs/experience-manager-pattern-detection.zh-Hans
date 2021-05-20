---
title: CTEM
description: 模式检测器代码帮助页
exl-id: cd70486c-8e21-4c31-89bf-928b80fa8772
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
>abstract="CTEM可识别已在AEM上安装的自定义组件。 此信息的提供是为了最佳做法评估"

`CTEM` 标识已在AEM上安装的自定义模板。此信息的提供是为了最佳做法评估。

模板由“cq:Template”的主类型值标识。 子类型与此代码一起使用来标识模板的类别：

* `custom.editable.template`:模板的路径不以“/apps”开头。
* `custom.static.template`:模板的路径以“/apps”开头。

## 可能的影响和风险{#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ctem_guidance"
>title="实施指南"
>abstract="最佳实践是将所有静态模板移动到可编辑的模板。 客户可以利用现有的AEM现代化工具将静态模板迁移到可编辑的模板。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/templates/templates.html" text="可编辑的模板"
>additional-url="https://opensource.adobe.com/aem-modernize-tools/" text="AEM 现代化工具"

* 最佳实践是将所有静态模板移动到可编辑的模板。

## 可能的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ctem_tools"
>title="工具和资源"
>abstract="借助AEM现代化套件，客户可以处理页面结构，从静态定义到可编辑的模板。 其目的在于帮助客户从旧版功能有限的功能转变为强大的现代AEM产品。 这些工具具有可配置、可感知配置和可扩展性。 联系Adobe支持以获取帮助和说明"
>additional-url="https://opensource.adobe.com/aem-modernize-tools/pages/tools/page-structure.html" text="页面结构转换器"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud支持"

* 利用[AEM现代化工具](https://opensource.adobe.com/aem-modernize-tools/)将静态模板迁移到可编辑的模板。
* 有关可编辑模板的更多信息，请访问[模板](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/templates/templates.html)。
* 请联系我们的[AEM支持团队](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以获得说明或解决问题。
