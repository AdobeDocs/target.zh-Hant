---
keywords: 概覽和參考
description: 深入瞭解訪客設定檔何時於 [!DNL Adobe Target]到期。
title: 訪客設定檔存留期是多久？可以延長嗎？
feature: Audiences
exl-id: 70cb5e3b-ed6d-450d-8c6e-f1bfe8d26e54
TQID: https://experienceleague.adobe.com/yMfacKgQthOmpfhFiuO-jGGPWZh5VrliOSi0TQ-uis0
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 147
ht-degree: 62%

---

# 訪客輪廓存留期

根據預設，[!DNL Adobe Target]中的訪客設定檔會在該訪客14天未使用後過期。 但可延長此輪廓存留期。

[請聯絡 Client Care 或您的 Adobe 顧問](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)，即可免費延長輪廓存留期。 存留期最長可設為 90 天。

如果您的設定檔已延長至超過預設值，則不需要下載新的[!DNL Platform Web SDK]檔案或at.js檔案。

但不會重設現有描述檔的過期日期。 如果先前訪客未在 15 天內返回，該描述檔即過期。 如果先前訪客在原始的 2 週描述檔過期前返回，描述檔將重設為延長的存留期。 所有新的訪客描述檔會設為延長的描述檔存留期。
