---
keywords: Analytics作為報表來源；a4t；A4T；需求
description: 瞭解如何使用Analytics for [!DNL Target] (A4T)設定在Adobe [!DNL Target] 中建立Adobe Analytics型活動所需的使用者帳戶需求。
title: A4T需要哪些使用者許可權需求？
feature: Analytics for Target (A4T)
solution: Target,Analytics
exl-id: f56fc525-92da-4814-86c1-18b3a2765f37
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 35%

---

# 使用者權限需求

有關在 [!DNL Adobe Target] (A4T) 中建立 [!DNL Adobe Analytics] 型活動之使用者帳戶需求的資訊。

定義 [!DNL Analytics] 活動時，在可以選取報表套裝之前，您同時需要 [!DNL Analytics] 使用者帳戶和 [!DNL Target] 使用者帳戶。

必須依下列各節所述來設定您的使用者帳戶:

## Adobe Experience Cloud {#section_3931A2FAD38F4A4FA92CC77B92AF3F0D}

在[!DNL Adobe Experience Cloud] [Admin Console](https://adminconsole.adobe.com)中完成下列工作：

### 將解決方案帳戶連結至您的 Adobe ID

[!DNL Analytics] 和 [!DNL Target] 使用者帳戶必須連結至 Adobe ID。

如需詳細資訊，請參閱[組織和帳戶連結](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=en)。

### 設定 Experience Cloud 群組成員資格

您必須是具有 [!DNL Analytics] 和 [!DNL Target] 存取權之一或多個 [!DNL Experience Cloud] 群組的成員。

如需詳細資訊，請參閱[管理Experience Cloud使用者和產品](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html)。

## Adobe Analytics {#section_8F404FDE9A634534AB0AA4CB3075582B}

若要在指定的報表套裝上使用A4T，您必須擁有該報表套裝的存取權，並授與[!DNL Web Services Access]群組的存取權。

1. 在&#x200B;**[!UICONTROL Admin Console]**&#x200B;中，按一下[!DNL Analytics]產品設定檔，然後按一下「**[!UICONTROL Permissions]**」標籤。

   然後您可以檢視設定檔可存取的報表套裝。

1. 確定您要在[!DNL Target]中存取的報告套裝是您所屬的產品設定檔中所列的其中一個。

   下圖是存取所有報表套裝的產品設定檔範例：

   ![Admin Console許可權索引標籤](/help/main/c-integrating-target-with-mac/a4t/assets/permissions-tab.png)

1. 設定[!UICONTROL Web Services Access]群組的存取權。

   必須存取[!DNL Analytics]中的[!UICONTROL Web Services Access]群組，才能使用[!DNL Analytics]做為[!DNL Target]的報告來源。


## Adobe [!DNL Target] {#section_26BA212D8D40443E9EE2AB327091425C}

不需要其他權限。
