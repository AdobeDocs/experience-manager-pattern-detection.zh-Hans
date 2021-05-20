---
title: 奥伊
description: 模式检测器代码帮助页
exl-id: 326144d6-705a-4b2c-ac35-403fd4c2259f
source-git-commit: 54b121a6ec29ba6ff6fb33b402f1821c34d0763f
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 3%

---

# 奥伊 {#oaui}

OAuth用户实例

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oaui_overview"
>title="OAuth用户实例"
>abstract="OAUI代码标识以下模式：至少有一个与OAuth相关的已配置用户需要正确迁移。 当rep:AuthorizableId节点下（以/home/user-path/user-node/oauth的形式）直接存在名为oauth的子节点时，将为用户配置OAuth"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html?lang=zh-Hans" text="AEM as aCloud Service — 发行说明"

`OAUI` 标识以下模式：至少有一个与OAuth相关的已配置用户需要正确迁移。

当`rep:AuthorizableId`节点下`/home/user-path/user-node/oauth`形式的节点下有名为`oauth`的子节点时，将为用户配置OAuth。

例如：`/home/users/ims/0001/R80w6XaUCBq3jHE47xDN/oauth`。

## 可能的影响和风险{#implications-and-risks}

* 使用OAuth配置的外部用户在使用以下过程重新配置之前将无法登录创作/发布实例。

## 可能的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oaui_guidance"
>title="实施指南"
>abstract="配置了OAuth的外部用户在重新配置为与AEM as a A A Compatible之前无法登录创作/发布实例。 AEM as a Cloud Service仅为作者、管理员和开发人员用户提供IMS身份验证支持，并为发布环境提供基于SAML的集成。 联系Adobe支持以获取帮助和说明"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/security/ims-support.html" text="IMS支持 — AEM as aCloud Service"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/personalization/user-and-group-sync-for-publish-tier.html?lang=en#integration-with-an-idp" text="SAML集成 — 发布"

* 请联系您的Adobe代表以讨论用户迁移选项。
* 请联系我们的[AEM支持团队](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以获得说明或解决问题。
