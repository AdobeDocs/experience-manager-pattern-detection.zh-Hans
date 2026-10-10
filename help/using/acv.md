---
title: ACV
description: Pattern Detector 代码帮助页面。
exl-id: 1dd1af45-aa56-48da-8582-c4330cded489
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
source-git-commit: baa8f6dbf24b735348ed6b27f1e885b5078859ce
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 100%
---
# ACV {#acv}

Assets Content Validator

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_acv_overview"
>title="Assets Content Validator"
>abstract="ACV 标识资源内容中缺少的必需节点。"
>additional-url="https://experienceleague.adobe.com/zh-hans/docs/experience-manager-cloud-service/content/assets/overview" text="重要变更 - Experience Manager as a Cloud Service"
>additional-url="https://experienceleague.adobe.com/zh-hans/docs/experience-manager-cloud-service/content/release-notes/release-notes/release-notes-current" text="Experience Manager as a Cloud Service - 发行说明"

`ACV`（资源的内容验证程序）标识资源内容中缺少的必需节点和违规内容。 这些问题可能会导致 Experience Manager as a Cloud Service 上某些 Assets 功能失效。

子类型用于标识信息的不同类型，例如：

* `missing.jcrcontent`：标识缺少存储库中必需节点的文件夹。 标识存储库中任何缺少的内容有助于防止功能或用例无法正常工作。
* `missing.original.rendition`：标识资源在存储库中缺少必要的原始演绎版。 预览 PDF 的页面不需要在 AEMaaCS 中生成子资产。 因此，对于 PDF 资源不再报告子资源缺少原始演绎版。
* `metadata.descendants.violation`：标识存储库中资源元数据节点下具有 100 个以上后代的资源。
* `conflict.node`：标识 /content/dam/ 路径下的存储库中存在发生冲突的节点。
* `psb.file.large`：标识大小超过 2 GB 的大型 PSB 文件（`dc:format : application/vnd.3gpp.pic-bw-small`）。
* `invalid.asset.name`：标识名称中含有无效字符 [`* / : [ \ ] | # % { } ? &`] 的资源。

## 可能产生的后果和风险 {#implications-and-risks}

* 可能会导致依赖于 Experience Manager as a Cloud Service 中继承属性的特定 Assets 功能出现故障。
* AEM Assets 依赖于原始演绎版的存在。 如果缺少原始演绎版，则 Cloud Service 中的资产处理会陷入循环。 AEMaaCS 不支持生成子资源。
* 元数据节点下面的后代数量较多可能会降低包含违规资源的文件夹的加载速度。
* 存在发生冲突的节点可能导致在 AEM as a Cloud Service 上引入失败。
* Experience Manager 可能无法处理分辨率高的 PSB 文件。 如果未对 Experience Manager 服务器进行适当的基准测试，使用 ImageMagick 处理大型文件的客户可能会遇到性能问题。
* 资产名称中的无效字符可能会导致迁移到 AEM as a Cloud Service 时失败。

## 可采用的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_acv_guidance"
>title="实施指南"
>abstract="Adobe 建议审查内容结构，以防止依赖继承属性的工作流中断。 联系客户关怀部门寻求帮助。"
>additional-url="https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支持"

* 如果文件夹缺少子节点，请分析该文件夹。 如果文件夹数量可控，则手动创建节点，否则使用脚本。
* 对于缺少原始演绎版的资源，请重新上传资源或者在迁移之前删除它们。
* 对于缺少原始演绎版的子资源，无需执行任何操作。
* 如果存在冲突节点，则应在迁移到 AEM as a Cloud Service 之前解决或删除它们。
* 如果您计划处理大量大型 PSD 或 PSB 文件，请联系 Adobe 客户支持团队。 Experience Manager 可能无法处理超过 30000 x 23000 像素的高分辨率 PSB 文件。 请参阅[文档](https://experienceleague.adobe.com/zh-hans/docs/experience-manager-65/content/assets/extending/best-practices-for-imagemagick)。
* 请联系我们的 [Experience Manager 客户服务团队](https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html)进行澄清或解决疑惑。
