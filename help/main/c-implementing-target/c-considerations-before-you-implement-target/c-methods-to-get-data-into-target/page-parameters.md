---
keywords: 實現；實現；設定；設定；頁面參數
description: 將資料 [!DNL Target] 使用頁面參數。
title: 如何將資料 [!DNL Target] 是否使用頁面參數？
feature: Implementation
role: Developer
exl-id: a285eadc-b71e-49a8-9071-397ada283baf
source-git-commit: b1e8ea2370fc15f4bfcd960ab2960cafe2db92b8
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 44%

---

# 頁面參數

頁面參數（也稱為「mbox parameters」）是直接通過頁面代碼傳遞的名稱/值對，這些代碼未儲存在訪問者的配置檔案中以供將來使用。

頁面參數對於將頁面資料發送到目標非常有用，該目標不需要與訪問者的配置檔案一起儲存，以便將來進行目標使用。 這些值改用來說明頁面，或使用者在特定頁面上採取的動作。

## 格式

頁面參數以字串名稱/值配對形式，透過伺服器呼叫而傳入 Target。參數名稱和值可自訂 (但有一些「保留名稱」是特定用途)。

### 範例

* `page=productPage`

* `categoryId=homeLoans`

## 示例使用案例

* **產品頁**:發送有關查看的特定產品的資訊(此方法是Recommendations的工作方式)
* **訂單詳細資訊**:發送訂單集合的訂單ID、orderTotal等
* **類別相關性**: 將類別檢視資訊傳送至 Target，以瞭解使用者與特定網站類別的相關性
* **第三方資料**: 傳送來自第三方資料來源的資訊，例如，天氣鎖定目標提供者、帳戶資料 (例如 DemandBase)、人口統計資料 (例如 Experian) 及其他。

## 方法的益處

資料即時發送到目標，並且可以在同一伺服器上調用資料所在。

## 注意事項

* 需要頁面程式碼更新 (直接或透過標記管理系統)。
* 如果資料必須用於後續頁/伺服器調用的目標，則必須將其轉換為配置檔案指令碼。
* 查詢字串僅可包含符合[網際網路工程任務小組 (IETF) 標準](https://www.ietf.org/rfc/rfc3986.txt)的字元。

   除了IETF站點上提到的這些字元之外，目標還允許查詢字串中的以下字元：

   ```< > # % " { } | \ ^ [ ] ` ```

   除此之外的字元都必須經過 URL 編碼。該標準指定以下格式( [https://www.ietf.org/rfc/rfc1738.txt](https://www.ietf.org/rfc/rfc1738.txt) )，如下所示：

   ![](assets/ietf1.png)

   或者，為簡單起見，下列為完整清單:

   ![](assets/ietf2.png)

## 代碼示例

targetPageParamsAll (將參數附加至頁面上的所有 mbox 呼叫):

`function targetPageParamsAll() { return "param1=value1&param2=value2&p3=hello%20world";`

targetPageParams (將參數附加至頁面上的全域 mbox):

`function targetPageParams() { return "param1=value1&param2=value2&p3=hello%20world";`

## 相關資訊的連結

建議: [根據頁面類型實作](https://developer.adobe.com/target/implement/recommendations/)

訂單確認: [追蹤轉換](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-without-a-tag-manager/)

類別相關性: [類別相關性](/help/main/c-target/c-visitor-profile/category-affinity.md#concept_75EC1E1123014448B8B92AD16B2D72CC)
