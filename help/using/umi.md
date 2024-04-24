---
title: UMI
description: Pattern Detector代码帮助页面。
exl-id: 04efa760-61f5-4690-8b4e-89fa756c5b64
source-git-commit: 84c193b66fbf9c41f546e8575a0aa17e94043b9a
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 41%

---

# UMI {#umi}

升级配置错误问题

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_umi_overview"
>title="升级配置错误问题"
>abstract="UMI标识对特定OSGi配置的修改，这些修改在升级时会导致问题，包括升级失败或功能减少。"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/release-notes/aem-cloud-changes" text="显著更改 - AEM as a Cloud Service"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/release-notes/release-notes/release-notes-current" text="AEM as a Cloud Service - 发行说明"

`UMI`  标识对特定OSGi配置的修改，这些修改在升级时会导致问题，包括升级失败或者功能减少。

检查以下配置的修改：

* `org.apache.jackrabbit.oak.security.user.RandomAuthorizableNodeName`
* `org.apache.jackrabbit.oak.security.internal.SecurityProviderRegistration.requiredServicePids`
* `org.apache.sling.engine.impl.auth.SlingAuthenticator`
* `org.apache.sling.scripting.java.impl.JavaScriptEngineFactory`
* `com.day.cq.commons.impl.ExternalizerImpl`
* `org.apache.sling.commons.log.LogManager.factory.config`：确认自定义记录器的 `org.apache.sling.commons.log.file` 属性是否指向 `logs/error.log` 文件以外的内容。

## 可能的后果和风险 {#implications-and-risks}

* 更改或移除配置可能导致以下问题：
   * 升级可能会卡住（例如，`org.apache.jackrabbit.oak.security.user.RandomAuthorizableNodeName` 缺失但存在于 `org.apache.jackrabbit.oak.security.internal.SecurityProviderRegistration.requiredServicePids` 中）。
   * 升级后可能出现授权问题 (`org.apache.sling.engine.impl.auth.SlingAuthenticator`)。
   * 特定功能可能无法正常工作。例如，更改 `org.apache.sling.scripting.java.impl.JavaScriptEngineFactory` 可能会导致一些JSP文件未编译，这最终会导致功能丢失。
   * Externalizer配置的值 `com.day.cq.commons.impl.ExternalizerImpl` 由AEMas a Cloud Service中的cloud manager环境变量设置。
   * AEM as a Cloud Service 不支持自定义日志文件。无法从AEMas a Cloud Service访问写入自定义命名日志的日志。

## 可采用的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_umi_guidance"
>title="实施指南"
>abstract="最佳实践是审查当前配置，恢复对上述配置所做的任何更改，以避免任何未来升级问题。 请联系Adobe支持部门以获取帮助或说明。"
>additional-url="https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支持"

* 请勿更改或移除以上提及的四个配置。
   * 如果存在以下违规：\
     “OSGi配置的必需属性 `xyz-configuration` 缺失： &#39;[属性–1，属性–2...]“。”\
     确认这些删除是否合法，因为这些OSGi配置是OOTB，可能从未从OSGi配置管理器中修改/保存。
* 如果配置已更改，它们应恢复到其预期值。这些值在 `UMI` 消息中指明。
* 对象 `com.day.cq.commons.impl.ExternalizerImpl`，请参见 [文档](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/implementing/developer-tools/externalizer) 用于在AEMas a Cloud Service中使用Cloud Manager环境变量设置外部化器配置。
* 对于 `org.apache.sling.commons.log.LogManager.factory.config`，更改 OSGI 配置以将自定义的记录器发送到 `logs/error.log` 文件。请参阅 [文档](https://experienceleague.adobe.com/en/docs/experience-manager-learn/cloud-service/debugging/debugging-aem-as-a-cloud-service/logs) 用于指向 `logs/error.log` 文件。
* 联系 [AEM支持团队](https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html) 以澄清或解决问题。
