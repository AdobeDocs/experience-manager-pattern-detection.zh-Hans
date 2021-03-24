---
title: 密送
description: 图案检测器代码帮助页
translation-type: tm+mt
source-git-commit: 4f94d4a1e0b8eb7bedbedba2c8a683f34655b527
workflow-type: tm+mt
source-wordcount: '123'
ht-degree: 0%

---


# NBCC {#nbcc}

非向后兼容更改

## 背景 {#background}

`NBCC` 标识某些JCR节点或包以不兼容方式更改的情况。在升级前，客户可能不知道此更改。

## 可能的影响和风险{#implications-and-risks}

* 依赖于使用不向后兼容更改的任何组件的功能可能会中断，并且可能无法正确解析。
* 升级后，客户应用程序的某些功能或某些AEM功能可能无法正常工作。

## 可能的解决方案{#solutions}

* 仅覆盖或引用向后兼容的Sling组件。
* 请考虑调整AEM升级后`/libs`或捆绑包中的资源。
* 请联系我们的[AEM支持团队](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以获得说明或解决问题。
