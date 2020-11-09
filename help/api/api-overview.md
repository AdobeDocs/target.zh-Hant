---
keywords: api;apis;admin api;delivery api;reporting api;profile api
description: 有關Adobe Target API的資訊，包括管理、傳送、報告和設定檔API。
title: Adobe Target API總覽
feature: api
topic: APIs
translation-type: tm+mt
source-git-commit: a05d2a28b7bea3aa559cd0174930af10c6d94134
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 1%

---


# Adobe Target API總覽

[!DNL Adobe Target] API可依類型分組。

| API類型 | 它可讓您 | 下載連結 | 其他實用連結 |
| --- | --- | --- |--- |
| 管理 | 建立、修改和刪除活動、觀眾、選件和其他物件(包括 [!DNL Recommendations] 實體、准則、設計等)。 API [!DNL Recommendations] 是一種管理API。) | <UL><li>[Target Admin API Postman Collection](https://developers.adobetarget.com/api/#admin-postman-collection)</li><li>[Recommendations API Postman Collection](https://developers.adobetarget.com/api/recommendations/#section/Postman)</li></ul> | [在](https://experienceleague.adobe.com/docs/target-learn/recommendations-api-tutorial/recs-api-overview.html)*Adobe Target教學課程中使用Recommendations API* |
| 傳送 | 從中擷取最佳化和個人化的 [!DNL Target] 內容，以便傳送給使用者。 | [Target Delivery API Postman Collection](https://developers.adobetarget.com/api/delivery-api/#section/Getting-Started/Postman-Collection) |  |
| 報表 | 匯出活動結果和其他報告結果。 | 報表API包含在 [Target Admin API Postman集合中](https://developers.adobetarget.com/api/#admin-postman-collection)。 |  |
| 描述檔 | 擷取並修改儲存在Adobe Target中的使用者設定檔。 | [Target描述檔API Postman Collection](https://developers.adobetarget.com/api/#profiles) |  |

>[!NOTE]
>
>管理API（包括API） [!DNL Target] 和傳送API之間有 [!DNL Recommendations] 重要的 [!DNL Target] 區別：
>
>* 管理API可讓您設定UI中 [!DNL Target] 也可設定的各 [!DNL Target] 個方面。 管理API需要驗證。
   >
   >
* 傳送API可讓您擷取內容。 傳送API不需要驗證。
>
>
若要使 [!DNL Target] 用管理API，您必須先使用Adobe I/O來設定驗證。如需詳細資訊，請參 [閱Adobe Target教學課程](https://experienceleague.adobe.com/docs/target-learn/tutorials/apis/configure-io-target-integration.html)*中的設定驗證*。
