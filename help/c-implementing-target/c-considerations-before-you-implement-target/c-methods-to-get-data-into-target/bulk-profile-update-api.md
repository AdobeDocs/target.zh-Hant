---
keywords: 實施；實施；設定；設定；批量配置檔案更新
description: 使用大量描述檔更新API將資料匯入Target。
title: 如何使用大量描述檔更新API將資料匯入Target?
feature: 實施
role: Developer
translation-type: tm+mt
source-git-commit: e8c25685341319fea4381386cad1ce0c5b80face
workflow-type: tm+mt
source-wordcount: '379'
ht-degree: 78%

---

# 大量設定檔更新 API

透過API，傳送。csv檔案至[!DNL Adobe Target]，並更新許多訪客的訪客資料。 一次呼叫就能以多個頁面內設定檔屬性來更新每一個訪客設定檔。

此選項類似於「客戶屬性」，但有一些差異：

* 「客戶屬性」使用 FTP 上傳，而 Target「大量設定檔更新 API」使用 HTTP POST API。
* 客戶屬性資料可以與 Analytics 共用。大量設定檔更新只能 Target 中使用。
* 「客戶屬性」支援為 Target 尚未看到的使用者建立設定檔。「大量設定檔更新 API」只會更新現有 Target 設定檔。
* 「客戶屬性」需要使用 Experience Cloud ID (ECID)。「大量設定檔更新 API」需要 TNT ID 或 `mbox3rdPartyId`。
* 您無法在 `mbox3rdPartyID` 中傳送下列字元: 加號 (+) 和正斜線 (/)。

## 格式

.csv 檔案必須透過訪客的 Target PCID 或 mboxThirdPartyId 來參照每一個訪客。不支援 Experience Cloud ID (ECID)。所有設定檔屬性/值都是透過 API 來建立和更新。API 文件中提供格式詳細資料。

## 範例使用案例

CRM 或其他內部系統中儲存關於訪客的實用資料 (您希望持續更新至 Target)，不會讓設定檔資料在頁面實作中曝光。

## 方法的優點

設定檔屬性的數量不限。

透過網站傳送的設定檔屬性可以透過 API 更新，反之亦然。

## 注意事項

批次檔的大小必須小於 50 MB。此外，每次上傳的總列數不得超過 500,000 列。

在 24 小時期間內，不限制後續批次中可上傳的列數。不過，在上班時間可以節流汲取程序，以確保其他程序的執行效率。

對相同的 thirdPartyIds 採用連續 [V2 批次更新呼叫](https://developers.adobetarget.com/api/#updating-profiles)，且其中不需使用 mbox 呼叫，會覆寫第一次批次更新呼叫所更新的屬性。

## 程式碼範例

請參閱[更新設定檔](https://developers.adobetarget.com/api/#updating-profiles)。

### 相關資訊的連結

[更新設定檔](https://developers.adobetarget.com/api/#updating-profiles)