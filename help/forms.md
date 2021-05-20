---
title: 表单
description: 模式检测器代码帮助页
exl-id: ac28760b-b0ab-4082-b7ce-730cddc4ad83
source-git-commit: 4ad2fe0fa05b8252112df8a94958e65bb882482d
workflow-type: tm+mt
source-wordcount: '1228'
ht-degree: 0%

---

# [!DNL FORMS] {#form}

[!DNL Adobe Experience Manager Forms]

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_forms_overview"
>title="Forms。"
>abstract="Forms。代码可识别与从Adobe Experience Manager Forms作为Cloud Service迁移到Adobe Experience Manager Forms相关的潜在问题。 在迁移到Cloud Service之前，请审查可能的影响和相关风险并解决这些问题。"
>additional-url="https://experienceleague.adobe.com/docs/experience-manager-pattern-detection/table-of-contents/forms.html#implications-and-risks" text="可能的影响和风险"

`FORMS` 确定与从as a. [!DNL Adobe Experience Manager Forms]  [!DNL Adobe Experience Manager Form] [!DNL Cloud Service]在迁移到[!DNL Cloud Service]之前，请解决这些问题。

以下子类型可帮助您识别不同类型的问题：

* `modified.feature`:更新或修改了这些功能、资产或API以进行Cloud Service。在迁移到Cloud Service之前，请运行迁移实用程序以使这些功能和资产与Cloud Service兼容。
* `unavailable.feature`:您的环境具有一些不可用或从Cloud Service中删除的功能和资产。请勿将此类功能或资产迁移到Cloud Service环境。
* `unsupported.feature`:您的环境使用了一些Cloud Service上尚不支持的功能。请勿将此类功能或资产迁移到Cloud Service环境。 有关这些功能可用性的信息，请查看月度发行说明。
* `unsupported.api`:您的环境中有一些API尚不支持Cloud Service。在迁移到Cloud Service之前，请禁用、替换或从代码中删除这些API。 有关这些功能可用性的信息，请查看月度发行说明。

