---
description: 在 Adobe Target (A4T) 中建立 Adobe Analytics 型活動的使用者帳戶需求。
keywords: Analytics 作為報表來源;a4t;A4T
seo-description: 在 Adobe Target (A4T) 中建立 Adobe Analytics 型活動的使用者帳戶需求。
seo-title: 使用者權限需求
solution: Target、Analytics
title: 使用者權限需求
topic: Reports & Analytics
uuid: cf359bcd-547e-4f8f-bcf6-e646245bb9ce
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

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

您必須是&#x200B;**[!UICONTROL 所有報表存取]**&#x200B;群組的成員，或您所屬的群組在您要使用的報表套裝中必須至少可存取一個報表，您才能為 Analytics 啟動的活動建立或檢視報表。如果無法檢視報表，請確定您是這其中一個群組的成員。

For more information, see [Product profiles and groups](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html#section_AB50558124D541CF80A0D3D76D35A4BF).

### 設定 Web 服務存取群組的存取權。

您必須屬於 [!DNL Adobe Analytics] 中的 Web 服務存取群組，才能使用 [!DNL Analytics] 做為 [!DNL Target] 的報表來源。

## Adobe Target {#section_26BA212D8D40443E9EE2AB327091425C}

不需要其他權限。
