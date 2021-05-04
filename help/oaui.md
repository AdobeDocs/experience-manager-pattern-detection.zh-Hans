---
title: 奥伊
description: 图案检测器代码帮助页
exl-id: 326144d6-705a-4b2c-ac35-403fd4c2259f
translation-type: tm+mt
source-git-commit: 54b121a6ec29ba6ff6fb33b402f1821c34d0763f
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 3%

---

# OAUI {#oaui}

OAuth用户实例

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oaui_overview"
>title="OAuth用户实例"
>abstract="OAUI代码标识一种模式，其中至少有一个与OAuth相关的已配置用户需要正确迁移。 如果在/home/user-path/user-node/oauth形式的rep:AuthorizableId节点下直接存在名为oauth的子节点，则为用户配置OAuth"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html?lang=zh-Hans" text="AEM as a Cloud Service — 发行说明"

`OAUI` 标识至少有一个与OAuth相关的配置用户需要正确迁移的模式。

当`rep:AuthorizableId`节点下面有名为`oauth`的子节点（以`/home/user-path/user-node/oauth`的形式）时，将为用户配置OAuth。

例如：`/home/users/ims/0001/R80w6XaUCBq3jHE47xDN/oauth`。

## 可能的影响和风险{#implications-and-risks}

* 使用OAuth配置的外部用户在按照以下过程重新配置之前将无法登录创作/发布实例。

## 可能的解决方案{#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_oaui_guidance"
>title="实施指南"
>abstract="配置了OAuth的外部用户在重新配置为与AEM兼容为Cloud Service之前无法登录创作/发布实例。 AEM作为Cloud Service优惠，仅对作者、管理员和开发人员用户和基于SAML的发布环境集成支持IMS身份验证。 联系Adobe支持以获得帮助和说明"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/security/ims-support.html" text="IMS支持 — AEM作为Cloud Service"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/personalization/user-and-group-sync-for-publish-tier.html?lang=en#integration-with-an-idp" text="SAML集成 — 发布"

* 请与Adobe代表联系，讨论用户迁移选项。
* 请联系我们的[AEM支持团队](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以获得说明或解决问题。
