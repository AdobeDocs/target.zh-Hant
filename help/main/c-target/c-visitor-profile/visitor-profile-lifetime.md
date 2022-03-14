---
keywords: 概覽和參考
description: 瞭解有關訪問者配置檔案何時過期的詳細資訊 [!DNL Adobe Target]。
title: 訪問者資料的使用期是多少，我可以延長它嗎？
feature: Audiences
exl-id: 70cb5e3b-ed6d-450d-8c6e-f1bfe8d26e54
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 62%

---

# 訪客設定檔存留期

預設情況下， [!DNL Adobe Target] 該訪問者在不活動14天後過期。 但可延長此描述檔存留期。

[請聯絡 Client Care 或您的 Adobe 顧問](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)，即可免費延長描述檔存留期。存留期最長可設為 90 天。

您不需要下載新 [!DNL Platform Web SDK] 檔案或at.js檔案（如果配置檔案擴展到預設值之外）。

但不會重設現有描述檔的過期日期。如果先前訪客未在 15 天內返回，該描述檔即過期。如果先前訪客在原始的 2 週描述檔過期前返回，描述檔將重設為延長的存留期。所有新的訪客描述檔會設為延長的描述檔存留期。
