---
keywords: 實施；設定；設定；客戶屬性；implement;implementing;setting;setup;customer attributes
description: 將資料 [!DNL Target] 使用客戶屬性。
title: 如何將資料 [!DNL Target] 是否使用客戶屬性？
feature: Implementation
role: Developer
exl-id: b6c4a286-7994-492d-bde9-346af7aa314f
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 56%

---

# 客戶屬性

客戶屬性可讓您透過 FTP 將訪客設定檔資料上傳至 [!DNL Adobe Experience Cloud]. 上載後，請使用 [!DNL Adobe Analytics] 和 [!DNL Adobe Target]。

目標標準客戶可以應用五個屬性，目標高級客戶可以應用200個屬性。

## 格式

含有 Experience Cloud ID (ECID) 和屬性名稱/值配對的 .csv 檔案是透過 FTP 上傳，或在 Experience Cloud UI 中手動上傳。

## 示例使用案例

您的 CRM 或其他內部系統儲存實用的資訊，可以與 Adobe 的 Experience Cloud 共用，包括 Target 和 Analytics。

## 方法的益處

上傳客戶資料會在 Target 中針對該訪客建立設定檔項目，即使 Target 尚未看過該訪客也一樣。

相同的資料會自動出現在 Target 和 Analytics 中。

FTP 是比 API 更簡單的實作方法。

## 注意事項

目標標準客戶可以應用五個屬性，目標高級客戶可以應用200個屬性

只能透過「客戶屬性」來更新值，而不是在頁面上更新。

需要 Experience Cloud ID (ECID) 實作。

## 代碼示例

有關詳細資訊，請參閱 [建立客戶屬性源並上載資料檔案](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html)。

### 相關資訊的連結

[建立客戶屬性來源及上傳資料檔案](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html).
