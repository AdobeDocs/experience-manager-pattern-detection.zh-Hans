---
title: UMI
description: Pattern Detector 代码帮助页面。
exl-id: 04efa760-61f5-4690-8b4e-89fa756c5b64
source-git-commit: 0d693e3ccadc81b59852914f115bb2fa2ea166b0
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 100%

---

# UMI {#umi}

升级配置错误问题

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_umi_overview"
>title="升级配置错误问题"
>abstract="UMI 标识对某些 OSGi 配置的修改，这些修改在升级时会导致问题，包括升级失败或者功能减少。"
>additional-url="https://experienceleague.adobe.com/zh-hans/docs/experience-manager-cloud-service/content/release-notes/aem-cloud-changes" text="显著更改 - AEM as a Cloud Service"
>additional-url="https://experienceleague.adobe.com/zh-hans/docs/experience-manager-cloud-service/content/release-notes/release-notes/release-notes-current" text="AEM as a Cloud Service - 发行说明"

`UMI`  标识对某些 OSGi 配置的修改，这些修改在升级时会导致问题，包括升级失败或者功能减少。

检查以下配置的修改：

* `org.apache.jackrabbit.oak.security.user.RandomAuthorizableNodeName`
* `org.apache.jackrabbit.oak.security.internal.SecurityProviderRegistration.requiredServicePids`
* `org.apache.sling.engine.impl.auth.SlingAuthenticator`
* `org.apache.sling.scripting.java.impl.JavaScriptEngineFactory`
* `com.day.cq.commons.impl.ExternalizerImpl`
* `org.apache.sling.commons.log.LogManager.factory.config`：确认自定义记录器的 `org.apache.sling.commons.log.file` 属性是否指向 `logs/error.log` 文件以外的内容。

## 可能产生的后果和风险 {#implications-and-risks}

* 更改或移除配置可能导致以下问题：
   * 升级可能会卡住（例如，`org.apache.jackrabbit.oak.security.user.RandomAuthorizableNodeName` 缺失但存在于 `org.apache.jackrabbit.oak.security.internal.SecurityProviderRegistration.requiredServicePids` 中）。
   * 升级后可能出现授权问题 (`org.apache.sling.engine.impl.auth.SlingAuthenticator`)。
   * 特定功能可能无法正常工作。例如，更改 `org.apache.sling.scripting.java.impl.JavaScriptEngineFactory` 可能会导致一些 JSP 文件未编译，这最终会导致功能丢失。
   * Externalizer 配置的值 `com.day.cq.commons.impl.ExternalizerImpl` 在 AEM as a Cloud Service 中通过云管理器环境变量设置。
   * AEM as a Cloud Service 不支持自定义日志文件。写入自定义命名日志的日志不能从 AEM as a Cloud Service 访问。

## 可采用的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_umi_guidance"
>title="实施指南"
>abstract="最佳实践是审查当前配置并恢复对所述配置进行的更改，以避免任何以后的升级问题。联系 Adobe 支持获取帮助或说明。"
>additional-url="https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支持"

* 请勿更改或移除以上提及的四个配置。
   * 如果有以下违规行为：\
     `xyz-configuration`“缺少 OSGi 配置的必需属性：‘[属性-1，属性-2...]’。”\
     由于这些 OSGi 配置是 OOTB，可能从未通过 OSGi 配置管理器修改/保存过，因此请确认这些删除是否合法。
* 如果配置已更改，它们应恢复到其预期值。这些值在 `UMI` 消息中指明。
* 对于 `com.day.cq.commons.impl.ExternalizerImpl`，请参阅关于在 AEM as a Cloud Service 中使用云管理器环境变量设置 Externalizer 的[文档](https://experienceleague.adobe.com/zh-hans/docs/experience-manager-cloud-service/content/implementing/developer-tools/externalizer)。
* 对于 `org.apache.sling.commons.log.LogManager.factory.config`，更改 OSGI 配置以将自定义的记录器发送到 `logs/error.log` 文件。请参阅关于重新指向`logs/error.log`文件的[文档](https://experienceleague.adobe.com/zh-hans/docs/experience-manager-learn/cloud-service/debugging/debugging-aem-as-a-cloud-service/logs)。
* 请联系 [AEM 支持团队](https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html) 进行澄清或解决疑惑。
