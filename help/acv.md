---
title: ACV
description: 模式检测器代码帮助页
exl-id: 7e3c1142-c349-4bce-b8de-8e91528f80a5
source-git-commit: 66489471aef923c6ab7e02acbab5f941b6459000
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 2%

---

# ACV {#acv}

资产内容验证器

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_acv_overview"
>title="资产内容验证器"
>abstract="ACV可识别资产内容中缺少的必需节点。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/home.html" text="显着更改 — Experience Manager为Cloud Service"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html?lang=zh-Hans" text="Experience Manager作为Cloud Service — 发行说明"

`ACV`  资产的内容验证器可识别资产内容中缺少的必需节点。这可能会导致将某些资产功能作为Experience ManagerCloud Service失败。

子类型用于标识不同类型的信息，例如：

* `missing.jcrcontent`:在存储库中标识缺少必需节点的文件夹。识别存储库中的任何缺失内容有助于防止任何损坏的功能或用例。
* `missing.original.rendition`:在存储库中标识缺少必需原始演绎版的资产。

## 可能的影响和风险 {#implications-and-risks}

* 这可能会导致某些依赖于Experience Manager作为Cloud Service中继承属性的资产功能失败。
* AEM Assets取决于原始呈现的存在。 如果缺少原始演绎版，则Cloud Service中的资产处理将进行循环。

## 可能的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_acv_guidance"
>title="实施指南"
>abstract="Adobe建议查看内容结构，以防止依赖继承属性的工作流损坏。 请联系客户关怀团队以获取帮助。"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud支持"

* 分析文件夹（如果文件夹缺少子节点）。 如果文件夹数量是可管理的，请手动创建节点，否则请使用脚本。
* 对于缺少原始演绎版的资产，请在迁移之前重新上传或删除这些资产。
* 请联系我们的[Experience Manager客户关怀团队](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以获得说明或解决问题。
