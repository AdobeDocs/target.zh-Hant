---
keywords: api;api;api;admin api;delivery api;reporting api;profile api
description: 尋找Adobe Target API，包括管理、傳送、報告和設定檔API。
title: 我可以在何處找到Target API和SDK檔案？
feature: APIs/SDKs
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 1%

---


# Adobe Target API總覽

[!DNL Adobe Target] API可依類型分組：管理、傳送、報告和描述檔API。

| API類型 | 它可讓您 | 下載連結 | 其他實用連結 |
| --- | --- | --- |--- |
| 管理 | 建立、修改和刪除活動、對象、選件和其他物件（包括[!DNL Recommendations]實體、准則、設計等）。 [!DNL Recommendations] API是一種管理API。) | <UL><li>[Target Admin API Postman Collection](https://developers.adobetarget.com/api/#admin-postman-collection)</li><li>[Recommendations API Postman Collection](https://developers.adobetarget.com/api/recommendations/#section/Postman)</li></ul> | [在](https://experienceleague.adobe.com/docs/target-learn/recommendations-api-tutorial/recs-api-overview.html) Adobe Target教學課程中使用Recommendations  *API* |
| 傳送 | 從[!DNL Target]擷取最佳化和個人化內容，以傳遞給使用者。 | [Target Delivery API Postman Collection](https://developers.adobetarget.com/api/delivery-api/#section/Getting-Started/Postman-Collection) |  |
| 報表 | 匯出活動結果和其他報告結果。 | 報告API包含在[Target Admin API Postman集合](https://developers.adobetarget.com/api/#admin-postman-collection)中。 |  |
| 描述檔 | 擷取並修改儲存在Adobe Target中的使用者設定檔。 | [Target描述檔API Postman Collection](https://developers.adobetarget.com/api/#profiles) |  |

>[!NOTE]
>
>[!DNL Target]管理API（包括[!DNL Recommendations] API）和[!DNL Target]傳送API之間有重要區別：
>
>* 管理API可讓您設定[!DNL Target]的各個方面，您也可以在[!DNL Target] UI中設定。 管理API需要驗證。
   >
   >
* 傳送API可讓您擷取內容。 傳送API不需要驗證。
>
>
若要使用[!DNL Target]管理API，您必須先使用Adobe I/O來設定驗證。如需詳細資訊，請參閱&#x200B;*Adobe Target教學課程*&#x200B;中的[設定驗證](https://experienceleague.adobe.com/docs/target-learn/tutorials/apis/configure-io-target-integration.html)。
