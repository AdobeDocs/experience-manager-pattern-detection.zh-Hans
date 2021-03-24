---
title: 吕
description: 图案检测器代码帮助页
translation-type: tm+mt
source-git-commit: a2c7137dd5cb2479bc0c6134d3afa58111049a68
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 4%

---


# LUI {#lui}

旧式用户界面

## 背景 {#background}

`LUI` 将AEM较高版本和AEM中不推荐或不支持的已弃用用户界面元素用作Cloud Service。

子类型用于标识应或必须升级的不同类型的用户界面元素：

* `legacy.dialog.classic`:必须将基于ExtJS的经典UI对话框更改为Coral。
   * 当对话框名称为“dialog”或“design_dialog”时以及
`jcr:primaryType`属性值或`xtype`属性值为&quot;cq:Dialog&quot;。
* `legacy.dialog.coral2`:Coral 2对话框应更新为使用Coral 3。
   * 当对话框及其子内容节点名称为“cq:dialog/content”时，会检测到此问题
&quot;cq:design_dialog/content&quot;、&quot;cq:dialog.coral2/content&quot;或&quot;cq:design_dialog.coral2/content&quot;
和`sling:resourceType`属性值不包含
&quot;granite/ui/components/coral/foundation&quot;。
* `legacy.custom.component`:继承的组 `foundation/components`件应更新为使用核心组件。
   * 当`jcr:primaryType`属性值为“cq:Component”且
      `sling:resourceSuperType` 属性值包含“foundation/components”或
      `sling:resourceSuperType` 超类型组件链的属性值包含“foundation/components”。
* `legacy.static.template`:静态模板，应升级到可编辑模板。
   * 当`jcr:primaryType`属性值为“cq:Template”时检测到此值。

## 可能的影响和风险{#implications-and-risks}

* 经典UI在AEM中不再作为Cloud Service可用。 创作的标准界面是触屏优化UI。
* 随着时间的推移，依赖旧版自定义组件可能会增加维护成本。

## 可能的解决方案{#solutions}

* 利用[AEM Moderization Tools suite](https://opensource.adobe.com/aem-modernize-tools/)减少实现AEM Sites实施现代化所需的工作。 这些工具包括以下产品的转换：
   * 经典(ExtJS)对话框至珊瑚对话框
   * 基础组件到核心组件
   * 对可编辑模板和响应式网格的静态模板和列控件
   * 设计和设计对话框到可编辑的模板策略
* 如果可能，请查阅项目的自定义组件库和过渡，以设置标准化的[核心组件](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/introduction.html)，以缩短开发时间并降低应用程序的维护成本。
* 请联系我们的[AEM支持团队](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以获得说明或解决问题。
