---
title: URS
description: Pattern Detector 代码帮助页面。
exl-id: 05c5b664-f034-42a2-918b-07772c8d480f
source-git-commit: 84c193b66fbf9c41f546e8575a0aa17e94043b9a
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 74%

---

# URS {#urs}

不支持的存储库结构

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urs_overview"
>title="不支持的存储库结构"
>abstract="URS 标识不支持的存储库结构和节点特征等情况。这会公开信息，以避免 AEM 产品代码与客户代码之间的冲突、将内容从 /etc 重构到存储库中的其他文件夹等等。"
>additional-url="https://experienceleague.adobe.com/zh-hans/docs/experience-manager-65/content/implementing/deploying/restructuring/repository-restructuring" text="存储库重构"

## 背景 {#background}

`URS`  标识不支持的存储库结构和节点特征等情况。 从 AEM 6.4 中开始，为存储库内容的重构提供了准则。通过清楚地描述 AEM 产品代码和客户代码的层次结构并避免其间的冲突、将内容从 `/etc` 重构到存储库中的其他文件夹，遵守以下高级规则：

* AEM产品代码始终放在 `/libs`，这必须使用自定义代码覆盖。
* 自定义代码应放在 `/apps`， `/content`、和 `/conf`.
* 强烈建议遵循 AEM as a Cloud Service 的这些准则。

子类型用于标识应该解决的特定类型的存储库问题：

* `clientlibs.location`：客户端库按路径引用 `/etc`。
* `file.location`：位于 `/etc` 下自安装以来经过修改的文件。
* `node.location`：位于 `/etc` 下自安装以来经过修改的节点。
* `workflow.location`：位于 `/etc/workflow` 下的工作流模型或启动器。
* `package.structure`：包含可变和不可变内容的软件包。
* `node.size`：不支持节点的大小。

## 可能产生的后果和风险 {#implications-and-risks}

* 依赖旧路径的自定义代码可能会导致意外行为并影响产品功能。
* 同时包含可变和不可变内容的软件包可能会在部署期间导致问题。

## 可采用的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urs_guidance"
>title="实施指南"
>abstract="最佳做法是检查您的代码项目。最佳做法是审查代码项目并确保它遵守了 AEM 项目结构指南，避免代码依赖于较早的/不支持的存储库路径，这种情况可能会导致 AEM as a Cloud Service 中出现意外行为。联系 Adobe 支持获取帮助或说明。"
>additional-url="https://experienceleague.adobe.com/zh-hans/docs/experience-manager-cloud-service/content/implementing/developing/aem-project-content-package-structure" text="AEM 项目结构准则"
>additional-url="https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支持"

* 请参阅[存储库重构](https://experienceleague.adobe.com/zh-hans/docs/experience-manager-65/content/implementing/deploying/restructuring/repository-restructuring)以获取为 AEM as a Cloud Service 做好准备的指南。
* 另请参阅 [AEM项目结构](https://experienceleague.adobe.com/zh-hans/docs/experience-manager-cloud-service/content/implementing/developing/aem-project-content-package-structure) 如果您想了解有关存储库的可变和不可变区域的更多信息。
* 请联系 [AEM 支持团队](https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html) 进行澄清或解决疑惑。
* 使用 [存储库现代化器](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/migration-journey/refactoring-tools/repo-modernizer#refactoring-tools) 通过将内容和代码分隔到单独的软件包来重构现有项目软件包，使其与为Adobe Experience Manager as a Cloud Service定义的项目结构兼容。
