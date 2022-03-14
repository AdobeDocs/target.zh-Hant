---
keywords: Recommendations;設定;偏好設定;行業別;篩選不相容的條件;預設主機群組;縮圖基底 url;建議 api token
description: '瞭解如何在Adobe Target執行Recommendations活動。 '
title: 如何實施Recommendations活動？
feature: Recommendations
exl-id: b6edb504-a8b6-4379-99c1-6907e71601f9
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1295'
ht-degree: 36%

---

# ![高級](/help/main/assets/premium.png) 規劃和實施 [!DNL Recommendations]

在設定之前 [!DNL Recommendations] 活動 [!DNL Adobe Target]，完成以下步驟：

1. [實施 [!DNL Target]](#implement-target) 用於捕獲用戶行為和提供建議案的Web和移動應用曲面。
1. [設定 [!DNL Recommendations] 目錄](#rec-catalog) 要向用戶推薦的產品或內容。
1. [傳遞行為資訊和上下文](#pass-behavioral) 至 [!DNL Target Recommendations] 讓它提供個性化的建議。
1. [配置全局排除](#exclusions)。
1. [配置 [!DNL Recommendations] 設定](#concept_C1E1E2351413468692D6C21145EF0B84)。

## 實作 [!DNL Target] {#implement-target}

[!DNL Target Recommendations] 要求您實施 [!DNL Adobe Experience Platform Web SDK] 或at.js 0.9.2（或更高版本）。 請參閱 [實施 [!DNL Target]](/help/main/c-implementing-target/implementing-target.md) 的子菜單。

## 設定您的Recommendations目錄 {#rec-catalog}

要提供高質量的建議， [!DNL Target] 必須瞭解您要推薦的產品或內容。 您的目錄通常應包含三種類型的有關您要推薦的項目的資訊。 假設您推薦電影。 包括以下內容：

1. 您要向收到建議的使用者顯示的資料。例如，可以顯示影片名稱和影片海報縮略圖的URL。
1. 適合用於套用行銷和推銷控制的資料。例如，可以顯示影片的分級，以便不推薦NC-17影片。
1. 用於確定項目與其他項目的相似性的資料。 例如，可以顯示影片的流派和影片導演。

[!DNL Target] 提供了多個整合選項來填充目錄。 這些選項可以組合使用來更新目錄中的不同項目，或在不同頻率上更新不同的項目屬性。

| 方法 | 是什麼 | 使用時機 | 其他資訊 |
| --- | --- | --- | --- |
| 目錄源 | 計畫源(CSV、Google產品XML或 [!DNL Analytics Product Classifications])，每天上傳和攝入。 | 用於一次發送多個項的資訊。 用於發送不常更改的資訊。 | 請參閱 [源](/help/main/c-recommendations/c-products/feeds.md)。 |
| 實體API | 調用API以發送單個項的即時更新。 | 用於每次發送一個項目的更新。 用於發送頻繁更改的資訊（例如價格、庫存/庫存水準）。 | 查看 [實體API開發者文檔](https://developers.adobetarget.com/api/recommendations/#tag/Entities)。 |
| 在頁面上傳遞更新 | 使用頁面上的JavaScript或Delivery API發送單個項的即時更新。 | 用於每次發送一個項目的更新。 用於發送頻繁更改的資訊（例如價格、庫存/庫存水準）。 | 請參閱 [物料視圖/產品頁](#items-product-pages) 下。 |

大多數客戶應至少實施一個源。 然後，您可以選擇使用「實體API」或「頁面上」方法，通過頻繁更改的屬性或項的更新來補充源。

## 傳遞行為資訊和上下文 {#pass-behavioral}

您應傳遞給的行為資訊和上下文 [!DNL Target] 取決於您的訪問者正在執行的操作，此操作通常與訪問者正在交互的頁面類型相關聯。

### 物料視圖/產品頁 {#items-product-pages}

在訪問者正在查看單個項目的頁面上，您應傳遞訪問者正在查看的項目的標識。 您還應將訪問者正在查看的項目的最細粒度類別傳遞，以便將建議過濾到當前類別。

您還可以在產品頁面本身傳遞某些快速更改的屬性。 例如，您可以傳遞價格(`value`)及庫存/庫存水準。

```
<script type="text/javascript">
function targetPageParams() { 
   return { 
      "entity": { 
         "id": "32323", 
         "categoryId": "running-shoes", 
         "value": 119.99, 
         "inventory": 329 
      } 
   } 
}
</script>
```

### 類別視圖/類別頁

在類別頁面上，您可能希望將建議限制為該類別中的產品或內容。 為此，請確保傳遞當前查看的類別的標識。

```
function targetPageParams() { 
   return { 
      "entity": { 
         "categoryId": "running-shoes" 
      } 
   } 
}
```

### 購物車添加/購物車視圖/結帳頁 {#cart}

在購物車頁面上，您可以根據訪問者當前購物車的內容推薦項目。 為此，請使用特殊參數傳遞訪問者當前購物車中所有項目的ID `cartIds`。

```
function targetPageParams() {
   return {
      "cartIds": ["352", "223", "23432", "432", "553"]
      }
}
```

有關 [!UICONTROL 基於購物車] 建議，請參閱 [基於購物車](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#cart-based) 在 *基於建議密鑰的建議*。

### 排除訪問者購物車中已有的物料

在整個站點的頁面上，您可以從建議中排除某些項目。 例如，您可能不想建議訪問者當前購物車中已包含的物料。 為此，請使用特殊參數傳遞要排除的所有項的ID `excludedIds`。

```
function targetPageParams() {
   return {
      "excludedIds": ["352", "223", "23432", "432", "553"]
      }
}
```

### 採購/訂單確認頁

在發生採購事件時，傳遞已採購物料或物料的標識。 請參閱 [跟蹤轉換](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#task_E85D2F64FEB84201A594F2288FABF053) 在 *實施 [!DNL Target] 沒有標籤管理器*。

## 配置全局排除 {#exclusions}

排除您不希望向訪問者推薦的全局級別上的任何項目。 請參閱[排除項目](/help/main/c-recommendations/c-products/exclusions.md)。

## 配置 [!DNL Recommendations] 設定 {#concept_C1E1E2351413468692D6C21145EF0B84}

使用設定來管理您的 [!DNL Recommendations] 實作。

訪問 [!UICONTROL Recommendations設定] 選項，開啟 [!DNL Target] 的 [!DNL Adobe Experience Cloud]，然後按一下 **[!UICONTROL Recommendations]** > **[!UICONTROL 設定]**。

![](assets/recs_settings.png)

可使用下列選項: 

| 設定 | 說明 |
|--- |--- |
| 自訂全域 Mbox | (可選) 指定用來提供 [!DNL Target] 活動的自訂全域 mbox。預設情況下，由 [!DNL Target] 用於 [!DNL Recommendations]。<br>注：在 [!DNL Target] [!UICONTROL 管理] 的子菜單。 開啟 [!DNL Target]，然後按一下 [!UICONTROL 管理] > [!UICONTROL 視覺體驗作曲家]。 |
| 垂直產業 | 行業別用於協助將建議條件分類。此資訊有助於您的團隊成員查找對特定頁面有意義的標準，例如最適合購物車頁面或媒體頁面的標準。 |
| 篩選不相容的條件 | 啟用此選項只會顯示讓所選頁面傳遞必要資料的條件。並非每個條件都在每頁正確運行。 頁面或框必須傳入 `entity.id` 或 `entity.categoryId` 當前項目/當前類別建議的相容性。 一般來說，最好只顯示相容的條件。不過，如果您要讓活動可以使用不相容的條件，請取消勾選此選項。<br>如果您使用標記管理解決方案，建議您停用此選項。<br>如需此選項的詳細資訊，請參閱 [Recommendations 常見問題集](/help/main/c-recommendations/c-recommendations-faq/recommendations-faq.md)。 |
| 預設主機群組 | 選取預設主機群組。<br>主機群組可用來將目錄中可用項目區分為不同用途。例如，您可以將主機群組用於開發和生產環境、不同品牌或不同地理位置。依照預設，「目錄搜尋」、「集合」和「排除項目」中的預覽結果是根據預設主機群組所產生。(您也可以使用「環境」篩選器，選取不同的主機群組來預覽結果。)依照預設，除非在建立或更新項目時指定環境 ID，否則新增的項目可在所有主機群組中使用。提供的建議取決於要求中指定的主機群組。<br>如果沒有看見您的產品，請確定您使用正確的主機群組。例如，假設您將建議設定為使用測試環境，並將主機群組設為「測試」，則可能需要在測試環境中重建集合，才會顯示產品。若要查看每個環境中可用的產品，請對每個環境使用「目錄搜尋」。您也可以針對所選的環境 (主機群組)，預覽 Recommendations 集合和排除項目的內容。<br>**注意：** 變更選定環境後，您必須按一下「搜尋」來更新傳回的結果。<br>[!UICONTROL 「環境」]篩選器可在 [!DNL Target] UI 中的以下位置使用:<ul><li>「目錄搜尋」(「建議 > 目錄搜尋」)</li><li>「建立集合」對話方塊 ([!UICONTROL 「Recommendations > 集合 > 新建」])</li><li>「更新集合」對話方塊 ([!UICONTROL 「Recommendations > 集合 > 編輯」])</li><li>「建立排除項目」對話方塊 ([!UICONTROL 「Recommendations > 排除項目 > 新建」])</li><li>「更新排除項目」對話方塊 ([!UICONTROL 「Recommendations > 排除項目 > 編輯」])</li></ul>如需詳細資訊，請參閱[主機](/help/main/administrating-target/hosts.md)。 |
| 縮圖基底 URL | 設定產品目錄的基底 URL 可讓您在傳入縮圖 URL 時，使用相對 URL 來指定產品的縮圖。<br>例如:<br>`"entity.thumbnailURL=/Images/Homepage/product1.jpg"`<br>設定相對於縮圖基底 URL 的 URL。 |
| Recommendations API Token | 在「建議 API」呼叫中 (例如「下載 API」) 使用此 Token。 |
