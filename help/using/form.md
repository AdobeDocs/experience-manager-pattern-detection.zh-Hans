---
title: FORM
description: Pattern Detector 代码帮助页面
exl-id: ac28760b-b0ab-4082-b7ce-730cddc4ad83
source-git-commit: f1e833bea35ef3b412936d529b14bff6f1cb35c1
workflow-type: ht
source-wordcount: '1110'
ht-degree: 100%

---

# [!DNL FORMS] {#form}

[!DNL Adobe Experience Manager Forms]

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_forms_overview"
>title="FORMS"
>abstract="FORMS 代码标识与从 Adobe Experience Manager Forms 迁移到 Adobe Experience Manager Forms as a Cloud Service 相关的潜在问题。审查可能的相关后果和风险，并在迁移到 Cloud Service 之前解决这些问题。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-pattern-detection/table-of-contents/forms.html#implications-and-risks" text="可能的后果和风险"

`FORMS` 标识与从 [!DNL Adobe Experience Manager Forms] 迁移到 [!DNL Adobe Experience Manager Form]s as a [!DNL Cloud Service] 相关的潜在问题。请在迁移到 [!DNL Cloud Service] 之前解决这些问题。

以下子类型帮助您标识问题的不同类型：

* `modified.feature`：这些功能、资源或 API 已经针对 Cloud Service 进行了更新或修改。在迁移到 Cloud Service 之前，请运行迁移实用程序，使这些功能和资源与 Cloud Service 兼容。
* `unavailable.feature`：您的环境具有不可用或者已从 Cloud Service 中删除的功能和资源。请勿将此类功能或资源迁移到 Cloud Service 环境。
* `unsupported.feature`：您的环境使用了一些 Cloud Service 上尚不支持的功能。请勿将此类功能或资源迁移到 Cloud Service 环境。有关功能可用性的信息，请查看每月发行说明。
* `unsupported.api`：您的环境具有一些 Cloud Service 上尚不支持的 API。在迁移到 Cloud Service 之前，请在代码中禁用、替换或者删除这些 API。有关功能可用性的信息，请查看每月发行说明。

