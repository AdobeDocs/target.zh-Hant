---
keywords: 實作; 設定; 頁面參數; tomcat; URL 編碼; 頁面內設定檔屬性; mbox 參數; 指令碼設定檔屬性; 大量設定檔更新 API; 單一檔案更新 API; 客戶屬性; 資料提供者
description: 將資料匯入 [!DNL Target] （頁面參數、描述檔屬性、指令碼描述檔屬性、資料提供者、單一和大量描述檔更新API、客戶屬性）。
title: 如何將資料匯入Target?
feature: 實施
role: Developer
exl-id: b42eb846-d423-4545-a8fe-0b8048ab689e
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 62%

---

# 方法概觀

有關您可用來將資料匯入[!DNL Adobe Target]之不同方法的資訊。

可用的方法包括：

| 方法 | 詳細資料 |
| --- | --- |
| [頁面參數](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/page-parameters.md)<br>（也稱為「mbox參數」） | 頁面參數是直接透過頁面程式碼傳入的名稱/值配對，不儲存在訪客的設定檔中供未來使用。<br>頁面參數對於傳送頁面資料至Target非常有用，因為Target不需要與訪客的描述檔一起儲存，以便日後進行定位。這些值改用來說明頁面，或使用者在特定頁面上採取的動作。 |
| [頁面內描述檔屬性](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/in-page-profile-attributes.md)<br>（也稱為「in-mbox描述檔屬性」） | 頁面內設定檔參數是直接透過頁面程式碼傳遞的名稱/值配對，儲存在訪客的設定檔中供未來使用。<br>頁面內設定檔屬性允許將使用者特定的資料儲存在 Target 的設定檔中，供稍後鎖定目標和分割。 |
| [指令碼設定檔屬性](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/script-profile-attributes.md) | 指令碼設定檔屬性是 Target 解決方案中定義的名稱/值配對。值取決於每次伺服器呼叫在 Target 的伺服器上執行 JavaScript 片段。<br>使用者撰寫較小的程式碼片段，在每次 mbox 呼叫時執行，以及在評估訪客的對象和活動成員資格之前執行。 |
| [資料提供者](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/data-providers.md) | 資料提供者可讓您輕鬆地將資料從第三方傳遞至Target。 |
| [大量設定檔更新 API](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/bulk-profile-update-api.md) | 透過 API，將 .csv 檔案傳送至 Target，此檔案包含許多訪客的訪客設定檔更新項目。一次呼叫就能以多個頁面內設定檔屬性來更新每一個訪客設定檔。 |
| [單一設定檔更新 API](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/single-profile-update-api.md) | 幾乎與「大量描述檔更新API」相同，但每次會更新一個訪客描述檔，並以API呼叫的行式，而非。csv檔案。 |
| [客戶屬性](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/customer-attributes.md) | 客戶屬性可讓您透過 FTP 將訪客設定檔資料上傳至 Experience Cloud。上傳後，請使用Adobe Analytics和Adobe Target的資料。 |












