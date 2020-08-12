---
keywords: Analytics as reporting source;a4t;A4T
description: 在 Adobe Target (A4T) 中建立 Adobe Analytics 型活動的使用者帳戶需求。
title: 使用者權限需求
feature: null
solution: Target,Analytics
topic: Reports and analytics
uuid: cf359bcd-547e-4f8f-bcf6-e646245bb9ce
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 63%

---


# 使用者權限需求 {#user-permission-requirements}

有關在 [!DNL Adobe Target] (A4T) 中建立 [!DNL Adobe Analytics] 型活動之使用者帳戶需求的資訊。

定義 [!DNL Analytics] 活動時，在可以選取報表套裝之前，您同時需要 [!DNL Analytics] 使用者帳戶和 [!DNL Target] 使用者帳戶。

必須依下列各節所述來設定您的使用者帳戶:

## Adobe Experience Cloud {#section_3931A2FAD38F4A4FA92CC77B92AF3F0D}

在 [!DNL Adobe Experience Cloud] [Admin Console](https://adminconsole.adobe.com) 中完成下列工作:

### 將解決方案帳戶連結至您的 Adobe ID

[!DNL Analytics] 和 [!DNL Target] 使用者帳戶必須連結至 Adobe ID。

For more information, see [Organizations and account linking](https://docs.adobe.com/help/en/core-services/interface/manage-users-and-products/organizations.html).

### 設定 Experience Cloud 群組成員資格

您必須是具有 [!DNL Analytics] 和 [!DNL Target] 存取權之一或多個 [!DNL Experience Cloud] 群組的成員。

For more information, see [Manage Experience Cloud users and products](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html).

## Adobe Analytics {#section_8F404FDE9A634534AB0AA4CB3075582B}

在 [!DNL Adobe Analytics] 中完成下列工作:

### 設定 Analytics 報表套裝的存取權

Before creating or viewing reports for an [!DNL Analytics]-powered activity, you must be a member of the **[!UICONTROL All Report Access]** group, or a member of a group that has access to at least one report in the report suite that you want to use. 如果無法檢視報表，請確定您是這其中一個群組的成員。

如需詳細資訊，請參 [閱產品設定檔和群組](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html#section_AB50558124D541CF80A0D3D76D35A4BF)。

### 設定 Web 服務存取群組的存取權。

您必須屬於 [!DNL Analytics] 中的 Web 服務存取群組，才能使用 [!DNL Analytics] 做為 [!DNL Target] 的報表來源。

## Adobe Target {#section_26BA212D8D40443E9EE2AB327091425C}

不需要其他權限。
