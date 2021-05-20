---
title: UMI
description: 模式检测器代码帮助页
exl-id: 04efa760-61f5-4690-8b4e-89fa756c5b64
source-git-commit: 76dc944f1592118920f89c513faf456b8aa443a9
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 3%

---

# UMI {#umi}

升级配置错误问题

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_umi_overview"
>title="升级配置错误问题"
>abstract="UMI标识对某些OSGi配置的修改，这些修改在升级时会导致问题，包括升级失败或功能减少。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/aem-cloud-changes.html" text="显着更改 — AEM作为Cloud Service"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html?lang=zh-Hans" text="AEM as aCloud Service — 发行说明"

`UMI` 标识对某些OSGi配置的修改，这些修改在升级时会导致问题，包括升级失败或功能减少。

将检查以下配置以进行修改：
* `org.apache.jackrabbit.oak.security.user.RandomAuthorizableNodeName`
* `org.apache.jackrabbit.oak.security.internal.SecurityProviderRegistration.requiredServicePids`
* `org.apache.sling.engine.impl.auth.SlingAuthenticator`
* `org.apache.sling.scripting.java.impl.JavaScriptEngineFactory`

## 可能的影响和风险{#implications-and-risks}

* 更改或删除配置可能会导致以下问题：
   * 升级可能卡住（例如`org.apache.jackrabbit.oak.security.user.RandomAuthorizableNodeName`缺失，但出现在`org.apache.jackrabbit.oak.security.internal.SecurityProviderRegistration.requiredServicePids`中）。
   * 升级后可能会出现授权问题(`org.apache.sling.engine.impl.auth.SlingAuthenticator`)。
   * 某些功能可能无法按预期工作。 例如，更改`org.apache.sling.scripting.java.impl.JavaScriptEngineFactory`可能会导致某些JSP文件无法编译，最终导致功能丢失。

## 可能的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_umi_guidance"
>title="实施指南"
>abstract="最佳做法是检查您当前的配置，并还原对上述配置所做的任何更改，以避免将来出现任何升级问题。 联系Adobe支持以获取帮助和说明"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud支持"

* 请勿更改或删除上述四个配置。
* 如果配置已更改，则应将其恢复为预期值。 这些值在`UMI`消息中指示。
* 请联系我们的[AEM支持团队](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以获得说明或解决问题。
