---
title: URS
description: 图案检测器代码帮助页
translation-type: tm+mt
source-git-commit: 5a83dd8d08da974a5d775032b8dbea2593be9d15
workflow-type: tm+mt
source-wordcount: '295'
ht-degree: 0%

---


# URS {#urs}

不支持的存储库结构

## 背景 {#background}

`URS` 标识不支持的存储库结构。从AEM 6.4开始，已为重组存储库内容提供了准则。 通过明确定义AEM产品代码和客户代码的层次结构并避免它们之间发生冲突，内容将从`/etc`重组到存储库中的其他文件夹，遵循以下高级规则：

* AEM产品代码将始终放置在`/libs`中，而不能被自定义代码覆盖自定义代码应将自定义代码放置在`/apps`、`/content`和`/conf`中。
* 强烈建议将AEM作为Cloud Service遵循这些准则。

子类型用于标识应解决的存储库问题的特定类型：
* `clientlibs.location`:按路径引用的 `/etc` 客户端库。
* `file.location`:安装后 `/etc` 已修改的文件。
* `node.location`:安装后 `/etc` 已修改的节点。
* `workflow.location`:下面的工作流模型或启动 `/etc/workflow`器。
* `package.structure`:包含可变内容和不可变内容的包。

## 可能的影响和风险{#implications-and-risks}

* 依赖较旧路径的自定义代码可能会导致不期望的行为并影响产品功能。
* 同时包含可变内容和不可变内容的包在部署过程中可能会导致问题。

## 可能的解决方案{#solutions}

* 请参阅[存储库重组](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/restructuring/repository-restructuring.html)，以获得准备将AEM作为Cloud Service的指导。
* 另请参阅[AEM项目结构](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html)，进一步了解存储库的可变和不可变区域。
* 请联系我们的[AEM支持团队](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以获得说明或解决问题。
* 利用[存储库Modernizer](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/refactoring-tools/repo-modernizer.html#refactoring-tools)将内容和代码分离为离散的包，以与为Adobe Experience Manager定义的项目结构(作为Cloud Service)兼容，从而重构现有项目包。