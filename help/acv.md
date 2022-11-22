---
title: ACV
description: Pattern Detector 代码帮助页面
exl-id: 1dd1af45-aa56-48da-8582-c4330cded489
source-git-commit: e7096efc1d9da7f5aad5a5b353ba622c879cc4a5
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 89%

---

# ACV {#acv}

Assets Content Validator

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_acv_overview"
>title="资产内容验证器"
>abstract="ACV 标识资源内容中缺少的必需节点。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/home.html" text="显著更改 - Experience Manager as a Cloud Service"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html" text="Experience Manager as a Cloud Service - 发行说明"

`ACV` 资源的内容验证程序标识资源内容中缺少的必需节点和违规内容。这可能会导致 Experience Manager as a Cloud Service 上特定 Assets 功能的故障。

子类型用于标识信息的不同类型，例如：

* `missing.jcrcontent`：标识缺少存储库中必需节点的文件夹。标识存储库中任何缺少的内容有助于防止损坏的功能或用例。
* `missing.original.rendition`：标识存储库中缺少必需原始演绎版的资源。请注意，预览PDF的页面不需要在AEMaCS中生成子资产。 因此，对于PDF资产，会禁止显示缺少原始呈现版本的报表子资产。
* `metadata.descendants.violation`：标识存储库中资源元数据节点下具有 100 个以上后代的资源。

## 可能的后果和风险 {#implications-and-risks}

* 这可能会导致依赖于 Experience Manager as a Cloud Service 中继承属性的特定 Assets 功能出现故障。
* AEM Assets 依赖于原始演绎版的存在。如果缺少原始演绎版，Cloud Service 中的资源处理将进入循环。AEMaCS不支持生成子资产。
* 元数据节点下面的后代数量较多可能会降低包含违规资源的文件夹的加载速度。

## 可采用的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_acv_guidance"
>title="实施指南"
>abstract="Adobe 建议审查内容结构，以防止依赖于继承属性的工作流损坏。联系客户关怀部门寻求帮助。"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支持"

* 分析文件夹是否有缺少的子节点。如果文件夹的数量可以管理，则手动创建节点，否则使用脚本。
* 对于缺少原始演绎版的资源，请重新上传资源或者在迁移之前删除它们。
* 缺少子资产原始呈现不需要执行任何操作。
* 请联系我们的 [Experience Manager 客户关怀团队](https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html)获取说明或解决问题。
