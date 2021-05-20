---
title: IOI
description: 模式检测器代码帮助页
exl-id: b6c9d11f-5189-4799-98c0-c2699dfe3f40
source-git-commit: 54b121a6ec29ba6ff6fb33b402f1821c34d0763f
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 0%

---

# IOI {#ioi}

内部Oak导入

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ioi_overview"
>title="内部Oak导入"
>abstract="IOI代码标识客户对内部Oak包的使用，并通过OSGi导入。 它们通常在不使用任何特定版本的情况下导出，并且仅供其他Oak包或低级AEM服务使用。"

`IOI` 识别客户对内部Oak包的使用，并通过OSGi导入。它们通常在不使用任何特定版本的情况下导出，并且仅供其他Oak包或低级AEM服务使用。

其中一些变量由`com.adobe.granite.repository`使用，后者在启动期间为AEM设置存储库。 另一个示例是`com.adobe.granite.maintenance.oak`Adobe包，该包封装并提供Oak维护任务。

## 可能的影响和风险{#implications-and-risks}

* 在将来的AEM版本中，可能会删除内部导出，这会直接取决于Oak，导致依赖项和不活动包损坏。
* 内部导出中的API可能会发生更改。

## 可能的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ioi_guidance"
>title="实施指南"
>abstract="客户应查看其自定义代码，以识别此类API的使用情况，并重构它们以与AEM as a Cloud Service兼容。 联系Adobe支持以获取帮助和说明"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud支持"

* 使用Sling资源API（或JCR API），而不是低级别访问。
* 避免，这取决于不属于任何公共API或SPI的内部包。
* 请联系我们的[AEM支持团队](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以获得说明或解决问题。
