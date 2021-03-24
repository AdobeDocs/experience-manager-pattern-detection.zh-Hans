---
title: UMI
description: 图案检测器代码帮助页
translation-type: tm+mt
source-git-commit: 4f94d4a1e0b8eb7bedbedba2c8a683f34655b527
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 0%

---


# UMI {#umi}

升级配置错误问题

## 背景 {#background}

`UMI` 标识对某些在升级时会导致问题的OSGi配置的修改，包括失败的升级或降低的功能。

将检查以下配置以进行修改：
* `org.apache.jackrabbit.oak.security.user.RandomAuthorizableNodeName`
* `org.apache.jackrabbit.oak.security.internal.SecurityProviderRegistration.requiredServicePids`
* `org.apache.sling.engine.impl.auth.SlingAuthenticator`
* `org.apache.sling.scripting.java.impl.JavaScriptEngineFactory`

## 可能的影响和风险{#implications-and-risks}

* 更改或删除配置可能导致以下问题：
   * 升级可能会卡住（例如`org.apache.jackrabbit.oak.security.user.RandomAuthorizableNodeName`丢失，但`org.apache.jackrabbit.oak.security.internal.SecurityProviderRegistration.requiredServicePids`中存在）。
   * 升级后可能会出现授权问题(`org.apache.sling.engine.impl.auth.SlingAuthenticator`)。
   * 某些功能可能无法按预期工作。 例如，更改`org.apache.sling.scripting.java.impl.JavaScriptEngineFactory`可能导致某些JSP文件无法编译，这最终会导致功能丢失。

## 可能的解决方案{#solutions}

* 请勿更改或删除上述四个配置。
* 如果配置已更改，则应将其恢复为预期值。 这些值在`UMI`消息中指示。
* 请联系我们的[AEM支持团队](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以获得说明或解决问题。
