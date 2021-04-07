---
keywords: 實作; 設定; 頁面參數; tomcat; URL 編碼; 頁面內設定檔屬性; mbox 參數; 指令碼設定檔屬性; 大量設定檔更新 API; 單一檔案更新 API; 客戶屬性; 資料提供者
description: 將資料匯入Target（頁面參數、描述檔屬性、指令碼描述檔屬性、資料提供者、單一和大量描述檔更新API、客戶屬性）。
title: 如何將資料匯入Target?
feature: 實施
role: Developer
exl-id: b42eb846-d423-4545-a8fe-0b8048ab689e
translation-type: tm+mt
source-git-commit: 70d4c5b4166081751246e867d90d43b67efa5469
workflow-type: tm+mt
source-wordcount: '1082'
ht-degree: 84%

---

# 方法概觀

有關您可用來將資料匯入[!DNL Adobe Target]之不同方法的資訊。

可用的方法包括：

| 方法 | 詳細資料 |
| --- | --- |
| [](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/page-parameters.md)<br>頁面參數 (又稱為「mbox 參數」) | 頁面參數是直接透過頁面程式碼傳入的名稱/值配對，不儲存在訪客的設定檔中供未來使用。<br>頁面參數很適合將額外的頁面資料傳送至 Target，這些資料不需要隨著訪客的設定檔一起儲存，以供未來鎖定目標使用。這些值改用來說明頁面，或使用者在特定頁面上採取的動作。 |
| [](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/in-page-profile-attributes.md)<br>頁面內設定檔屬性 (又稱為「mbox 內設定檔屬性) | 頁面內設定檔參數是直接透過頁面程式碼傳遞的名稱/值配對，儲存在訪客的設定檔中供未來使用。<br>頁面內設定檔屬性允許將使用者特定的資料儲存在 Target 的設定檔中，供稍後鎖定目標和分割。 |
| [指令碼設定檔屬性](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/script-profile-attributes.md) | 指令碼設定檔屬性是 Target 解決方案中定義的名稱/值配對。值取決於每次伺服器呼叫在 Target 的伺服器上執行 JavaScript 片段。<br>使用者撰寫較小的程式碼片段，在每次 mbox 呼叫時執行，以及在評估訪客的對象和活動成員資格之前執行。 |
| [資料提供者](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/data-providers.md) | 資料提供者是一種功能，可讓您輕鬆將資料從第三方傳遞至Target。 |
| 大量設定檔更新 API | 透過 API，將 .csv 檔案傳送至 Target，此檔案包含許多訪客的訪客設定檔更新項目。一次呼叫就能以多個頁面內設定檔屬性來更新每一個訪客設定檔。 |
| 單一設定檔更新 API | 幾乎與「大量描述檔更新API」相同，但每次會更新一個訪客描述檔，並以API呼叫的行式，而非。csv檔案。 |
| 客戶屬性 | 客戶屬性可讓您透過 FTP 將訪客設定檔資料上傳至 Experience Cloud。上傳後，即可在 Adobe Analytics 和 Adobe Target 中運用這些資料。 |







## 大量設定檔更新 API {#section_92AB4820A5624C669D9A1F1B6220D4FA}

透過 API，將 .csv 檔案傳送至 Target，此檔案包含許多訪客的訪客設定檔更新項目。一次呼叫就能以多個頁面內設定檔屬性來更新每一個訪客設定檔。

此選項很類似於「客戶屬性」，只有輕微差異:

* 「客戶屬性」使用 FTP 上傳，而 Target「大量設定檔更新 API」使用 HTTP POST API。
* 客戶屬性資料可以與 Analytics 共用。大量設定檔更新只能 Target 中使用。
* 「客戶屬性」支援為 Target 尚未看到的使用者建立設定檔。「大量設定檔更新 API」只會更新現有 Target 設定檔。
* 「客戶屬性」需要使用 Experience Cloud ID (ECID)。「大量設定檔更新 API」需要 TNT ID 或 `mbox3rdPartyId`。
* 您無法在 `mbox3rdPartyID` 中傳送下列字元: 加號 (+) 和正斜線 (/)。

