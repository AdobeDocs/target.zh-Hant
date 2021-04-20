---
keywords: 實施；實施；設定；設定；頁面參數
description: 使用頁面內描述檔屬性將資料匯入Target。
title: 如何使用頁面內描述檔屬性將資料匯入Target?
feature: Implementation
role: Developer
exl-id: c6000720-a862-4e9c-96a5-055963a79544
translation-type: tm+mt
source-git-commit: 20daf4510e754d77cd16be64770105932178fec5
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 56%

---

# 頁面內描述檔屬性

[!DNL Adobe Target]中的頁面內描述檔屬性（也稱為&quot;in-mbox描述檔屬性&quot;）是直接透過頁面程式碼傳遞的名稱／值配對，會儲存在訪客的描述檔中以供日後使用。

頁面內設定檔屬性允許將使用者特定的資料儲存在 Target 的設定檔中，供稍後鎖定目標和分割。

## 格式

頁面內設定檔屬性以字串名稱/值配對形式，透過伺服器呼叫而傳入 Target，字首 &quot;profile.&quot; 會加在屬性名稱之前。

屬性名稱和值可自訂 (但有一些「保留名稱」是特定用途)。

### 範例

* `profile.membershipLevel=silver`
* `profile.visitCount=3`

## 範例使用案例

* **登入資訊**: 根據使用者的登入將非 PII (個人識別資訊) 資料與 Target 共用。此資料可以是會籍狀態、訂單記錄等。
* **商店資訊**: 追蹤哪一家商店是此使用者偏好的位置。
* **先前的互動**: 追蹤使用者先前在網站上完成的動作，以提供未來個人化的相關資訊。

## 方法的優點

資料會即時傳送至Target，並可用於資料傳入的相同伺服器呼叫。

## 注意事項

需要頁面程式碼更新 (直接或透過標記管理系統)。

屬性和值在伺服器呼叫中可見，所以訪客可以看到值。如果共用信用範圍或其他潛在私人資訊等資訊，此方法可能不是最佳方法。

## 程式碼範例

targetPageParamsAll (將屬性附加至頁面上的所有 mbox 呼叫):

`function targetPageParamsAll() { return "profile.param1=value1&profile.param2=value2&profile.p3=hello%20world"; }`

targetPageParams (將屬性附加至頁面上的全域 mbox):

`function targetPageParams() { return profile.param1=value1&profile.param2=value2&profile.p3=hello%20world"; }`

mboxCreate 程式碼中的屬性:

`<div class="mboxDefault"> default content to replace by offer </div> <script> mboxCreate('mboxName','profile.param1=value1','profile.param2=value2'); </script>`

## 相關資訊的連結

[設定檔屬性](/help/c-target/c-visitor-profile/profile-parameters.md#concept_01A30B4762D64CD5946B3AA38DC8A201)

[訪客資料](/help/c-target/c-audiences/c-target-rules/visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E)
