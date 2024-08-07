---
title: CTEM
description: Pattern Detector 代码帮助页面。
exl-id: cd70486c-8e21-4c31-89bf-928b80fa8772
source-git-commit: 58fdb55e1f0c067dacf6825c4076465bc8c5d821
workflow-type: tm+mt
source-wordcount: '247'
ht-degree: 100%

---

# CTEM {#ctem}

自定义模板

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ctem_overview"
>title="自定义模板"
>abstract="CTEM 标识在 AEM 上安装的自定义组件。提供此类信息是为了进行最佳实践评估"

`CTEM`标识在 AEM 上安装的自定义模板。提供此类信息是为了进行最佳实践评估。

模板的主要类型值为 `cq:Template`，这有助于标识它们。此代码使用了子类型来标识模板的类别：

* `custom.editable.template`：模板的路径并非以 `/apps` 开头。
* `custom.static.template`：模板的路径以 `/apps` 开头。

## 可能产生的后果和风险 {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ctem_guidance"
>title="实施指南"
>abstract="最佳实践是将所有静态模板迁移到可编辑模板。客户可以利用现有 AEM 现代化工具将静态模板迁移到可编辑模板。"
>additional-url="https://experienceleague.adobe.com/zh-hans/docs/experience-manager-65/content/implementing/developing/platform/templates/templates" text="可编辑模板"
>additional-url="https://opensource.adobe.com/aem-modernize-tools/" text="AEM 现代化工具"

* 最佳实践是将所有静态模板迁移到可编辑模板。

## 可采用的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ctem_tools"
>title="工具和资源"
>abstract="利用 AEM 现代化套件的帮助，客户可以操作页面的结构，从静态定义更改为可编辑模板。其目的是为了帮助客户从旧版有限的功能迁移到可靠的现代化 AEM 方案。这些工具可配置、可以感知配置且可扩展。联系 Adobe 支持获取帮助或说明。"
>additional-url="https://opensource.adobe.com/aem-modernize-tools/pages/structure/about.html" text="页面结构转换器"
>additional-url="https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支持"

* 使用 [AEM 现代化工具](https://opensource.adobe.com/aem-modernize-tools/)将静态模板迁移到可编辑模板。
* 在[模板](https://experienceleague.adobe.com/zh-hans/docs/experience-manager-65/content/implementing/developing/platform/templates/templates)中可查找有关可编辑模板的更多信息。
* 请联系 [AEM 支持团队](https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html) 进行澄清或解决疑惑。
