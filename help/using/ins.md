---
title: INS
description: Pattern Detector 代码帮助页面。
exl-id: d89e1589-3195-4b2d-98f4-136bedaecb0b
source-git-commit: 84c193b66fbf9c41f546e8575a0aa17e94043b9a
workflow-type: tm+mt
source-wordcount: '107'
ht-degree: 77%

---

# INS {#ins}

命名空间无效

## 背景 {#background}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ins_overview"
>title="命名空间无效"
>abstract="INS 识别 AEM 实例上的命名空间问题"

`INS`  （命名空间无效）标识AEM实例上的命名空间问题。

子类型用于标识不同类型的信息，例如：

* `uri`：识别 AEM 中无效的命名空间 URI。

## 可能产生的后果和风险 {#implications-and-risks}

* 无法复制内容（跨层）或复制内容(跨 `env`，通过 `/crx/packMgr`或内容副本)。

## 可采用的解决方案 {#solutions}

>[!CONTEXTUALHELP]
>id="aemcloud_bpa_ins_guidance"
>title="实施指南"
>abstract="联系客户关怀部门寻求帮助。"
>additional-url="https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html" text="Experience Cloud 支持"

* 根据 [JCR 规范](https://developer.adobe.com/experience-manager/reference-materials/spec/jcr/1.0/4.5_Namespaces.html)修复命名空间定义。请按照[此处](https://experienceleaguecommunities.adobe.com/t5/adobe-experience-manager/how-can-i-delete-a-namespace-created-in-crx/td-p/225163)提到的步骤操作
* 请联系我们的 [Experience Manager 客户服务团队](https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html)进行澄清或解决疑惑。
