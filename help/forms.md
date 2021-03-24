---
title: Forms。
description: 图案检测器代码帮助页
translation-type: tm+mt
source-git-commit: a6ba6e93c89644160650882ecbf17028bec35068
workflow-type: tm+mt
source-wordcount: '946'
ht-degree: 0%

---


# [!DNL FORMS] {#forms}

[!DNL Adobe Experience Manager Forms]

## 背景 {#background}

`FORMS` 确定与从Adobe Experience Manager Forms作为Cloud Service迁移到Adobe Experience Manager Forms相关的潜在问题。在迁移到Cloud Service之前解决这些问题。

以下子类型可帮助您确定不同类型的问题：

* `modified.feature`:这些功能、资源或API已更新或修改以用于Cloud Service。在迁移到Cloud Service之前，请运行迁移实用程序以使这些功能和资源与Cloud Service兼容。
* `unavailable.feature`:您的环境具有不可用或从Cloud Service中删除的功能和资产。请勿将此类功能或资产迁移到Cloud Service环境。
* `unsupported.feature`:您的环境使用某些功能但不支持Cloud Service。请勿将此类功能或资产迁移到Cloud Service环境。 请关注月度发行说明，了解功能的可用性。
* `unsupported.api`:您的环境有一些API，但该Cloud Service尚不支持。在迁移到Cloud Service之前，请禁用、替换这些API，或从您的代码中删除这些API。 请关注月度发行说明，了解功能的可用性。

请参见[可能的含义和风险](#implications-and-risks)和[可能的解决方案](#solutions)部分，了解使某些功能和API与Cloud Service兼容所需的替换和其他操作

## 可能的影响和风险{#implications-and-risks}

在作为Cloud Service迁移到Adobe Experience Manager Forms之前，请解决以下问题。 当未解决以下所列的影响和风险时，某些功能不能像Cloud Service环境中预期的那样发挥作用。

* 规则编辑器功能的代码编辑器功能不可用。 (CODE_EDITOR)

* 默认情况下，电子邮件支持（SMTP端口）处于禁用状态。 (EMAIL_SERVICE_CONFIGURATION)

* **[!UICONTROL 电子邮件PDF]**&#x200B;提交操作不可用。(EMAIL_PDF_SUBMIT_ACTION)

* 尚不支持基于XDP的自适应表单。 (XDP_BASED_FORM)

* 提交表单时会立即调用提交操作，而不是等待所有签名者完成签名。 因此，自适应表单签名文档(发送给签名者的Adobe Sign协议PDF)不可用于提交操作以供使用或处理。 (FORM_SIGN_INTEGRATION)

* 签名步骤不可用。 (SIGNATURE_STEP)

* 验证步骤不可用。 (VERIFY_STEP)

* Forms Portal功能和&#x200B;**[!UICONTROL Forms Portal提交操作]**&#x200B;不可用。 不能使用Forms Portal列表表单、保存草稿或显示提交的表单。 无法将提交到自适应表单的(使用&#x200B;**[!UICONTROL Forms Portal提交操作]**)数据发送到Forms Portal。 [!UICONTROL 另存为] 草稿和 [!UICONTROL 自动] 保存自适应表单功能目前不受支持。(FORMS._PORTAL_SUBMISSION、FORMS._PORTAL、DRAFT_AUTO_SAVE、DRAFT_SAVE)

* **[!UICONTROL 提交到Forms工作流]**&#x200B;提交操作不可用。 在AEM 6.5 Forms和先前版本上，提交操作用于在JEE工作流和LiveCycle Workflow上将自适应表单数据提交到旧版AEM Forms。 (LC_WORKFLOW_SUBMISSION)

* 交互通信功能不可用。  (FP_用户档案_INTERACTIVE_COMMUNICATIONS)。

* **[!UICONTROL 另存为]** 草稿和 **[!UICONTROL 自动]** 保存自适应表单功能目前不受支持。(DRAFT_AUTO_SAVE，DRAFT_SAVE)

* 元数据折叠面板不可用。 (METADATA_ACCORDION_FORM_容器)

* 默认情况下，CAPTCHA组件现在使用Google reCAPTCHA服务验证CAPTCHA。 使用Adobe Experience Manager验证CAPTCHA的选项不可用。 (FORMS._CAPTCHA)

## 可能的解决方案{#solutions}

* 使用迁移实用程序将环境上的所有规则脚本转换为可重用的函数。 您可以将可重用函数与可视规则编辑器一起使用，以继续获取通过规则脚本获得的结果。 (CODE_EDITOR)

* 请与支持团队联系，为您的环境启用电子邮件（打开SMTP端口）功能。 默认情况下，仅启用传出HTTP和HTTPS连接。 (EMAIL_SERVICE_CONFIGURATION)

* 使用&#x200B;**[!UICONTROL Email]**&#x200B;提交操作而不是&#x200B;**[!UICONTROL Email PDF]**。 **[!UICONTROL Email]**&#x200B;提交操作提供了用于发送附件和将记录(DoR)附加到电子邮件的文档的选项。 (EMAIL_PDF_SUBMIT_ACTION)

* 请勿将基于XDP的自适应表单迁移到Cloud Service环境。 请关注月度发行说明，了解功能的可用性。 (XDP_BASED_FORM)

* 提交的数据包含Sign协议ID。 如果需要，您可以使用签名协议ID来检索签名协议PDF。  (FORM_SIGN_INTEGRATION)

* 在同一窗口中，将自适应表单中的签名步骤替换为对自适应表单帖子提交进行签名的选项。 它可以帮助您继续提供[浏览器内签名体验](https://medium.com/adobetech/using-adobe-sign-to-e-sign-an-adaptive-form-heres-the-best-way-to-do-it-dc3e15f9b684)。 (SIGNATURE_STEP)

* 在将现有自适应表单移至Cloud Service环境之前，从现有自适应表单中删除验证步骤。 (VERIFY_STEP)

* 没有替代&#x200B;**[!UICONTROL Forms Portal提交操作]**&#x200B;的选项。 在为Cloud Service发布Forms门户功能后，即可使用此提交操作。 请关注月度发行说明，了解功能的可用性。 (FORMS._PORTAL_SUBMISSION， FORMS._PORTAL)

* 没有替代的提交操作可提交到&#x200B;**[!UICONTROL 提交到Forms工作流]**&#x200B;提交操作。 您可以开发自定义提交操作，以将数据、附件或记录文档(DoR)发送到LiveCycle进程。 (LC_WORKFLOW_SUBMISSION)

* 请勿将您的交互通信、字母和相关词典迁移到Cloud Service环境。 (FP_用户档案_INTERACTIVE_COMMUNICATIONS)

* 在将自适应表单迁移到Cloud Service之前，禁用自适应表单中的&#x200B;**[!UICONTROL 另存为草稿]**&#x200B;和&#x200B;**[!UICONTROL 启用自动保存]**&#x200B;选项。 为Cloud Service发布Forms门户功能后，即可启用这些选项。 请关注月度发行说明，了解功能的可用性。 (DRAFT_AUTO_SAVE，DRAFT_SAVE)

* 无法替换元数据折叠面板。 在将表单迁移到Cloud Service之前，从表单中删除它。(METADATA_ACCORDION_FORM_容器)

* 使用Google reCaptcha，而不是Adobe Experience Manager提供的CAPTCHA服务。 (FORMS._CAPTCHA)

联系[Adobe支持](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以获得说明或解决问题。
