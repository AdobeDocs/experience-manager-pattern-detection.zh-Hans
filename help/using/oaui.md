---
title: OAUI
description: 模式检测器代码帮助页面……
exl-id: 326144d6-705a-4b2c-ac35-403fd4c2259f
source-git-commit: 982ad1a6f43a29f2ee2284219757c8fc11b31ce0
workflow-type: tm+mt
source-wordcount: '230'
ht-degree: 47%

---

# OAUI {#oaui}

OAuth 用户实例

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oaui_overview"
>title="OAuth 用户实例"
>abstract="OAUI 代码标识的模式是，至少一个与 OAuth 相关的已配置用户需要正确的迁移。当名为 oauth 的子节点直接位于 rep:AuthorizableId 节点下且形式为 /home/user-path/user-node/oauth 时，为用户配置 OAuth"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/release-notes/release-notes/release-notes-current" text="AEM as a Cloud Service - 发行说明"

OAUI标识的模式是，至少一个与OAuth相关的已配置用户需要正确的迁移。

当名为 `oauth` 的子节点直接位于 `rep:AuthorizableId` 节点下且形式为 `/home/user-path/user-node/oauth` 时，为用户配置 OAuth。

示例为：`/home/users/ims/0001/R80w6XaUCBq3jHE47xDN/oauth`。

## 可能的后果和风险 {#implications-and-risks}

* 在使用以下过程重新配置之前，使用OAuth配置的外部用户无法登录author/publish实例。

## 可采用的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oaui_guidance"
>title="实施指南"
>abstract="在重新配置为与AEMas a Cloud Service兼容之前，使用OAuth配置的外部用户无法登录author/publish实例。 AEMas a Cloud Service仅为作者、管理员和开发用户提供IMS身份验证支持，为发布环境提供基于SAML的集成。 请联系 Adobe 支持部门获取帮助及说明"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/security/ims-support" text="IMS 支持 - AEM as a Cloud Service"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/sites/authoring/personalization/user-and-group-sync-for-publish-tier#integration-with-an-idp" text="SAML 集成 - 发布"

* 如果您必须讨论用户迁移的选项，请联系您的Adobe代表。
* 联系 [AEM支持团队](https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html) 以澄清或解决问题。
