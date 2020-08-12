---
keywords: api;apis;admin api;delivery api;reporting api;profile api
description: 有關Adobe Target API的資訊，包括管理、傳送、報告和設定檔API。
title: Adobe Target API總覽
topic: APIs
translation-type: tm+mt
source-git-commit: 84cd5d41655baaaadeba63954858730ce956e039
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 2%

---


# Adobe Target API總覽

Adobe Target API可依類型分組。

| API 類型 | 它可讓您 | 下載連結 | 其他實用連結 |
| --- | --- | --- |--- |
| 管理 | 建立、修改和刪除活動、觀眾、選件和其他物件(包括 [!DNL Recommendations] 實體、准則、設計等)。 API [!DNL Recommendations] 是一種管理API。) | <UL><li>[Target Admin API Postman Collection](https://developers.adobetarget.com/api/#admin-postman-collection)</li><li>[Recommendations API Postman Collection](https://developers.adobetarget.com/api/recommendations/#section/Postman)</li></ul> | [在](https://docs.adobe.com/content/help/en/target-learn/recommendations-api-tutorial/recs-api-overview.html)*Adobe Target教學課程中使用Recommendations API* |
| 傳送 | 從中擷取最佳化和個人化的 [!DNL Target] 內容，以便傳送給使用者。 | [Target Delivery API Postman Collection](https://developers.adobetarget.com/api/delivery-api/#section/Getting-Started/Postman-Collection) |  |
| 報表 | 匯出活動結果和其他報告結果。 | 報表API包含在 [Target Admin API Postman集合中](https://developers.adobetarget.com/api/#admin-postman-collection)。 |  |
| 描述檔 | 擷取並修改儲存在Adobe Target中的使用者設定檔。 | [Target描述檔API Postman Collection](https://developers.adobetarget.com/api/#profiles) |  |

>[!NOTE]
>
>請注意管理 **API** (包括 [!DNL Recommendations] API)與傳送API（可讓您設定Adobe Target的各個方面）之 ****&#x200B;間的區別，傳送API可讓您擷取內容。 管理API需要驗證，而傳送API則不需要。
>
>若要使用Adobe Target管理API，您首先需要使用Adobe I/O來設定驗證。如需詳細資訊，請參 [閱Adobe Target教學課程](https://docs.adobe.com/content/help/en/target-learn/tutorials/apis/configure-io-target-integration.html)*中的設定驗證*。
