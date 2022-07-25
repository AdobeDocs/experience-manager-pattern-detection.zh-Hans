---
title: LUI
description: Pattern Detector 代码帮助页面
exl-id: 742220d6-b37a-48ec-9f89-2f3f0ce6ff96
source-git-commit: 1c2d064c239ad6f5599678d8057fe2a6b7fd8d01
workflow-type: tm+mt
source-wordcount: '703'
ht-degree: 98%

---

# 吕 {#lui}

旧版用户界面

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_lui_overview"
>title="旧版用户界面"
>abstract="LUI 标识使用了已弃用的用户界面元素，而更高版本的 AEM 和 AEM as a Cloud Service 中不推荐使用或者不支持这些元素。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html" text="显著更改 - AEM as a Cloud Service"

`LUI` 标识使用了已弃用的用户界面元素，而更高版本的 AEM 和 AEM as a Cloud Service 中不推荐使用或者不支持这些元素。

子类型用于标识应该或必须升级的不同类型用户界面元素：

* `legacy.dialog.classic`：基于 ExtJS 的经典 UI 对话框必须改为 Coral。
   * 当对话框的名称为“dialog”或“design_dialog”并且
`jcr:primaryType` 属性值或 `xtype` 属性值为“cq:Dialog”时会检测到此情况。
* `legacy.dialog.coral2`：Coral 2 对话框应更新为使用 Coral 3。
   * 当对话框及其子内容节点名称为“cq:dialog/content”、
“cq:design_dialog/content”、“cq:dialog.coral2/content”或“cq:design_dialog.coral2/content”
并且 `sling:resourceType` 属性值不包含
“granite/ui/components/coral/foundation”时会检测到此情况。
* `legacy.custom.component`：继承自 `foundation/components` 的组件应该更新以使用核心组件。
   * 当 `jcr:primaryType` 属性值为“cq:Component”并且
      `sling:resourceSuperType` 属性值包含“foundation/components”或者任意
      超类型链组件的 `sling:resourceSuperType` 属性值包含
“foundation/components”时会检测到此情况。
* `legacy.static.template`：静态模板应该升级为可编辑模板。
   * 当 `jcr:primaryType` 属性值为“cq:Template”时会检测到此情况。
* `content.fragment.template`：内容片段模板应创建片段模型以替换片段模板。
   * 内容片段模板可在以下位置找到：
      * 现成的内容片段模板存储在 `/libs/settings/dam/cfm/templates` 中
      * 它们可以在 `/apps/settings/dam/cfm/templates` 或 `/conf/.../settings/dam/cfm/templates`（... = global 或 &quot;tenant&quot;）中覆盖

## 可能的后果和风险 {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_lui_guidance"
>title="实施指南"
>abstract="经典 UI 在 AEM as a Cloud Service 中不再可用，用于创作的标准界面为支持触摸的 UI。最佳实践是移除所有不支持的界面，链接的定制设置应重构为与 AEM as a Cloud Service 兼容的更新特性/功能。客户可以利用现有 AEM 现代化套件来帮助减少打造现代化 AEM Sites 实现所需的工作。"
>additional-url="https://opensource.adobe.com/aem-modernize-tools/" text="AEM 现代化工具"

* 经典 UI 在 AEM as a Cloud Service 中不再可用。用于创作的标准界面是支持触摸的 UI。
* 从长期来看，依靠旧版自定义组件会增加维护成本。
* 在 AEM 6.3 中，内容片段模型取代了内容片段模板。将基于旧模板的内容片段迁移到 AEM as a Cloud Service 后，这些片段仍然可用，但无法基于旧模板创建新的片段。同时也无法使用 AEM GraphQL 提供这些片段，它需要内容片段模型作为架构。

## 可采用的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_lui_tools"
>title="工具和资源"
>abstract="在 AEM 现代化套件的帮助下，客户可以从经典 (ExtJS) 对话框转为 Coral 对话框。其目的是为了帮助客户从不支持的功能或旧版功能迁移到可靠的现代化 AEM 方案。这些工具是可配置的、可感知配置的和可扩展的。 此外，可以探索使用一组标准化核心组件替换自定义组件，以加快应用程序的开发速度并减少维护成本。"
>additional-url="https://opensource.adobe.com/aem-modernize-tools/pages/component/about.html" text="组件转换器"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-core-components/using/introduction.html" text="核心组件"

* 利用 [AEM 现代化工具套件](https://opensource.adobe.com/aem-modernize-tools/)减少打造现代化 AEM Sites 实现所需的工作。这些工具包括以下转化：
   * 经典 (ExtJS) 对话框到 Coral 对话框
   * 基础组件到核心组件
   * 静态模板和列控件到可编辑模板和响应式网格
   * 设计和设计对话框到可编辑模板策略
* 审查项目的自定义组件库，如果可能，请转换为一组标准化[核心组件](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/introduction.html?lang=zh-Hans)，以加快应用程序的开发速度并减少维护成本。
* 推荐使用与旧模板等同的功能创建内容片段模型，并在以后使用这些模型创建内容片段。有关详细信息，请参阅[内容片段模型](https://experienceleague.adobe.com/docs/experience-manager-65/assets/content-fragments/content-fragments-models.html?lang=zh-Hans)。
* 请联系我们的 [AEM 支持团队](https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html)获取说明或解决问题。
