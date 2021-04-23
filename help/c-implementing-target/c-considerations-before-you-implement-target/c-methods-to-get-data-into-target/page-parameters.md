---
keywords: 實施；實施；設定；設定；頁面參數
description: 使用頁面參數將資料匯入 [!DNL Target] 。
title: 如何使用頁面參數將資料匯入 [!DNL Target] ?
feature: 實施
role: Developer
exl-id: a285eadc-b71e-49a8-9071-397ada283baf
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 46%

---

# 頁面參數

頁面參數（也稱為「mbox參數」）是直接透過頁面代碼傳遞的名稱／值配對，不會儲存在訪客的描述檔中以供日後使用。

頁面參數對於傳送頁面資料至Target非常有用，因為Target不需要與訪客的描述檔一起儲存，以便日後進行定位。 這些值改用來說明頁面，或使用者在特定頁面上採取的動作。

## 格式

頁面參數以字串名稱/值配對形式，透過伺服器呼叫而傳入 Target。參數名稱和值可自訂 (但有一些「保留名稱」是特定用途)。

### 範例

* `page=productPage`

* `categoryId=homeLoans`

## 範例使用案例

* **產品頁面**:傳送有關已檢視特定產品的資訊(此方法是Recommendations的運作方式)
* **訂單詳細資訊**:傳送訂單ID、orderTotal等，以收集訂單
* **類別相關性**: 將類別檢視資訊傳送至 Target，以瞭解使用者與特定網站類別的相關性
* **第三方資料**: 傳送來自第三方資料來源的資訊，例如，天氣鎖定目標提供者、帳戶資料 (例如 DemandBase)、人口統計資料 (例如 Experian) 及其他。

## 方法的優點

資料會即時傳送至Target，並可用於相同的伺服器上，呼叫資料所在的資料。

## 注意事項

* 需要頁面程式碼更新 (直接或透過標記管理系統)。
* 如果資料必須用於後續頁面／伺服器呼叫的定位，則必須轉譯為描述檔指令碼。
* 查詢字串僅可包含符合[網際網路工程任務小組 (IETF) 標準](https://www.ietf.org/rfc/rfc3986.txt)的字元。

   除了IETF站點上提及的字元之外， Target還允許查詢字串中包含以下字元：

   `&lt; > # % &quot; { } | \\ ^ \[\] \``

   除此之外的字元都必須經過 URL 編碼。此標準指定下列格式([https://www.ietf.org/rfc/rfc1738.txt](https://www.ietf.org/rfc/rfc1738.txt))，如下所示：

   ![](assets/ietf1.png)

   或者，為簡單起見，下列為完整清單:

   ![](assets/ietf2.png)

## 程式碼範例

targetPageParamsAll (將參數附加至頁面上的所有 mbox 呼叫):

`function targetPageParamsAll() { return "param1=value1&param2=value2&p3=hello%20world";`

targetPageParams (將參數附加至頁面上的全域 mbox):

`function targetPageParams() { return "param1=value1&param2=value2&p3=hello%20world";`

mboxCreate 程式碼中的參數:

`<div class="mboxDefault"> default content to replace by offer </div> <script> mboxCreate('mboxName','param1=value1','param2=value2'); </script>`

## 相關資訊的連結

建議: [根據頁面類型實作](/help/c-recommendations/plan-implement.md#reference_DE38BB07BD3C4511B176CDAB45E126FC)

訂單確認: [追蹤轉換](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#task_E85D2F64FEB84201A594F2288FABF053)

類別相關性: [類別相關性](/help/c-target/c-visitor-profile/category-affinity.md#concept_75EC1E1123014448B8B92AD16B2D72CC)
