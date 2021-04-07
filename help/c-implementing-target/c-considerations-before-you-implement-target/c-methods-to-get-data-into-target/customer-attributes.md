---
keywords: 實施；實施；設定；設定；客戶屬性
description: 使用客戶屬性將資料匯入Target。
title: 如何使用客戶屬性將資料匯入Target?
feature: 實施
role: Developer
translation-type: tm+mt
source-git-commit: e8c25685341319fea4381386cad1ce0c5b80face
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 56%

---

# 客戶屬性

客戶屬性可讓您透過 FTP 將訪客設定檔資料上傳至 [!DNL Adobe Experience Cloud]. 上傳後，請使用[!DNL Adobe Analytics]和[!DNL Adobe Target]中的資料。

Target Standard客戶可套用5個屬性，Target Premium客戶可套用200個屬性。

## 格式

含有 Experience Cloud ID (ECID) 和屬性名稱/值配對的 .csv 檔案是透過 FTP 上傳，或在 Experience Cloud UI 中手動上傳。

## 範例使用案例

您的 CRM 或其他內部系統儲存實用的資訊，可以與 Adobe 的 Experience Cloud 共用，包括 Target 和 Analytics。

## 方法的優點

上傳客戶資料會在 Target 中針對該訪客建立設定檔項目，即使 Target 尚未看過該訪客也一樣。

相同的資料會自動出現在 Target 和 Analytics 中。

FTP 是比 API 更簡單的實作方法。

## 注意事項

Target Standard客戶可套用5個屬性，Target Premium客戶可套用200個屬性

只能透過「客戶屬性」來更新值，而不是在頁面上更新。

需要 Experience Cloud ID (ECID) 實作。

## 程式碼範例

如需詳細資訊，請參閱[建立客戶屬性來源並上傳資料檔案](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html)。

### 相關資訊的連結

[建立客戶屬性來源及上傳資料檔案](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html).