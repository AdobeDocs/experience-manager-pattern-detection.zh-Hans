---
title: URS
description: Pattern Detector 代码帮助页面
exl-id: 05c5b664-f034-42a2-918b-07772c8d480f
source-git-commit: d5b8b890502e9951acf01bc15fc1aa2e526ea9e5
workflow-type: ht
source-wordcount: '430'
ht-degree: 100%

---

# URS {#urs}

不支持的存储库结构

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urs_overview"
>title="不支持的存储库结构"
>abstract="URS 标识不支持的存储库结构和节点特征等情况。这会公开信息，以避免 AEM 产品代码与客户代码之间的冲突、将内容从 /etc 重构到存储库中的其他文件夹等等。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/deploying/restructuring/repository-restructuring.html" text="存储库重构"

## 背景 {#background}

`URS` 标识不支持的存储库结构和节点特征等情况。从 AEM 6.4 中开始，为存储库内容的重构提供了准则。通过清楚地描述 AEM 产品代码和客户代码的层次结构并避免其间的冲突、将内容从 `/etc` 重构到存储库中的其他文件夹，遵守以下高级规则：

* AEM 产品代码始终放在 `/libs` 中，这必须使用自定义代码覆盖。
* 自定义代码应放在 `/apps`、`/content` 和 `/conf` 中。
* AEM as a Cloud Service 不支持长节点名称（大于 150 字节）。
* 强烈建议遵循 AEM as a Cloud Service 的这些准则。

子类型用于标识应该解决的特定类型的存储库问题：
* `clientlibs.location`：客户端库按路径引用 `/etc`。
* `file.location`：位于 `/etc` 下自安装以来经过修改的文件。
* `node.location`：位于 `/etc` 下自安装以来经过修改的节点。
* `workflow.location`：位于 `/etc/workflow` 下的工作流模型或启动器。
* `package.structure`：包含可变和不可变内容的软件包。
* `node.size`：不支持节点的大小。

## 可能的后果和风险 {#implications-and-risks}

* 依赖旧路径的自定义代码可能会导致意外行为并影响产品功能。
* 同时包含可变和不可变内容的软件包可能会在部署期间导致问题。

## 可采用的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urs_guidance"
>title="实施指南"
>abstract="最佳实践是审查代码项目并确保它遵守了 AEM 项目结构指南，避免代码依赖于较早的/不支持的存储库路径，这种情况可能会导致 AEM as a Cloud Service 中的意外行为。请联系 Adobe 支持部门获取帮助或说明"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html" text="AEM 项目结构准则"
>additional-url="https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支持"

* 请参考[存储库重构](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/restructuring/repository-restructuring.html)以获取为 AEM as a Cloud Service 做好准备的指南。
* 另请参考 [AEM 项目结构](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html)以详细了解存储库的可变和不可变领域。
* 请联系我们的 [AEM 支持团队](https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html)获取说明或解决问题。
* 利用[存储库现代化器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/refactoring-tools/repo-modernizer.html#refactoring-tools)，通过将内容和代码分隔到单独的软件包来重构现有项目软件包，使其与为 Adobe Experience Manager as a Cloud Service 定义的项目结构兼容。