请参阅[可能的影响和风险](#implications-and-risks)和[可能的解决方案](#solutions)部分，以了解有关使某些功能和API与Cloud Service兼容所需的替换和其他操作的信息

## 可能的影响和风险{#implications-and-risks}

在迁移到[!DNL Adobe Experience Manager Forms as a Cloud Service]之前，请解决以下问题。 如果未解决下面所列的影响和风险，则某些功能在Cloud Service环境中无法按预期运行。

* 规则编辑器功能的代码编辑器功能不可用。 (CODE_EDITOR)

* 默认情况下，电子邮件支持（SMTP端口）处于禁用状态。 (EMAIL_SERVICE_CONFIGURATION)

* **[!UICONTROL 电子邮件PDF]**&#x200B;提交操作不可用。(EMAIL_PDF_SUBMIT_ACTION)

* 尚不支持基于XFA的自适应Forms。 (XFA_BASED_FORM、XDP_BASED_FORM)

* 在提交表单时，会立即调用提交操作，而不是等待所有签名者完成签名。 因此，发送给签名者的Adobe Sign协议PDF不可用于提交操作以供使用或处理。 (FORM_SIGN_INTEGRATION)

* “签名”步骤不可用。 (SIGNATURE_STEP)

* 验证步骤不可用。 (VERIFY_STEP)

* Forms Portal功能和&#x200B;**[!UICONTROL Forms Portal提交操作]**&#x200B;尚不可用。 (FORMS._PORTAL_SUBMISSION， FORMS._PORTAL， DRAFT_AUTO_SAVE， DRAFT_SAVE)

* **[!UICONTROL 提交到Forms Workflow]**&#x200B;提交操作不可用。 在[!DNL AEM 6.5 Forms]及更早版本中，“提交操作”用于将自适应表单数据提交到旧版[!DNL AEM Forms on JEE]工作流和LiveCycle Workflow。 (LC_WORKFLOW_SUBMISSION)

* 交互式通信功能不可用。  (FP_PROFILE_INTERACTIVE_COMMUNICATIONS)。

* **[!UICONTROL 另存为草]** 稿和 **[!UICONTROL 自动]** 保存自适应表单功能目前不受支持。(DRAFT_AUTO_SAVE， DRAFT_SAVE)

* 元数据折叠面板不可用。 (METADATA_ACCORDION_FORM_CONTAINER)

* 默认情况下，CAPTCHA组件现在使用Google reCAPTCHA服务来验证CAPTCHA。 已弃用使用Adobe Experience Manager验证CAPTCHA的选项。 (FORMS._CAPTCHA)

* [!DNL AEM Forms] 应用程序不可 [!DNL Cloud Services]用。(AEM_FORMS._APP)

* [文档](https://experienceleague.adobe.com/docs/experience-manager-65/forms/install-aem-forms/osgi-installation/install-configure-document-services.html?lang=en#deployment-topology) 服务步骤在AEM工作流中不可用。(WORKFLOW_DOCSERVICES)

## 可能的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_forms_guidance"
>title="实施指南"
>abstract="通过FORMS公开的信息。代码可以提供有关替换和使某些功能和API与Cloud Service兼容所需的其他操作的指导。 联系Adobe支持以获取帮助和说明"
>additional-url="https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud支持"

* 使用迁移实用程序将环境中的所有规则脚本转换为可重用函数。 您可以将可重用函数与可视化规则编辑器一起使用，以继续获取通过规则脚本获取的结果。 (CODE_EDITOR)

* 请与支持团队联系，以为您的环境启用电子邮件（打开SMTP端口）功能。 默认情况下，只启用传出HTTP和HTTPS连接。 （EMAIL_SERVICE_CONFIGURATION，电子邮件步骤）

* 使用&#x200B;**[!UICONTROL Email]**&#x200B;提交操作，而不是&#x200B;**[!UICONTROL Email PDF]**。 **[!UICONTROL Email]**&#x200B;提交操作提供了用于发送附件和附加记录文档(DoR)及电子邮件的选项。 (EMAIL_PDF_SUBMIT_ACTION)

* 提交的数据包含Adobe Sign协议ID。 您可以根据需要使用签署协议ID来检索签署协议PDF。  (FORM_SIGN_INTEGRATION)

* 从现有自适应表单中删除签名步骤。 配置您的自适应表单以使用[浏览器内签名体验](https://medium.com/adobetech/using-adobe-sign-to-e-sign-an-adaptive-form-heres-the-best-way-to-do-it-dc3e15f9b684)。 它显示Adobe Sign协议，即在提交自适应表单时，在浏览器中签署协议。 浏览器内签名体验有助于提供更快的签名体验，并为签名者节省时间。 (SIGNATURE_STEP)

* 在将此类表单移至[!DNL Cloud Service]环境之前，请从现有的自适应Forms中删除验证步骤。 (VERIFY_STEP)

* 修改现有自适应表单以使用[提交到REST端点](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html#submit-to-rest-endpoint)、[发送电子邮件](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html#send-email)、[使用表单数据模型](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html#submit-using-form-data-model)提交，以及[调用AEM工作流](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html#invoke-an-aem-workflow)提交操作。 Forms Portal和Forms Portal提交操作尚不可用。 有关这些功能可用性的信息，请查看月度发行说明。 (FORMS._PORTAL_SUBMISSION， FORMS._PORTAL)

* 您可以开发AEM工作流并修改现有的自适应表单，以使用[AEM Workflow](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html#invoke-an-aem-workflow)提交操作将数据发送到AEM工作流，而不是使用&#x200B;**[!UICONTROL 提交到Forms Workflow]**&#x200B;提交操作。 您可以开发一个自定义提交操作，以将数据、附件或记录文档(DoR)发送到LiveCycle进程，而不是使用[!UICONTROL 提交到Forms Workflow]。 (LC_WORKFLOW_SUBMISSION)

* 有关交互式通信功能可用性的信息，请查看月度发行说明。 在该功能不可用之前，请勿将您的交互式通信、信件和相关字典迁移到Cloud Service环境。 (FP_PROFILE_INTERACTIVE_COMMUNICATIONS)

* 在将&#x200B;**[!UICONTROL 另存为草稿]**&#x200B;和&#x200B;**[!UICONTROL 启用自动保存]**&#x200B;选项后，再将它们迁移到Cloud Service。 为Cloud Service发布Forms门户功能后，即可启用这些选项。 有关这些功能可用性的信息，请查看月度发行说明。 (DRAFT_AUTO_SAVE， DRAFT_SAVE)

* 没有替换元数据折叠面板。 在将表单迁移到Cloud Service之前，将其从表单中删除。(METADATA_ACCORDION_FORM_CONTAINER)

* 使用Google reCaptcha，而不是Adobe Experience Manager提供的CAPTCHA服务。 (FORMS._CAPTCHA)

* 自适应Forms提供响应式设计。 这些表单会根据底层设备更改外观、设计和交互性。 您可以在移动设备上继续使用自适应Forms。 有关[!DNL AEM Forms]应用程序可用性的信息，请查看月度发行说明。 (AEM_FORMS._APP)

* 请勿迁移使用文档服务工作流步骤的AEM工作流模型。 此外，在迁移表单之前，请不要迁移或更新将用户数据发送到使用文档服务工作流步骤的工作流模型的自适应Forms，也不要将提交操作更改为[受支持的](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html)。 (WORKFLOW_DOCSERVICES)

* 不能开箱即用地支持基于XFA的自适应Forms。 如果您打算使用基于XFA的自适应Forms，请联系Adobe支持，并提供用例和特定要求的详细信息。(XFA_BASED_FORM， XDP_BASED_FORM)

请联系[Adobe支持](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以获得说明或解决问题。
