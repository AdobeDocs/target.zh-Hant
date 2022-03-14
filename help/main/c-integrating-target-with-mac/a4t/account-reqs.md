---
keywords: 分析作為報告源；a4t;A4T；要求
description: 瞭解如何配置建立基於Adobe Analytics的Adobe活動所需的用戶帳戶要求 [!DNL Target] 使用分析 [!DNL Target] (A4T)。
title: A4T需要哪些用戶權限要求？
feature: Analytics for Target (A4T)
solution: Target,Analytics
exl-id: f56fc525-92da-4814-86c1-18b3a2765f37
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 34%

---

# 使用者權限需求

有關在 [!DNL Adobe Target] (A4T) 中建立 [!DNL Adobe Analytics] 型活動之使用者帳戶需求的資訊。

定義 [!DNL Analytics] 活動時，在可以選取報表套裝之前，您同時需要 [!DNL Analytics] 使用者帳戶和 [!DNL Target] 使用者帳戶。

必須依下列各節所述來設定您的使用者帳戶:

## Adobe Experience Cloud {#section_3931A2FAD38F4A4FA92CC77B92AF3F0D}

在 [!DNL Adobe Experience Cloud] [Admin Console](https://adminconsole.adobe.com) 中完成下列工作:

### 將解決方案帳戶連結至您的 Adobe ID

[!DNL Analytics] 和 [!DNL Target] 使用者帳戶必須連結至 Adobe ID。

有關詳細資訊，請參見 [組織和帳戶連結](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=en)。

### 設定 Experience Cloud 群組成員資格

您必須是具有 [!DNL Analytics] 和 [!DNL Target] 存取權之一或多個 [!DNL Experience Cloud] 群組的成員。

有關詳細資訊，請參見 [管理Experience Cloud用戶和產品](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html)。

## Adobe Analytics {#section_8F404FDE9A634534AB0AA4CB3075582B}

要在給定的報告套件上使用A4T，您必須有權訪問該報告套件並授予對 [!DNL Web Services Access] 組。

1. 在 **[!UICONTROL Admin Console]**，按一下 [!DNL Analytics] 產品配置檔案，然後按一下 **[!UICONTROL 權限]** 頁籤。

   然後，您可以查看配置檔案有權訪問的報表套件。

1. 確保要訪問的報告套件 [!DNL Target] 是您所屬的產品配置檔案中列出的其中一個。

   下圖是具有所有報告套件訪問權限的產品配置檔案的示例：

   ![Admin Console權限頁籤](/help/main/c-integrating-target-with-mac/a4t/assets/permissions-tab.png)

1. 配置對 [!UICONTROL Web服務訪問] 組。

   訪問 [!UICONTROL Web服務訪問] 組 [!DNL Analytics] 必須能夠使用 [!DNL Analytics] 作為 [!DNL Target]。


## Adobe [!DNL Target] {#section_26BA212D8D40443E9EE2AB327091425C}

不需要其他權限。
