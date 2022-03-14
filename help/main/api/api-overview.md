---
keywords: api;apis;admin api;delivery api;reporting api;profile api;apis;admin api;delivery api;reporting api;profile api
description: 查找Adobe [!DNL Target] API，包括管理、交付、報告和配置檔案API。
title: 在哪裡可以找到 [!DNL Target] API和SDK文檔？
feature: APIs/SDKs
role: Developer
exl-id: 2a0232cc-9a6a-42f4-afb6-4b3e2b13939c
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 1%

---

# Adobe [!DNL Target] API概述

[!DNL Adobe Target] API可以按類型分組：管理、交付、報告和配置檔案API。

| API類型 | 它使您能夠 | 下載連結 | 其他有用連結 |
| --- | --- | --- |--- |
| 管理 | 建立、修改和刪除活動、受眾、聘用和其他對象(包括 [!DNL Recommendations] 實體、標準、設計等。 的 [!DNL Recommendations] API是管理API的類型。) | <UL><li>[目標管理API郵遞員集合](https://developers.adobetarget.com/api/#admin-postman-collection)</li><li>[RecommendationsAPI郵遞員收藏](https://developers.adobetarget.com/api/recommendations/#section/Postman)</li></ul> | [使用RecommendationsAPI](https://experienceleague.adobe.com/docs/target-learn/recommendations-api-tutorial/recs-api-overview.html) 在 *Adobe TargetTutorials* |
| 傳送 | 從中檢索優化和個性化的內容 [!DNL Target] 交付給最終用戶。 | [目標傳遞API郵遞員集合](https://developers.adobetarget.com/api/delivery-api/#section/Getting-Started/Postman-Collection) |  |
| 報表 | 導出活動結果和其他報告結果。 | 報告API包含在 [目標管理API郵遞員集合](https://developers.adobetarget.com/api/#admin-postman-collection)。 |  |
| 設定檔 | 檢索和修改儲存在Adobe Target的用戶配置檔案。 | [目標配置檔案API郵遞員集合](https://developers.adobetarget.com/api/#profiles) |  |

>[!NOTE]
>
>兩者之間有重要區別 [!DNL Target] 管理API(包括 [!DNL Recommendations] API)和 [!DNL Target] 傳遞API:
>
>* 管理API允許您配置 [!DNL Target] 也可以在 [!DNL Target] UI。 管理API需要身份驗證。
>
>* 通過交付API可檢索內容。 傳遞API不需要身份驗證。
>
>要使用 [!DNL Target] 管理API，您首先需要使用Adobe I/O配置身份驗證。有關詳細資訊，請參見 [配置身份驗證](https://experienceleague.adobe.com/docs/target-learn/tutorials/apis/configure-io-target-integration.html) 在 *Adobe TargetTutorials*。
