---
title: 表单
description: 图案检测器代码帮助页
translation-type: tm+mt
source-git-commit: aa44c3ce87496f412191000f1980a7ebbde386cd
workflow-type: tm+mt
source-wordcount: '1143'
ht-degree: 0%

---


# [!DNL FORMS] {#form}

[!DNL Adobe Experience Manager Forms]

## 背景 {#background}

`FORMS` 确定与从迁移到的 [!DNL Adobe Experience Manager Forms] 潜 [!DNL Adobe Experience Manager Form]在问题， [!DNL Cloud Service]在迁移到[!DNL Cloud Service]之前解决这些问题。

以下子类型可帮助您确定不同类型的问题：

* `modified.feature`:这些功能、资源或API已更新或修改以用于Cloud Service。在迁移到Cloud Service之前，请运行迁移实用程序以使这些功能和资源与Cloud Service兼容。
* `unavailable.feature`:您的环境具有不可用或从Cloud Service中删除的功能和资产。请勿将此类功能或资产迁移到Cloud Service环境。
* `unsupported.feature`:您的环境使用某些功能但不支持Cloud Service。请勿将此类功能或资产迁移到Cloud Service环境。 请关注月度发行说明，了解功能的可用性。
* `unsupported.api`:您的环境有一些API，但该Cloud Service尚不支持。在迁移到Cloud Service之前，请禁用、替换这些API，或从您的代码中删除这些API。 请关注月度发行说明，了解功能的可用性。

