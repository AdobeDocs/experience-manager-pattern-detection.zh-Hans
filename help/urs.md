---
title: URS
description: 模式检测器代码帮助页
exl-id: 05c5b664-f034-42a2-918b-07772c8d480f
source-git-commit: 54b121a6ec29ba6ff6fb33b402f1821c34d0763f
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 0%

---

# URS {#urs}

不支持的存储库结构

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urs_overview"
>title="不支持的存储库结构"
>abstract="URS标识不受支持的存储库结构。 这可显示信息以避免AEM产品代码和客户代码之间的冲突、从/etc重组到存储库中的其他文件夹的内容等。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-65/deploying/restructuring/repository-restructuring.html" text="存储库重组"

## 背景 {#background}

`URS` 标识不支持的存储库结构的大小写。从AEM 6.4开始，已为存储库内容的重组提供准则。 通过明确定义AEM产品代码和客户代码的层次结构并避免它们之间的冲突，内容将从`/etc`重组到存储库中的其他文件夹，并遵循以下高级规则：

* AEM产品代码将始终放置在`/libs`中，且不得被自定义代码覆盖自定义代码自定义代码应放置在`/apps`、`/content`和`/conf`中。
* 强烈建议遵循这些准则，AEM as a Cloud Service。

子类型用于确定应解决的特定类型的存储库问题：
* `clientlibs.location`:按路径引用的客 `/etc` 户端库。
* `file.location`:安装后 `/etc` 修改的文件。
* `node.location`:安装后 `/etc` 已修改的下的节点。
* `workflow.location`:下的工作流模型或启动 `/etc/workflow`器。
* `package.structure`:包含可变和不可变内容的包。

## 可能的影响和风险{#implications-and-risks}

* 依赖于旧路径的自定义代码可能会导致不需要的行为并影响产品功能。
* 同时包含可变和不可变内容的包在部署期间可能会导致问题。

## 可能的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_urs_guidance"
>title="实施指南"
>abstract="最佳做法是审核您的代码项目，并确保它遵循AEM项目结构准则，并避免代码依赖较旧/不受支持的存储库路径，该路径可能会导致AEM作为Cloud Service中出现不希望的行为。 联系Adobe支持以获取帮助和说明"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html" text="AEM项目结构指南"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud支持"

* 请参阅[存储库重组](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/restructuring/repository-restructuring.html) ，以获取有关准备将AEM作为Cloud Service的指导。
* 另请参阅[AEM项目结构](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html) ，了解有关存储库中可变和不可变区域的更多信息。
* 请联系我们的[AEM支持团队](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以获得说明或解决问题。
* 利用[Repository Modernizer](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/refactoring-tools/repo-modernizer.html#refactoring-tools)将内容和代码分离为离散包，以与为Adobe Experience Manager(作为Cloud Service)定义的项目结构兼容，从而重构现有项目包。
