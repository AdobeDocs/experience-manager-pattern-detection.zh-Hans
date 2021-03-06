---
title: CTEM
description: Pattern Detector 代码帮助页面
exl-id: cd70486c-8e21-4c31-89bf-928b80fa8772
source-git-commit: 9a993a5cf078e5bc61cb5d314d2a15abcbd33f2a
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 95%

---

# CTEM {#ctem}

自定义模板

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ctem_overview"
>title="自定义模板"
>abstract="CTEM 标识 AEM 上已安装的自定义组件。提供此类信息是为了进行最佳实践评估"

`CTEM` 标识 AEM 上已安装的自定义模板。提供此类信息是为了进行最佳实践评估。

模板由主要类型值“cq:Template”标识。此代码使用了子类型来标识模板的类别：

* `custom.editable.template`：模板的路径并非以“/apps”开头。
* `custom.static.template`：模板的路径以“/apps”开头。

## 可能的后果和风险 {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ctem_guidance"
>title="实施指南"
>abstract="将所有静态模板迁移到可编辑模板的最佳实践。客户可以利用现有 AEM 现代化工具将静态模板迁移到可编辑模板。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/templates/templates.html" text="可编辑模板"
>additional-url="https://opensource.adobe.com/aem-modernize-tools/" text="AEM 现代化工具"

* 将所有静态模板迁移到可编辑模板的最佳实践。

## 可采用的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ctem_tools"
>title="工具和资源"
>abstract="利用 AEM 现代化套件的帮助，客户可以操作页面的结构，从静态定义更改为可编辑模板。其目的是为了帮助客户从旧版有限的功能迁移到可靠的现代化 AEM 方案。这些工具是可配置的、可感知配置的和可扩展的。 请联系 Adobe 支持部门获取帮助或说明"
>additional-url="https://opensource.adobe.com/aem-modernize-tools/pages/structure/about.html" text="页面结构转换器"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支持"

* 利用 [AEM 现代化工具](https://opensource.adobe.com/aem-modernize-tools/)将静态模板迁移到可编辑模板。
* 在[模板](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/templates/templates.html)中可查找有关可编辑模板的更多信息。
* 请联系我们的 [AEM 支持团队](https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html)获取说明或解决问题。
