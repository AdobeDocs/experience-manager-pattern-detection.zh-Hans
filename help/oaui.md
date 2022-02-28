---
title: OAUI
description: Pattern Detector 代码帮助页面
exl-id: 326144d6-705a-4b2c-ac35-403fd4c2259f
source-git-commit: 54b121a6ec29ba6ff6fb33b402f1821c34d0763f
workflow-type: ht
source-wordcount: '256'
ht-degree: 100%

---

# OAUI {#oaui}

OAuth 用户实例

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oaui_overview"
>title="OAuth 用户实例"
>abstract="OAUI 代码标识的模式是，至少一个与 OAuth 相关的已配置用户需要正确的迁移。当名为 oauth 的子节点直接位于 rep:AuthorizableId 节点下且形式为 /home/user-path/user-node/oauth 时，为用户配置 OAuth"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html" text="AEM as a Cloud Service - 发行说明"

`OAUI` 代码标识的模式是，至少一个与 OAuth 相关的已配置用户需要正确的迁移。

当名为 `oauth` 的子节点直接位于 `rep:AuthorizableId` 节点下且形式为 `/home/user-path/user-node/oauth` 时，为用户配置 OAuth。

示例为：`/home/users/ims/0001/R80w6XaUCBq3jHE47xDN/oauth`。

## 可能的后果和风险 {#implications-and-risks}

* 在使用以下过程重新配置之前，使用 OAuth 配置的外部用户无法登录 author/publish 实例。

## 可采用的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oaui_guidance"
>title="实施指南"
>abstract="在重新配置以与 AEM as a Cloud Service 兼容之前，使用 OAuth 配置的外部用户无法登录 author/publish 实例。AEM as a Cloud Service 仅为作者、管理员和开发用户提供 IMS 身份验证支持，为发布环境提供基于 SAML 的集成。请联系 Adobe 支持部门获取帮助或说明"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/security/ims-support.html" text="IMS 支持 - AEM as a Cloud Service"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/personalization/user-and-group-sync-for-publish-tier.html?lang=zh-Hans#integration-with-an-idp" text="SAML 集成 - 发布"

* 请与您的 Adobe 代表联系，讨论用户迁移的选项。
* 请联系我们的 [AEM 支持团队](https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html)获取说明或解决问题。
