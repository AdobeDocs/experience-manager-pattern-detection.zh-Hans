---
title: IOI
description: 图案检测器代码帮助页
translation-type: tm+mt
source-git-commit: 4f94d4a1e0b8eb7bedbedba2c8a683f34655b527
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 0%

---


# IOI {#ioi}

内部Oak导入

## 背景 {#background}

`IOI` 识别客户对内部Oak包的使用，并通过OSGi导入。它们通常导出时没有任何特定版本，并且仅供其他Oak捆绑套件或低级AEM服务使用。

其中有些由`com.adobe.granite.repository`使用，后者在启动过程中为AEM设置存储库。 另一个示例是`com.adobe.granite.maintenance.oak`Adobe包，它包装并提供Oak维护任务。

## 可能的影响和风险{#implications-and-risks}

* 在将来的AEM版本中，可能会删除内部导出，直接根据Oak的不同导致依赖关系和非活动捆绑包损坏。
* 内部导出中的API可能会更改。

## 可能的解决方案{#solutions}

* 使用Sling Resource API（或JCR API）代替低级访问。
* 请避免依赖不属于任何公共API或SPI的内部包。
* 请联系我们的[AEM支持团队](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以获得说明或解决问题。