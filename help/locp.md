---
title: LOCP
description: 图案检测器代码帮助页
translation-type: tm+mt
source-git-commit: 4f94d4a1e0b8eb7bedbedba2c8a683f34655b527
workflow-type: tm+mt
source-wordcount: '93'
ht-degree: 1%

---


# LOCP {#locp}

/libs覆盖自定义包

## 背景 {#background}

`LOCP` 标识将内容发送到的自定义包的 `/libs`检测，这是一种反模式（ACL除外）。

## 可能的影响和风险{#implications-and-risks}

* 对于任何CFP、SP或主要AEM升级，可能会删除或替换客户代码。
* 在某些情况下，新内容可能未正确安装。

## 可能的解决方案{#solutions}

* 客户包应将内容部署到`/apps`，而不是`/libs`。
* 请联系我们的[AEM支持团队](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以获得说明或解决问题。
