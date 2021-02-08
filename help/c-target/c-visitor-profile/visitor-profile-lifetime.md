---
keywords: 概覽和參考
description: 進一步瞭解Adobe Target中的訪客資料何時過期（預設為14天）。 聯絡Adobe Client Care可延長描述檔存留期。
title: 訪客描述檔存留期為何，我可以延長它嗎？
feature: Audiences
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 73%

---


# 訪客設定檔存留期{#visitor-profile-lifetime}

根據預設，訪客設定檔會在該訪客 14 天未使用後過期。但可延長此描述檔存留期。

[請聯絡 Client Care 或您的 Adobe 顧問](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)，即可免費延長描述檔存留期。存留期最長可設為 90 天。

您使用的 [!DNL Target] JavaScript 資料庫 ([!DNL at.js] 或 [!DNL mbox.js]) 會決定您是否需要下載新檔案:

| Target 資料庫 | 詳細資料 |
|--- |--- |
| at.js | 如果您的設定檔已延長至超過預設值，則不需下載新的 at.js 檔案。 |
| mbox.js | 如果您的描述檔延長超過預設的 14 天，在顧問或 Client Care 變更您的設定後，您必須下載新的 mbox.js 檔案。更新的 mbox.js 檔案中包含可支援已變更描述檔存留期的 Cookie 延伸模組。開始使用新資料庫之後，您的訪客設定檔存留期將會更新。 |

但不會重設現有描述檔的過期日期。如果先前訪客未在 15 天內返回，該描述檔即過期。如果先前訪客在原始的 2 週描述檔過期前返回，描述檔將重設為延長的存留期。所有新的訪客描述檔會設為延長的描述檔存留期。

在下列情況下，假設一個或兩個網站都是以mbox.js實作，而mbox.js需要在描述檔更新後更新程式碼。 如果兩個網站都採用一個用戶端程式碼，而訪客瀏覽了兩個網站，則描述檔會設為上次瀏覽任何網站的描述檔存留期。 例如，如果網站 1 具有 84 天的描述檔存留期而網站 2 具有 14 天存留期，訪客先造訪網站 1 接著造訪網站 2，則該訪客的描述檔將在 14 天未使用後過期。如果訪客先造訪網站 2 再造訪網站 1，則描述檔將在 84 天未使用後過期。
