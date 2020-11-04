---
keywords: Analytics as reporting source;a4t;A4T
description: 在 Adobe Target (A4T) 中建立 Adobe Analytics 型活動的使用者帳戶需求。
title: 使用者權限需求
feature: a4t implementation
solution: Target,Analytics
topic: Reports and analytics
uuid: cf359bcd-547e-4f8f-bcf6-e646245bb9ce
translation-type: tm+mt
source-git-commit: 3215aa7c5ce986ff335dd2669c250ef5900d8789
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 51%

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

若要在指定的報表套裝上使用A4T，您必須擁有該報表套裝的存取權。 若要在 [!UICONTROL Admin Console中存取]，請按一下產 [!DNL Analytics] 品設定檔，然後按一下「 [!UICONTROL 權限] 」標籤。 然後您就可以看到描述檔可存取的報表套裝。 請確定您要存取的報表套裝是您所 [!DNL Target] 屬產品設定檔中所列的報表套裝之一。

下圖為可存取所有報表套裝的產品設定檔範例：

![「管理控制台權限」標籤](/help/c-integrating-target-with-mac/a4t/assets/permissions-tab.png)

## Adobe Target {#section_26BA212D8D40443E9EE2AB327091425C}

不需要其他權限。
