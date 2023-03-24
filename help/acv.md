---
title: ACV
description: Pattern Detector 代码帮助页面
exl-id: 1dd1af45-aa56-48da-8582-c4330cded489
source-git-commit: 1aa0169c5ea5180500fd41c8074a9bf561151b62
workflow-type: ht
source-wordcount: '492'
ht-degree: 100%

---

# ACV {#acv}

Assets Content Validator

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_acv_overview"
>title="Assets Content Validator"
>abstract="ACV 标识资源内容中缺少的必需节点。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/home.html" text="显著更改 - Experience Manager as a Cloud Service"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html" text="Experience Manager as a Cloud Service - 发行说明"

`ACV` 资源的内容验证程序标识资源内容中缺少的必需节点和违规内容。这可能会导致 Experience Manager as a Cloud Service 上特定 Assets 功能的故障。

子类型用于标识信息的不同类型，例如：

* `missing.jcrcontent`：标识缺少存储库中必需节点的文件夹。标识存储库中任何缺少的内容有助于防止损坏的功能或用例。
* `missing.original.rendition`：标识资源在存储库中缺少必要的原始演绎版。敬请注意，预览 PDF 的页面不需要在 AEMaaCS 中生成子资源。因此，对于 PDF 资源不再报告子资源缺少原始演绎版。
* `metadata.descendants.violation`：标识存储库中资源元数据节点下具有 100 个以上后代的资源。
* `conflict.node`：标识 /content/dam/ 路径下的存储库中存在发生冲突的节点。
* `psb.file.large`：识别大小大于 2 GB 的大型 PSB 文件 (dc:format : application/vnd.3gpp.pic-bw-small)。

## 可能的后果和风险 {#implications-and-risks}

* 这可能会导致依赖于 Experience Manager as a Cloud Service 中继承属性的特定 Assets 功能出现故障。
* AEM Assets 依赖于原始演绎版的存在。如果缺少原始演绎版，则在 Cloud Service 中处理资源将陷入循环。AEMaaCS 不支持生成子资源。
* 元数据节点下面的后代数量较多可能会降低包含违规资源的文件夹的加载速度。
* 存在发生冲突的节点可能导致在 AEM as a Cloud Service 上摄取失败。
* Experience Manager 可能无法处理分辨率非常高的 PSB 文件。如果未对 Experience Manager 服务器进行适当的基准测试，使用 ImageMagick 处理大型文件的客户可能会遇到性能问题。

## 可采用的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_acv_guidance"
>title="实施指南"
>abstract="Adobe 建议审查内容结构，以防止依赖于继承属性的工作流损坏。联系客户关怀部门寻求帮助。"
>additional-url="https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支持"

* 分析文件夹是否有缺少的子节点。如果文件夹的数量可以管理，则手动创建节点，否则使用脚本。
* 对于缺少原始演绎版的资源，请重新上传资源或者在迁移之前删除它们。
* 缺少子资源原始演绎版无需采取任何操作。
* 如果存在发生冲突的节点，则在迁移到 AEM as a Cloud Service 之前，或者应解决冲突，或者可能需要删除这些节点。
* 如果您计划处理大量大型 PSD 或 PSB 文件，请联系 Adobe 客户支持团队。Experience Manager 可能无法处理超过 30000 x 23000 像素的高分辨率 PSB 文件。请参考[文档](https://experienceleague.adobe.com/docs/experience-manager-65/assets/extending/best-practices-for-imagemagick.html)。
* 请联系我们的 [Experience Manager 客户关怀团队](https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html)以获取说明或解决问题。