### 格式

.csv 檔案必須透過訪客的 Target PCID 或 mboxThirdPartyId 來參照每一個訪客。不支援 Experience Cloud ID (ECID)。所有設定檔屬性/值都是透過 API 來建立和更新。API 文件中提供格式詳細資料。

### 範例使用案例

CRM 或其他內部系統中儲存關於訪客的實用資料 (您希望持續更新至 Target)，不會讓設定檔資料在頁面實作中曝光。

### 方法優點

設定檔屬性的數量不限。

透過網站傳送的設定檔屬性可以透過 API 更新，反之亦然。

### 注意事項

批次檔的大小必須小於 50 MB。此外，每次上傳的總列數不得超過 500,000 列。

在 24 小時期間內，不限制後續批次中可上傳的列數。不過，在上班時間可以節流汲取程序，以確保其他程序的執行效率。

對相同的 thirdPartyIds 採用連續 [V2 批次更新呼叫](https://developers.adobetarget.com/api/#updating-profiles)，且其中不需使用 mbox 呼叫，會覆寫第一次批次更新呼叫所更新的屬性。

### 代碼範例

請參閱[更新設定檔](https://developers.adobetarget.com/api/#updating-profiles)。

### 相關資訊的連結

[更新設定檔](https://developers.adobetarget.com/api/#updating-profiles)

## 單一設定檔更新 API {#section_5D7A9DD7019F40E9AEF2F66F7F345A8D}

幾乎與「大量描述檔更新API」相同，但每次會更新一個訪客描述檔，並以API呼叫的行式，而非。csv檔案。

### 格式

必須透過 Target mboxPC 值或 mboxThirdPartyId 值來識別訪客。不支援 Experience Cloud ID (ECID)。

### 範例使用案例

當訪客執行一些離線動作，您需要即時更新 Target，例如聯絡客戶服務中心、獲得貸款、在商店中使用尊榮卡、使用資訊站等。

### 方法優點

設定檔屬性的數量不限。

透過網站傳送的設定檔屬性可以透過 API 更新，反之亦然。

### 注意事項

24 小時期間內以 1,000,000 次 API 呼叫 (1 百萬) 為限制。

只更新設定檔。無法為 Target 尚未看到的潛在使用者建立設定檔。

### 代碼範例

支援 GET 和 POST。  `https://CLIENT.tt.omtrdc.net/m2/client/profile/update?mboxPC=1368007744041-575948.01_00&profile.attr1=0&profile.attr2=1...`

### 相關資訊的連結

[更新設定檔](https://developers.adobetarget.com/api/#updating-profiles)

## 客戶屬性 {#section_C47FC7980A9A4608BD1A5F0BD900FA70}

客戶屬性可讓您透過 FTP 將訪客設定檔資料上傳至 Experience Cloud。上傳後，即可在 Adobe Analytics 和 Adobe Target 中運用這些資料。

Target Standard 客戶可使用 5 個屬性，Target Premium 客戶可使用 200 個屬性。

### 格式

含有 Experience Cloud ID (ECID) 和屬性名稱/值配對的 .csv 檔案是透過 FTP 上傳，或在 Experience Cloud UI 中手動上傳。

### 範例使用案例

您的 CRM 或其他內部系統儲存實用的資訊，可以與 Adobe 的 Experience Cloud 共用，包括 Target 和 Analytics。

### 方法優點

上傳客戶資料會在 Target 中針對該訪客建立設定檔項目，即使 Target 尚未看過該訪客也一樣。

相同的資料會自動出現在 Target 和 Analytics 中。

FTP 是比 API 更簡單的實作方法。

### 注意事項

Target Standard 客戶可使用 5 個屬性，Target Premium 客戶可使用 200 個屬性

只能透過「客戶屬性」來更新值，而不是在頁面上更新。

需要 Experience Cloud ID (ECID) 實作。

### 代碼範例

如需詳細資訊，請參閱[建立客戶屬性來源並上傳資料檔案](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html)。

### 相關資訊的連結

[建立客戶屬性來源及上傳資料檔案](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html).
