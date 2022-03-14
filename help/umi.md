---
title: UMI
description: Pattern Detector 代码帮助页面
exl-id: 04efa760-61f5-4690-8b4e-89fa756c5b64
source-git-commit: e72ddc20578f8ca736da198e626478816e7ca641
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# UMI {#umi}

升级配置错误问题

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_umi_overview"
>title="升级配置错误问题"
>abstract="UMI 标识对特定 OSGi 配置的修改，这些修改在升级时会导致问题，包括升级失败或者功能减少。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html" text="显著更改 - AEM as a Cloud Service"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html" text="AEM as a Cloud Service - 发行说明"

`UMI` 标识对特定 OSGi 配置的修改，这些修改在升级时会导致问题，包括升级失败或者功能减少。

检查以下配置的修改：
* `org.apache.jackrabbit.oak.security.user.RandomAuthorizableNodeName`
* `org.apache.jackrabbit.oak.security.internal.SecurityProviderRegistration.requiredServicePids`
* `org.apache.sling.engine.impl.auth.SlingAuthenticator`
* `org.apache.sling.scripting.java.impl.JavaScriptEngineFactory`
* `com.day.cq.commons.impl.ExternalizerImpl`

## 可能的后果和风险 {#implications-and-risks}

* 更改或移除配置可能导致以下问题：
   * 升级可能会卡住（例如，`org.apache.jackrabbit.oak.security.user.RandomAuthorizableNodeName` 缺失但存在于 `org.apache.jackrabbit.oak.security.internal.SecurityProviderRegistration.requiredServicePids` 中）。
   * 升级后可能出现授权问题 (`org.apache.sling.engine.impl.auth.SlingAuthenticator`)。
   * 特定功能可能无法正常工作。例如，更改 `org.apache.sling.scripting.java.impl.JavaScriptEngineFactory` 会导致一些 JSP 文件未编译，这最终会导致功能丢失。
   * 外部器配置的值 `com.day.cq.commons.impl.ExternalizerImpl` 由cloud manageras a Cloud Service中的环境变量设置。

## 可采用的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_umi_guidance"
>title="实施指南"
>abstract="最佳实践是审查当前配置，恢复对所述配置进行的更改以避免任何以后的升级问题。请联系 Adobe 支持部门获取帮助或说明"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支持"

* 请勿更改或移除以上提及的四个配置。
* 如果配置已更改，它们应恢复到其预期值。这些值在 `UMI` 消息中指明。
* 对于 `com.day.cq.commons.impl.ExternalizerImpl`，请参阅 [文档](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developer-tools/externalizer.html?lang=en) 用于在AEMas a Cloud Service中使用cloud manager环境变量设置externalizer配置。
* 请联系我们的 [AEM 支持团队](https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html)获取说明或解决问题。
