---
title: UMI
description: Pattern Detector 代码帮助页面
exl-id: 04efa760-61f5-4690-8b4e-89fa756c5b64
source-git-commit: f1e833bea35ef3b412936d529b14bff6f1cb35c1
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 100%

---

# UMI {#umi}

升级配置错误问题

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_umi_overview"
>title="升级配置错误问题"
>abstract="UMI 标识对特定 OSGi 配置的修改，这些修改在升级时会导致问题，包括升级失败或者功能减少。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html?lang=zh-Hans" text="显著更改 - AEM as a Cloud Service"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html?lang=zh-Hans" text="AEM as a Cloud Service - 发行说明"

`UMI` 标识对特定 OSGi 配置的修改，这些修改在升级时会导致问题，包括升级失败或者功能减少。

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
   * 特定功能可能无法正常工作。例如，更改 `org.apache.sling.scripting.java.impl.JavaScriptEngineFactory` 会导致一些 JSP 文件未编译，这最终会导致功能丢失。
   * 在 AEM as a Cloud Service 中由 Cloud Manager 环境变量设置了外部化器配置 `com.day.cq.commons.impl.ExternalizerImpl` 的值。
   * AEM as a Cloud Service 不支持自定义日志文件。将无法从 AEM as a Cloud Service 访问写入自定义命名的日志的日志内容。

## 可采用的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_umi_guidance"
>title="实施指南"
>abstract="最佳实践是审查当前配置，恢复对所述配置进行的更改以避免任何以后的升级问题。请联系 Adobe 支持部门获取帮助或说明"
>additional-url="https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支持"

* 请勿更改或移除以上提及的四个配置。
   * 如果出现下列违规情况：\
     “缺少 OSGi 配置‘xyz-configuration’的必需属性：‘[属性 1,属性 2...]’。”\
     由于这些 OSGi 配置是 OOTB，可能从未通过 OSGi 配置过滤器修改/保存，因此请确认这些删除是否合法。
* 如果配置已更改，它们应恢复到其预期值。这些值在 `UMI` 消息中指明。
* 对于 `com.day.cq.commons.impl.ExternalizerImpl`，请参阅关于在 AEM as a Cloud Service 中使用 Cloud Manager 环境变量设置外部化器配置的[文档](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developer-tools/externalizer.html?lang=en)。
* 对于 `org.apache.sling.commons.log.LogManager.factory.config`，更改 OSGI 配置以将自定义的记录器发送到 `logs/error.log` 文件。请参阅关于指向 `logs/error.log` 文件的[文档](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/debugging/debugging-aem-as-a-cloud-service/logs.html)。
* 请联系我们的 [AEM 支持团队](https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html)以获得澄清或解决关切。
