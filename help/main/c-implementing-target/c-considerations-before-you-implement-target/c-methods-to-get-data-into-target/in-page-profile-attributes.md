---
keywords: 實現；實現；設定；設定；page參數
description: 將資料 [!DNL Target] 使用頁內配置檔案屬性。
title: 如何將資料 [!DNL Target] 是否使用頁內配置檔案屬性？
feature: Implementation
role: Developer
exl-id: c6000720-a862-4e9c-96a5-055963a79544
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 57%

---

# 頁面中設定檔屬性

中的頁內配置檔案屬性 [!DNL Adobe Target] （也稱為「收件箱配置檔案屬性」）是直接通過頁面代碼傳遞的名稱/值對，這些代碼儲存在訪問者的配置檔案中，以供將來使用。

頁面內設定檔屬性允許將使用者特定的資料儲存在 Target 的設定檔中，供稍後鎖定目標和分割。

## 格式

頁面內設定檔屬性以字串名稱/值配對形式，透過伺服器呼叫而傳入 Target，字首 &quot;profile.&quot; 會加在屬性名稱之前。

屬性名稱和值可自訂 (但有一些「保留名稱」是特定用途)。

### 範例

* `profile.membershipLevel=silver`
* `profile.visitCount=3`

## 示例使用案例

* **登入資訊**: 根據使用者的登入將非 PII (個人識別資訊) 資料與 Target 共用。此資料可以是成員身份狀態、訂單歷史記錄或更多。
* **商店資訊**: 追蹤哪一家商店是此使用者偏好的位置。
* **先前的互動**: 追蹤使用者先前在網站上完成的動作，以提供未來個人化的相關資訊。

## 方法的益處

資料即時發送到目標，並可用於資料所在的同一伺服器調用。

## 注意事項

需要頁面程式碼更新 (直接或透過標記管理系統)。

屬性和值在伺服器呼叫中可見，所以訪客可以看到值。如果共用信用範圍等資訊或其他可能的私有資訊，則此方法可能不是最佳方法。

## 代碼示例

targetPageParamsAll (將屬性附加至頁面上的所有 mbox 呼叫):

`function targetPageParamsAll() { return "profile.param1=value1&profile.param2=value2&profile.p3=hello%20world"; }`

targetPageParams (將屬性附加至頁面上的全域 mbox):

`function targetPageParams() { return profile.param1=value1&profile.param2=value2&profile.p3=hello%20world"; }`

mboxCreate 程式碼中的屬性:

`<div class="mboxDefault"> default content to replace by offer </div> <script> mboxCreate('mboxName','profile.param1=value1','profile.param2=value2'); </script>`

## 相關資訊的連結

[描述檔屬性](/help/main/c-target/c-visitor-profile/profile-parameters.md#concept_01A30B4762D64CD5946B3AA38DC8A201)

[訪客設定檔](/help/main/c-target/c-audiences/c-target-rules/visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E)
