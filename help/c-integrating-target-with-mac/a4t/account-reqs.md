---
keywords: Analytics作為報告來源；a4t;A4T；需求
description: 瞭解如何使用Analytics for Target(A4T)，設定在Adobe Target中建立以Adobe Analytics為基礎的活動所需的使用者帳戶需求。
title: A4T需要哪些使用者權限要求？
feature: Analytics for Target (A4T)
solution: Target,Analytics
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 38%

---


# 使用者權限需求

有關在 [!DNL Adobe Target] (A4T) 中建立 [!DNL Adobe Analytics] 型活動之使用者帳戶需求的資訊。

定義 [!DNL Analytics] 活動時，在可以選取報表套裝之前，您同時需要 [!DNL Analytics] 使用者帳戶和 [!DNL Target] 使用者帳戶。

必須依下列各節所述來設定您的使用者帳戶:

## Adobe Experience Cloud {#section_3931A2FAD38F4A4FA92CC77B92AF3F0D}

在 [!DNL Adobe Experience Cloud] [Admin Console](https://adminconsole.adobe.com) 中完成下列工作:

### 將解決方案帳戶連結至您的 Adobe ID

[!DNL Analytics] 和 [!DNL Target] 使用者帳戶必須連結至 Adobe ID。

如需詳細資訊，請參閱[組織和帳戶連結](https://docs.adobe.com/help/en/core-services/interface/manage-users-and-products/organizations.html)。

### 設定 Experience Cloud 群組成員資格

您必須是具有 [!DNL Analytics] 和 [!DNL Target] 存取權之一或多個 [!DNL Experience Cloud] 群組的成員。

如需詳細資訊，請參閱[管理Experience Cloud使用者和產品](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html)。

## Adobe Analytics {#section_8F404FDE9A634534AB0AA4CB3075582B}

設定對[!DNL Analytics]報表套裝的存取：

若要在指定的報表套裝上使用A4T，您必須擁有該報表套裝的存取權。

1. 在&#x200B;**[!UICONTROL 管理控制台]**&#x200B;中，按一下[!DNL Analytics]產品設定檔，然後按一下&#x200B;**[!UICONTROL 權限]**&#x200B;標籤。

   然後您就可以看到描述檔可存取的報表套裝。

1. 請確定您要在[!DNL Target]中存取的報表套裝是您所屬產品設定檔中所列的報表套裝之一。

   下圖為可存取所有報表套裝的產品設定檔範例：

   ![「管理控制台權限」標籤](/help/c-integrating-target-with-mac/a4t/assets/permissions-tab.png)

## Adobe Target {#section_26BA212D8D40443E9EE2AB327091425C}

不需要其他權限。
