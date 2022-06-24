---
keywords: 實作; 設定; 頁面參數; tomcat; URL 編碼; 頁面內設定檔屬性; mbox 參數; 指令碼設定檔屬性; 大量設定檔更新 API; 單一檔案更新 API; 客戶屬性; 資料提供者
description: 將資料 [!DNL Target] （頁面參數、配置檔案屬性、指令碼配置檔案屬性、資料提供程式、單個和批量配置檔案更新API、客戶屬性）。
title: 如何將資料導入目標？
feature: Implementation
role: Developer
exl-id: b42eb846-d423-4545-a8fe-0b8048ab689e
source-git-commit: 719eb95049dad3bee5925dff794871cd65969f79
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 50%

---

# 方法概覽

有關可用於將資料導入的不同方法的資訊 [!DNL Adobe Target]。

可用方法包括：

| 方法 | 詳細資料 |
| --- | --- |
| [頁面參數](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/page-parameters/){target=_blank}<br>（也稱為「mbox參數」） | 頁面參數是直接透過頁面程式碼傳入的名稱/值配對，不儲存在訪客的設定檔中供未來使用。<br>頁面參數對於將頁面資料發送到目標非常有用，該目標不需要與訪問者的配置檔案一起儲存，以便將來進行目標使用。 這些值改用來說明頁面，或使用者在特定頁面上採取的動作。 |
| [頁內配置檔案屬性](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/in-page-profile-attributes/){target=_blank}<br>（也稱為「收件箱配置檔案屬性」） | 頁面內設定檔參數是直接透過頁面程式碼傳遞的名稱/值配對，儲存在訪客的設定檔中供未來使用。<br>頁面內設定檔屬性允許將使用者特定的資料儲存在 Target 的設定檔中，供稍後鎖定目標和分割。 |
| [指令碼配置檔案屬性](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/script-profile-attributes/){target=_blank} | 指令碼設定檔屬性是 Target 解決方案中定義的名稱/值配對。值取決於每次伺服器呼叫在 Target 的伺服器上執行 JavaScript 片段。<br>使用者撰寫較小的程式碼片段，在每次 mbox 呼叫時執行，以及在評估訪客的對象和活動成員資格之前執行。 |
| [資料提供程式](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/data-providers/){target=_blank} | 資料提供程式使您能夠輕鬆地將資料從第三方傳遞到目標。 |
| [批量配置檔案更新API](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/bulk-profile-update-api/){target=_blank} | 透過 API，將 .csv 檔案傳送至 Target，此檔案包含許多訪客的訪客設定檔更新項目。一次呼叫就能以多個頁面內設定檔屬性來更新每一個訪客設定檔。 |
| [單個配置檔案更新API](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/single-profile-update-api/){target=_blank} | 幾乎與批量配置檔案更新API相同，但每次更新一個訪問者配置檔案，在API調用中排行，而不是使用.csv檔案。 |
| [客戶屬性](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/customer-attributes/){target=_blank} | 客戶屬性可讓您透過 FTP 將訪客設定檔資料上傳至 Experience Cloud。上傳後，請使用Adobe Analytics和Adobe Target的資料。 |












