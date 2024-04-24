---
title: ECU
description: Pattern Detector代码帮助页面。
exl-id: fd061001-b00e-44ae-bd31-71bd2fa733cd
source-git-commit: 84c193b66fbf9c41f546e8575a0aa17e94043b9a
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 50%

---

# ECU {#ecu}

已弃用：无关内容使用（替换为 CAV，即内容领域违规）

## 背景 {#background}

`ECU`  标识这样一种模式，不同内容领域的使用方式违反了内容分类规则。

Sling请求处理定义资源的内容、其 `sling:resourceType` 属性用于确定用于呈现内容的脚本。 （有关更多信息，请参阅[定位脚本](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/developing/introduction/the-basics#locating-the-script)。）Sling 还提供了通过“叠加”和“覆盖”来访问及合并资源的技术。这些内容在 [Sling 资源合并器](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/developing/platform/sling-resource-merger)和[叠加](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/developing/platform/overlays)中介绍。

使客户更安全、更轻松地了解 `/libs` 可以安全使用并覆盖中的内容 `/libs` 已使用“mixin”属性进行分类：Public、Abstract、Final和Internal。 每个分类都暗示了有关如何使用、继承或覆盖内容的规则。有关详细说明，请参阅[可持续升级](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/deploying/upgrading/sustainable-upgrades)。

## 可能的后果和风险 {#implications-and-risks}

* AEM 升级可能导致页面渲染问题或其他意外行为。
* 安全更新不生效。

## 可采用的解决方案 {#solutions}

* 尽可能减少内容叠加的使用，仅限那些需要的用例。
* 特别是，避免叠加限制的内容（Final 和 Internal 分类）。
* 考虑调整来自的更改 `/libs` 安装AEM升级、Service Pack或累积修订包后。
* 联系 [AEM支持团队](https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html) 以澄清或解决问题。
