---
description: 依預設，訪客描述檔會儲存 14 天。但可延長此描述檔存留期。
keywords: 概覽和參考
seo-description: 依預設，訪客描述檔會儲存 14 天。但可延長此描述檔存留期。
seo-title: 訪客設定檔存留期
solution: Target
subtopic: 快速入門
title: 訪客設定檔存留期
topic: Standard
uuid: 01ccda60-7e28-4d26-8d5d-1c0a022bbef0
translation-type: tm+mt
source-git-commit: 592fb6833a9bce1a4b9b5b698ee41331374a8a22

---


# 訪客設定檔存留期{#visitor-profile-lifetime}

依預設，訪客描述檔會儲存 14 天。但可延長此描述檔存留期。

[請聯絡 Client Care 或您的 Adobe 顧問](../../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)，即可免費延長描述檔存留期。存留期最長可設為 90 天。

您使用的 [!DNL Target] JavaScript 資料庫 ([!DNL mbox.js] 或 [!DNL at.js]) 會決定您是否需要下載新檔案:

| Target 資料庫 | 詳細資料 |
|--- |--- |
| at.js | 如果您的設定檔已延長至超過預設值，則不需下載新的 at.js 檔案。 |
| mbox.js | 如果您的描述檔延長超過預設的 14 天，在顧問或 Client Care 變更您的設定後，您必須下載新的 mbox.js 檔案。更新的 mbox.js 檔案中包含可支援已變更描述檔存留期的 Cookie 延伸模組。開始使用新資料庫之後，您的訪客設定檔存留期將會更新。 |

但不會重設現有描述檔的過期日期。如果先前訪客未在 15 天內返回，該描述檔即過期。如果先前訪客在原始的 2 週描述檔過期前返回，描述檔將重設為延長的存留期。所有新的訪客描述檔會設為延長的描述檔存留期。

如果您有兩個網站屬於同一個用戶端代碼，而訪客造訪了這兩個網站，則描述檔會設為最後造訪之網站的描述檔存留期。例如，如果網站 1 具有 84 天的描述檔存留期而網站 2 具有 14 天存留期，訪客先造訪網站 1 接著造訪網站 2，則該訪客的描述檔將在 14 天後過期。如果訪客先造訪網站 2 再造訪網站 1，則描述檔將在 84 天後過期。
