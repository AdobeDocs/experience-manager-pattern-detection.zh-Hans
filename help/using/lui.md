---
title: LUI
description: Pattern Detector代码帮助页面。
exl-id: 742220d6-b37a-48ec-9f89-2f3f0ce6ff96
source-git-commit: 982ad1a6f43a29f2ee2284219757c8fc11b31ce0
workflow-type: tm+mt
source-wordcount: '704'
ht-degree: 58%

---

# LUI {#lui}

旧版用户界面

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_lui_overview"
>title="旧版用户界面"
>abstract="LUI 标识使用了已弃用的用户界面元素，而更高版本的 AEM 和 AEM as a Cloud Service 中不推荐使用或者不支持这些元素。"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/release-notes/aem-cloud-changes" text="显著更改 - AEM as a Cloud Service"

LUI 标识使用了已弃用的用户界面元素，而更高版本的 AEM 和 AEM as a Cloud Service 中不推荐使用或者不支持这些元素。

子类型用于标识应该或必须升级的不同类型用户界面元素：

* `legacy.dialog.classic`：基于 ExtJS 的经典 UI 对话框必须改为 Coral。
   * 当对话框的名称为“dialog”或“design_dialog”并且 `jcr:primaryType` 属性值或 `xtype` 属性值是 `cq:Dialog`.
* `legacy.dialog.coral2`： `Coral 2` 对话框应更新以使用 `Coral 3`.
   * 当对话框及其子内容节点名称为 `cq:dialog/content`，
     `cq:design_dialog/content`， `cq:dialog.coral2/content`“”，或 `cq:design_dialog.coral2/content`
和 `sling:resourceType` 属性值不包含“granite/ui/components/coral/foundation”。
* `legacy.custom.component`：继承自 `foundation/components` 的组件应该更新以使用核心组件。
   * 在以下情况下会检测到此错误： `jcr:primaryType` 属性值是&quot;`cq:Component`”和
     `sling:resourceSuperType` 属性值包含“foundation/components”。 或者，任何
     超类型链组件的 `sling:resourceSuperType` 属性值包含
“foundation/components”时会检测到此情况。
* `legacy.static.template`：静态模板应该升级为可编辑模板。
   * 在以下情况下会检测到此错误： `jcr:primaryType` 属性值是&quot;`cq:Template`“。
* `content.fragment.template`：内容片段模板应创建片段模型以替换片段模板。
   * 内容片段模板可在以下位置找到：
      * 现成的内容片段模板存储在 `/libs/settings/dam/cfm/templates` 中
      * 它们可以在 `/apps/settings/dam/cfm/templates` 或 `/conf/.../settings/dam/cfm/templates`（... = global 或 &quot;tenant&quot;）中覆盖
* `translation.dictionary`： `I18n` 存在于/apps下的词典。
   * /apps 在运行时不可变，而 translator.html 在 AEM as a cloud service 中将不再可用。

## 可能的后果和风险 {#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_lui_guidance"
>title="实施指南"
>abstract="经典 UI 在 AEM as a Cloud Service 中不再可用，用于创作的标准界面为支持触摸的 UI。最佳实践是移动所有不支持的界面，链接的自定义项应重构为与AEMas a Cloud Service兼容的更新特性/功能。 客户可以使用现有的AEM现代化套件来帮助减少打造现代化AEM Sites实施所需的工作。"
>additional-url="https://opensource.adobe.com/aem-modernize-tools/" text="AEM 现代化工具"

* 经典 UI 在 AEM as a Cloud Service 中不再可用。用于创作的标准界面是支持触摸的 UI。
* 从长期来看，依靠旧版自定义组件会增加维护成本。
* 在AEM 6.3中，内容片段模板已由内容片段模型取代。将基于旧模板的内容片段迁移到AEMas a Cloud Service后，这些片段仍然可用，但无法基于旧模板创建片段。 也无法使用AEM GraphQL提供这些片段，而这需要内容片段模型作为架构。
* /apps 在运行时不可变，而 translator.html 在 AEM as a cloud service 中将不再可用。因此， `I18n` 词典必须通过CI/CD管道取自Git。

## 可采用的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_lui_tools"
>title="工具和资源"
>abstract="在 AEM 现代化套件的帮助下，客户可以从经典 (ExtJS) 对话框转为 Coral 对话框。其目的是为了帮助客户从不支持的功能或旧版功能迁移到可靠的现代化 AEM 方案。这些工具可配置、可感知配置且可扩展。 此外，可以探索使用一组标准化核心组件替换自定义组件，以加快应用程序的开发速度并减少维护成本。"
>additional-url="https://opensource.adobe.com/aem-modernize-tools/pages/component/about.html" text="组件转换器"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-core-components/using/introduction" text="核心组件"

* 要减少打造现代化的AEM Sites实施所需的工作，请使用 [AEM现代化工具套件](https://opensource.adobe.com/aem-modernize-tools/). 这些工具包括以下转化：
   * 经典 (ExtJS) 对话框到 Coral 对话框
   * 基础组件到核心组件
   * 静态模板和列控件到可编辑模板和响应式网格
   * 设计和设计对话框到可编辑模板策略
* 审查项目的自定义组件库，如果可能，请转换为一组标准化[核心组件](https://experienceleague.adobe.com/en/docs/experience-manager-core-components/using/introduction)，以加快应用程序的开发速度并减少维护成本。
* 使用与旧模板等同的功能创建内容片段模型，并在将来使用这些模型创建内容片段。 请参阅 [内容片段模型](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/assets/content-fragments/content-fragments-models) 以了解更多详细信息。
* `I18n` 词典必须通过CI/CD管道取自Git。 [文档](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/release-notes/aem-cloud-changes#apps-libs-immutable)
* 联系 [AEM支持团队](https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html) 以澄清或解决问题。