请参见[可能的含义和风险](#implications-and-risks)和[可能的解决方案](#solutions)部分，了解使某些功能和API与Cloud Service兼容所需的替换和其他操作

## 可能的影响和风险{#implications-and-risks}

在迁移到[!DNL Adobe Experience Manager Forms as a Cloud Service]之前，请解决以下问题。 当未解决以下所列的影响和风险时，某些功能不能像Cloud Service环境中预期的那样发挥作用。

* 规则编辑器功能的代码编辑器功能不可用。 (CODE_EDITOR)

* 默认情况下，电子邮件支持（SMTP端口）处于禁用状态。 (EMAIL_SERVICE_CONFIGURATION)

* **[!UICONTROL 电子邮件PDF]**&#x200B;提交操作不可用。(EMAIL_PDF_SUBMIT_ACTION)

* 尚不支持基于XFA的自适应Forms。 (XFA_BASED_FORM、XDP_BASED_FORM)

* 提交表单时会立即调用提交操作，而不是等待所有签名者完成签名。 因此，发送给签名者的Adobe Sign协议PDF不可用于使用或处理提交操作。 (FORM_SIGN_INTEGRATION)

* 签名步骤不可用。 (SIGNATURE_STEP)

* 验证步骤不可用。 (VERIFY_STEP)

* Forms Portal功能和&#x200B;**[!UICONTROL Forms Portal提交操作]**&#x200B;尚不可用。 (FORMS._PORTAL_SUBMISSION、FORMS._PORTAL、DRAFT_AUTO_SAVE、DRAFT_SAVE)

* **[!UICONTROL 提交至Forms Workflow]**&#x200B;提交操作不可用。 在[!DNL AEM 6.5 Forms]和先前版本中，使用提交操作将自适应表单数据提交到旧版[!DNL AEM Forms on JEE]工作流和LiveCycle Workflow。 (LC_WORKFLOW_SUBMISSION)

* 交互通信功能不可用。  (FP_用户档案_INTERACTIVE_COMMUNICATIONS)。

* **[!UICONTROL 另存为]** 草稿和 **[!UICONTROL 自动]** 保存自适应表单功能目前不受支持。(DRAFT_AUTO_SAVE，DRAFT_SAVE)

* 元数据折叠面板不可用。 (METADATA_ACCORDION_FORM_容器)

* 默认情况下，CAPTCHA组件现在使用Google reCAPTCHA服务验证CAPTCHA。 已弃用使用Adobe Experience Manager验证CAPTCHA的选项。 (FORMS._CAPTCHA)

* [!DNL AEM Forms] 应用程序不可 [!DNL Cloud Services]用。(AEM_FORMS._APP)

* [文档](https://experienceleague.adobe.com/docs/experience-manager-65/forms/install-aem-forms/osgi-installation/install-configure-document-services.html?lang=en#deployment-topology) 服务步骤在AEM工作流中不可用。(WORKFLOW_DOCSERVICES)

## 可能的解决方案{#solutions}

* 使用迁移实用程序将环境上的所有规则脚本转换为可重用的函数。 您可以将可重用函数与可视规则编辑器一起使用，以继续获取通过规则脚本获得的结果。 (CODE_EDITOR)

* 请与支持团队联系，为您的环境启用电子邮件（打开SMTP端口）功能。 默认情况下，仅启用传出HTTP和HTTPS连接。 （EMAIL_SERVICE_CONFIGURATION，电子邮件步骤）

* 使用&#x200B;**[!UICONTROL 电子邮件]**&#x200B;提交操作，而不是&#x200B;**[!UICONTROL 电子邮件PDF]**。 **[!UICONTROL 电子邮件]**&#x200B;提交操作提供用于发送附件和附加记录文档(DoR)和电子邮件的选项。 (EMAIL_PDF_SUBMIT_ACTION)

* 提交的数据包含Adobe Sign协议ID。 如果需要，您可以使用签名协议ID来检索签名协议PDF。  (FORM_SIGN_INTEGRATION)

* 从现有自适应表单中删除签名步骤。 配置Adaptive Form以使用[浏览器内签名体验](https://medium.com/adobetech/using-adobe-sign-to-e-sign-an-adaptive-form-heres-the-best-way-to-do-it-dc3e15f9b684)。 它显示Adobe Sign协议，以便在提交自适应表单时在浏览器中签署协议。 浏览器内签名体验有助于为签名者提供更快的签名体验并节省时间。 (SIGNATURE_STEP)

* 在将这些表单移至[!DNL Cloud Service]环境之前，请从现有Adaptive Forms中删除验证步骤。 (VERIFY_STEP)

* 修改现有自适应表单以使用[提交到REST端点](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html#submit-to-rest-endpoint)、[发送电子邮件](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html#send-email)、[使用表单数据模型](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html#submit-using-form-data-model)提交和[调用AEM工作流](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html#invoke-an-aem-workflow)提交操作。 Forms Portal和Forms Portal提交操作尚不可用。 请关注月度发行说明，了解功能的可用性。 (FORMS._PORTAL_SUBMISSION， FORMS._PORTAL)

* 您可以开发AEM工作流并修改现有的自适应表单以使用[AEM工作流](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html#invoke-an-aem-workflow)提交操作将数据发送到AEM工作流，而不是使用&#x200B;**[!UICONTROL 提交到Forms Workflow]**&#x200B;提交操作。 您可以开发自定义提交操作，以将数据、附件或记录文档(DoR)发送到LiveCycle进程，而不是使用[!UICONTROL 提交到Forms Workflow]。 (LC_WORKFLOW_SUBMISSION)

* 要了解交互通信功能的可用性，请关注月度发行说明。 在该功能不可用之前，请勿将您的交互通信、字母和相关词典迁移到Cloud Service环境。 (FP_用户档案_INTERACTIVE_COMMUNICATIONS)

* 在将&#x200B;**[!UICONTROL 文件迁移到Cloud Service之前，请禁用Adaptive Forms中的另存为草稿]**&#x200B;和&#x200B;**[!UICONTROL 启用自动保存]**&#x200B;选项。 为Cloud Service发布Forms门户功能后，即可启用这些选项。 请关注月度发行说明，了解功能的可用性。 (DRAFT_AUTO_SAVE，DRAFT_SAVE)

* 无法替换元数据折叠面板。 在将表单迁移到Cloud Service之前，从表单中删除它。(METADATA_ACCORDION_FORM_容器)

* 使用Google reCaptcha，而不是Adobe Experience Manager提供的CAPTCHA服务。 (FORMS._CAPTCHA)

* 自适应Forms优惠响应式设计。 这些表单会根据底层设备更改外观、设计和交互性。 您可以在移动设备上继续使用Adaptive Forms，同时在月度发行说明中关注[!DNL AEM Forms]应用程序的可用性。 (AEM_FORMS._APP)

* 请勿迁移使用文档服务工作流步骤的AEM工作流模型。 此外，请勿迁移或更新将用户数据发送到使用文档服务工作流步骤的工作流模型的自适应Forms，或在迁移表单之前将提交操作更改为[支持的](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html)操作。 (WORKFLOW_DOCSERVICES)

* 对基于XFA的自适应Forms的支持现成不可用。 如果您打算使用基于XFA的自适应Forms，请联系Adobe支持，了解您的使用案例和具体要求的详细信息。((XFA_BASED_FORM， XDP_BASED_FORM)

联系[Adobe支持](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)以获得说明或解决问题。
