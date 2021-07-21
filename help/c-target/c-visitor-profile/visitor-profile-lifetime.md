---
keywords: 概覽和參考
description: 進一步了解訪客設定檔何時會在 [!DNL Adobe Target]過期。
title: 什麼是訪客設定檔存留期，我可以延長它嗎？
feature: 對象
exl-id: 70cb5e3b-ed6d-450d-8c6e-f1bfe8d26e54
source-git-commit: c19163020cdcb41a17ea6b65b5b500fadc9c7512
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 45%

---

# 訪客設定檔存留期

依預設，[!DNL Adobe Target]中的訪客設定檔會在該訪客閒置14天後過期。 但可延長此描述檔存留期。

[請聯絡 Client Care 或您的 Adobe 顧問](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)，即可免費延長描述檔存留期。存留期最長可設為 90 天。

如果您的設定檔已延長至超過預設值，則不需要下載新的[!DNL Platform Web SDK]檔案或at.js檔案。

但不會重設現有描述檔的過期日期。如果先前訪客未在 15 天內返回，該描述檔即過期。如果先前訪客在原始的 2 週描述檔過期前返回，描述檔將重設為延長的存留期。所有新的訪客描述檔會設為延長的描述檔存留期。

在以下情況中，假設使用[!DNL Platform Web SDK]實作一個或兩個網站。 如果兩個網站都屬於一個用戶端代碼，且訪客造訪了兩個網站，則描述檔會設為最後造訪之網站的描述檔存留期。 例如，假設網站1具有84天的描述檔存留期。 網站2的存留期為14天。 如果訪客先造訪網站1接著造訪網站2，該訪客的設定檔便會在14天未使用後過期。 如果訪客先造訪網站 2 再造訪網站 1，則描述檔將在 84 天未使用後過期。
