---
title: ECU
description: Pattern Detector 代码帮助页面。
exl-id: fd061001-b00e-44ae-bd31-71bd2fa733cd
source-git-commit: 2881b122773a8a5ad09fb9a14ae35b4a83dae20d
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 75%

---

# ECU {#ecu}

已弃用：无关内容使用（替换为 CAV，即内容领域违规）

## 背景 {#background}

`ECU`  标识以违反内容分类规则的方式使用不同内容区域的模式。

Sling 请求处理定义如何使用资源的内容（特别是其 `sling:resourceType` 属性），用于确定将用于渲染内容的脚本。（有关更多信息，请参阅[定位脚本](https://experienceleague.adobe.com/zh-hans/docs/experience-manager-65/content/implementing/developing/introduction/the-basics#locating-the-script)。）Sling还提供了通过叠加和覆盖来访问和合并资源的技术。 这些技术被描述为 [Sling资源合并器](https://experienceleague.adobe.com/zh-hans/docs/experience-manager-65/content/implementing/developing/platform/sling-resource-merger) 和 [叠加](https://experienceleague.adobe.com/zh-hans/docs/experience-manager-65/content/implementing/developing/platform/overlays).

使客户更安全、更轻松地了解 `/libs` 可以安全使用和叠加，内容位于 `/libs` 已分类为“mixin”物业：

* 公共
* 摘要
* 最终
* 内部

每个分类都暗示了有关如何使用、继承或覆盖内容的规则。有关详细说明，请参阅[可持续升级](https://experienceleague.adobe.com/zh-hans/docs/experience-manager-65/content/implementing/deploying/upgrading/sustainable-upgrades)。

## 可能产生的后果和风险 {#implications-and-risks}

* AEM 升级可能导致页面渲染问题或其他意外行为。
* 安全更新不生效。

## 可采用的解决方案 {#solutions}

* 尽可能减少内容叠加的使用，仅限那些需要的用例。
* 特别是，避免叠加限制的内容（Final 和 Internal 分类）。
* 在升级 AEM 、Service Pack 或安装 Cumulative Fix Pack 后，请考虑采用来自 `/libs` 的更改。
* 请联系 [AEM 支持团队](https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html) 进行澄清或解决疑惑。