有关进行替换以及使这些功能和 API 与 Cloud Service 兼容所需其他操作的信息，请参阅[可能的后果和风险](#implications-and-risks)和[可采用的解决方案](#solutions)部分

## 可能的后果和风险 {#implications-and-risks}

请在迁移到 [!DNL Adobe Experience Manager Forms as a Cloud Service] 之前解决以下问题。如果未能解决以下列出的后果和风险，一些功能在 Cloud Service 环境中将无法正常工作。

* 规则编辑器功能的代码编辑器功能不可用。(CODE_EDITOR)

* 默认情况下禁用了电子邮件支持（SMTP 端口）。(EMAIL_SERVICE_CONFIGURATION)

* **[!UICONTROL 电子邮件 PDF]** 提交操作不可用。(EMAIL_PDF_SUBMIT_ACTION)

* 尚不支持基于 XFA 的自适应表单。(XFA_BASED_FORM, XDP_BASED_FORM)

* 在表单提交后立即调用提交操作，而不是等待所有签名者完成签名。因此，发送给签名者的 Adobe Sign 协议 PDF 不可再由提交操作使用或处理。(FORM_SIGN_INTEGRATION)

* 签名步骤不可用。(SIGNATURE_STEP)

* 验证步骤不可用。(VERIFY_STEP)

* **[!UICONTROL 提交到 Forms Workflow]** 提交操作不可用。在 AEM 6.5 Forms 和更低版本中，使用提交操作将自适应表单提交到旧版 AEM Forms on JEE Workflow 和 LiveCycle Workflow。(LC_WORKFLOW_SUBMISSION)

* 交互式通信功能不可用。(FP_PROFILE_INTERACTIVE_COMMUNICATIONS)

* 元数据折叠不可用。(METADATA_ACCORDION_FORM_CONTAINER)

* 默认情况下，CAPTCHA 组件现在使用 Google reCAPTCHA 服务来验证 CAPTCHA。使用 Adobe Experience Manager 验证 CAPTCHA 的选项已弃用。(FORMS_CAPTCHA)

* [!DNL AEM Forms] 应用程序不可用于 [!DNL Cloud Services]。(AEM_FORMS_APP)

* [文档服务](https://experienceleague.adobe.com/docs/experience-manager-65/forms/install-aem-forms/osgi-installation/install-configure-document-services.html?lang=zh-Hans#deployment-topology)步骤在 AEM Workflow 中不可用。(WORKFLOW_DOCSERVICES)

## 可采用的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_forms_guidance"
>title="实施指南"
>abstract="通过 FORMS 代码公开的信息可提供指南，说明了进行替换以及使这些功能和 API 与 Cloud Service 兼容所需的其他操作。请联系 Adobe 支持部门获取帮助或说明"
>additional-url="https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支持"

* 使用迁移实用程序将环境上的所有规则脚本转换为可重用的函数。您可以将可重用的函数与 Visual 规则编辑器结合使用，以继续获取通过规则脚本获取的结果。(CODE_EDITOR)

* 联系支持团队，为您的环境启用电子邮件（打开 SMTP 端口）功能。默认情况下仅启用传出 HTTP 和 HTTPS 连接。(EMAIL_SERVICE_CONFIGURATION, Email step)

* 使用&#x200B;**[!UICONTROL 电子邮件]**&#x200B;提交操作而非 **[!UICONTROL 电子邮件 PDF]**。**[!UICONTROL 电子邮件]**&#x200B;提交操作提供了选项，用于发送附件和使用电子邮件附加记录文档 (DoR)。(EMAIL_PDF_SUBMIT_ACTION)

* 提交包含 Adobe Sign 协议 ID 的数据。如果需要，您可以使用 Sign 协议 ID 检索 Sign 协议 PDF。(FORM_SIGN_INTEGRATION)

* 从现有自适应表单中删除签名步骤。配置自适应表单用于[浏览器中签名体验](https://medium.com/adobetech/using-adobe-sign-to-e-sign-an-adaptive-form-heres-the-best-way-to-do-it-dc3e15f9b684)。它显示 Adobe Sign 协议，以在自适应表单提交时在浏览器中签名。浏览器中的签名体验有助于提供更快的签名体验，节省签名者的时间。(SIGNATURE_STEP)

* 先从现有自适应表单中删除验证步骤，然后再将此类表单迁移到 [!DNL Cloud Service] 环境。(VERIFY_STEP)

* 修改现有自适应表单以使用[提交到 REST 端点](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html#submit-to-rest-endpoint)、[发送电子邮件](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html#send-email)、[使用表单数据模型提交](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html#submit-using-form-data-model)和[调用 AEM Workflow](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html#invoke-an-aem-workflow) 提交操作。

* 您可以开发 AEM Workflow 并修改现有自适应表单，以使用 [AEM Workflow](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html#invoke-an-aem-workflow) 提交操作将数据发送到 AEM Workflow，而不是使用&#x200B;**[!UICONTROL 提交到 Forms Workflow]** 提交操作。您可以开发自定义提交操作来将数据、附件或者记录文档 (DoR) 发送到 LiveCycle 流程，而不是使用[!UICONTROL 提交到 Forms Workflow]。(LC_WORKFLOW_SUBMISSION)

* 有关交互式通信功能可用性的信息，请查看每月发行说明。在功能不可用前，请勿将交互式通信、信函和相关字典迁移到 Cloud Service 环境。(FP_PROFILE_INTERACTIVE_COMMUNICATIONS)

* 元数据折叠没有替换项。在迁移到 Cloud Service 之前，请将其从表单中删除。(METADATA_ACCORDION_FORM_CONTAINER)

* 使用 Google reCaptcha 而非 Adobe Experience Manager 提供的 CAPTCHA 服务。(FORMS_CAPTCHA)

* 请勿迁移使用文档服务工作流步骤的 AEM Workflow 模型。此外，对于自适应表单，如果将用户数据发送到使用文档服务工作流的工作流模型，请勿进行迁移或更新，或者在迁移表单之前将提交操作更改为[支持的操作](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html)。(WORKFLOW_DOCSERVICES)

* 自适应表单提供了响应式设计。这些表单会根据底层设备更改外观、设计和交互性。您可以在移动设备上继续使用自适应表单。有关 [!DNL AEM Forms] 应用程序可用性的信息，请查看每月发行说明。(AEM_FORMS_APP)

* 对基于 XFA 的自适应表单的支持并非现成可用。如果您需要使用基于 XFA 的自适应表单，请联系 Adobe 支持部门并提供您用例的详细信息和具体要求。(XFA_BASED_FORM, XDP_BASED_FORM)

请联系 [Adobe 支持部门](https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html)获取说明或解决问题。
