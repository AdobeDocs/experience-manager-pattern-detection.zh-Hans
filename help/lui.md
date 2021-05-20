---
title: 吕
description: 模式检测器代码帮助页
exl-id: 742220d6-b37a-48ec-9f89-2f3f0ce6ff96
source-git-commit: 76dc944f1592118920f89c513faf456b8aa443a9
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 5%

---

# 吕 {#lui}

旧版用户界面

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_lui_overview"
>title="旧版用户界面"
>abstract="LUI标识了在AEM的较新版本和AEM as a Cloud Service中不建议或不支持的已弃用用户界面元素的使用。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html" text="显着更改 — AEM作为Cloud Service"

`LUI` 标识在AEM的较新版本和AEM as a Cloud Service中不建议或不支持的已弃用用户界面元素的使用。

子类型用于标识应升级或必须升级的不同类型的用户界面元素：

* `legacy.dialog.classic`:必须将基于ExtJS的经典UI对话框更改为Coral。
   * 当对话框名称为“dialog”或“design_dialog”时，以及
`jcr:primaryType`属性值或`xtype`属性值为“cq:Dialog”。
* `legacy.dialog.coral2`:Coral 2对话框应更新为使用Coral 3。
   * 当对话框及其子内容节点名称为“cq:dialog/content”时，会检测到此情况。
&quot;cq:design_dialog/content&quot;、&quot;cq:dialog.coral2/content&quot;或&quot;cq:design_dialog.coral2/content&quot;
和`sling:resourceType`属性值不包含
&quot;granite/ui/components/coral/foundation&quot;。
* `legacy.custom.component`:应更新从继承 `foundation/components`的组件，以使用核心组件。
   * 当`jcr:primaryType`属性值为“cq:Component”且
      `sling:resourceSuperType` 属性值包含“foundation/components”或
      `sling:resourceSuperType` 超类型组件链的属性值包含“foundation/components”。
* `legacy.static.template`:静态模板，应将其升级到可编辑的模板。
   * 当`jcr:primaryType`属性值为“cq:Template”时，会检测到此情况。

## 可能的影响和风险{#implications-and-risks}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_lui_guidance"
>title="实施指南"
>abstract="经典UI不再作为Cloud Service在AEM中可用，而创作的标准界面是触屏UI。 最佳做法是将所有不受支持的界面和链接的自定义都重构为与AEM作为Cloud Service兼容的较新特性/功能。 客户可以利用现有的AEM现代化套件来帮助减少使AEM Sites实施现代化所需的工作。"
>additional-url="https://opensource.adobe.com/aem-modernize-tools/" text="AEM 现代化工具"

* 经典UI在AEM中不再作为Cloud Service提供。 创作的标准界面是触屏UI。
* 随着时间的推移，依赖旧版自定义组件可能会增加维护成本。

## 可能的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_lui_tools"
>title="工具和资源"
>abstract="借助AEM Moderinization Suite，客户可以将经典(ExtJS)对话框转换为Coral对话框。 其目的是帮助客户从不受支持的或旧版功能转变为强大的现代AEM产品。 这些工具具有可配置、可感知配置和可扩展性。 此外，探索使用一组标准化核心组件来替换自定义组件，以加快开发时间并降低应用程序的维护成本。"
>additional-url="https://opensource.adobe.com/aem-modernize-tools/pages/tools/component.html" text="组件转换器"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-core-components/using/introduction.html" text="核心组件"

* 利用[AEM现代化工具套件](https://opensource.adobe.com/aem-modernize-tools/)减少使AEM Sites实施符合现代化要求所需的工作。 这些工具包括：
   * 经典(ExtJS)对话框到Coral对话框
   * 基础组件到核心组件
   * 可编辑模板和响应式网格的静态模板和列控件
   * 可编辑的模板策略的设计和设计对话框
* 查看项目的自定义组件库并尽可能过渡到标准化的[核心组件](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/introduction.html?lang=zh-Hans)集，以加快开发时间并降低应用程序的维护成本。
* 请联系我们的[AEM支持团队](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以获得说明或解决问题。
