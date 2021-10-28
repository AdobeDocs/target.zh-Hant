---
keywords: Recommendations;設定;偏好設定;行業別;篩選不相容的條件;預設主機群組;縮圖基底 url;建議 api token
description: '了解如何在Adobe Target中實作Recommendations活動。 '
title: 如何實作Recommendations活動？
feature: Recommendations
exl-id: b6edb504-a8b6-4379-99c1-6907e71601f9
source-git-commit: 802ed4cc03973ee61ff3e40930b137422868835b
workflow-type: tm+mt
source-wordcount: '1544'
ht-degree: 30%

---

# ![PREMIUM](/help/assets/premium.png) 計畫和實作 [!DNL Recommendations]

設定您的第一個 [!DNL Recommendations] 活動 [!DNL Adobe Target]，請完成下列步驟：

1. [實作 [!DNL Target]](#implement-target) 應用程式頁面上，擷取使用者行為並傳送建議時使用。
1. [設定您的 [!DNL Recommendations] 目錄](#rec-catalog) 產品或內容，以向使用者建議。
1. [傳遞行為資訊和內容](#pass-behavioral) to [!DNL Target Recommendations] 以便提供個人化建議。
1. [設定全域排除](#exclusions).
1. [設定 [!DNL Recommendations] 設定](#concept_C1E1E2351413468692D6C21145EF0B84).

## 實作 [!DNL Target] {#implement-target}

[!DNL Target Recommendations] 需要您實作 [!DNL Adobe Experience Platform Web SDK] 或at.js 0.9.2（或更新版本）。 請參閱 [實作 [!DNL Target]](/help/c-implementing-target/implementing-target.md) 以取得更多資訊。

## 設定您的Recommendations目錄 {#rec-catalog}

若要提供高品質的建議， [!DNL Target] 必須知道您要建議的產品或內容。 您的目錄通常應包含三種關於您要建議之項目的資訊。 假設您要推薦電影。 納入下列項目：

1. 您要向收到建議的使用者顯示的資料。例如，您可以顯示電影名稱，以及電影海報縮圖影像的URL。
1. 適合用於套用行銷和推銷控制的資料。例如，您可以顯示電影分級，以便不建議NC-17電影。
1. 適合用來判斷項目與其他項目片段相似度的資料。 例如，您可以顯示電影類型和電影導演。

[!DNL Target] 提供多個整合選項以填入目錄。 這些選項可以組合使用來更新目錄中的不同項目，或更新不同頻率上的不同項目屬性。

| 方法 | 是什麼 | 使用時機 | 其他資訊 |
| --- | --- | --- | --- |
| 目錄摘要 | 排程摘要(CSV、Google產品XML或 [!DNL Analytics Product Classifications])上傳及擷取。 | 用於一次傳送多個項目的相關資訊。 用於傳送不常變更的資訊。 | 請參閱 [動態消息](/help/c-recommendations/c-products/feeds.md). |
| 實體API | 呼叫API以傳送單一項目的最新更新。 | 用於一次傳送大約一個項目的更新。 用於傳送經常變更的資訊（例如價格、庫存/庫存水準）。 | 請參閱 [實體API開發人員檔案](https://developers.adobetarget.com/api/recommendations/#tag/Entities). |
| 在頁面上傳遞更新 | 使用頁面上的JavaScript或使用傳送API，針對單一項目立即傳送更新。 | 用於一次傳送大約一個項目的更新。 用於傳送經常變更的資訊（例如價格、庫存/庫存水準）。 | 請參閱 [項目檢視/產品頁面](#items-product-pages) 下方。 |

大部分的客戶應至少實作一個摘要。 然後，您可以選擇使用實體API或頁面上方法，以經常變更屬性或項目的更新補充您的摘要。

## 傳遞行為資訊和內容 {#pass-behavioral}

您應傳遞至的行為資訊和內容 [!DNL Target] 取決於訪客正在採取的動作，而此動作通常與訪客正在互動的頁面類型相關聯。

### 項目檢視/產品頁面 {#items-product-pages}

在訪客檢視單一項目的頁面上（例如產品詳細資料頁面），您應傳遞訪客檢視之項目的身分。 您也應該傳遞訪客正在檢視之項目最精細的類別，以允許篩選建議至目前類別。

您也可以在產品頁面本身傳遞某些快速變更的屬性。 例如，您可以傳遞價格(`value`)和庫存/庫存水準。

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

### 類別檢視/類別頁面

在類別頁面上，您可能會想要將建議限制在該類別中的產品或內容。 若要這麼做，請確定您傳遞目前已檢視類別的身分。

```
function targetPageParams() { 
   return { 
      "entity": { 
         "categoryId": "running-shoes" 
      } 
   } 
}
```

### 購物車新增/購物車檢視/結帳頁面 {#cart}

在購物車頁面上，您可以根據訪客目前購物車的內容來建議項目。 若要這麼做，請使用特殊參數，傳遞訪客目前購物車中所有項目的ID `cartIds`.

```
function targetPageParams() {
   return {
      "cartIds": ["352", "223", "23432", "432", "553"]
      }
}
```

購物車型建議邏輯類似於「[!UICONTROL 建議您]&quot;基於用戶的算法和到&quot;[!UICONTROL 瀏覽過這些、也購買了的人]&quot;和&quot;[!UICONTROL 購買、購買的人]」項目型演算法。

[!DNL Target] 使用協作篩選技術來判斷訪客購物車中每個項目的相似度，然後結合每個項目的這些行為相似度，以取得合併的清單。

[!DNL Target] 此外，行銷人員可以選擇在單一工作階段或跨多個工作階段查看訪客行為：

* **在單一工作階段內**:根據其他訪客在單一工作階段中所執行的操作。

   如果有感覺產品會根據使用狀況、時機或事件彼此強烈「搭配使用」，在單一工作階段中查看行為或許有意義。 例如，訪客正在購買打印機，因此可能還需要墨水和紙張。 或者，遊客正在購買花生醬，可能還需要麵包和果凍。

* **跨多個工作階段**:根據其他訪客在多個工作階段間所執行的動作。

   如果有感覺產品會根據訪客偏好或品味彼此強烈「搭配」，則跨多個工作階段查看行為或許有意義。 例如，某位訪客喜歡《星際大戰》，也可能喜歡《印地安納·瓊斯》，即使該訪客不一定想在同一時間看兩部電影。 或者，訪客喜歡棋盤遊戲「代號」，也可能喜歡棋盤遊戲「Avalon」，即使訪客無法同時玩兩個遊戲亦然。 

無論您是查看單一工作階段內或多個工作階段間的訪客行為， [!DNL Target] 根據訪客目前購物車中的項目，為每位訪客提供建議。

### 排除訪客購物車中已有的項目

在您網站的整個頁面上，您可以從建議中排除一些項目。 例如，您可能不想建議已位於訪客目前購物車中的項目。 若要這麼做，請使用特殊參數傳遞您要排除之所有項目的ID `excludedIds`.

```
function targetPageParams() {
   return {
      "excludedIds": ["352", "223", "23432", "432", "553"]
      }
}
```

### 購買/訂購確認頁面

發生購買事件時，傳遞已購買項目或項目的身分。 請參閱 [追蹤轉換](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#task_E85D2F64FEB84201A594F2288FABF053) in *實作 [!DNL Target] 沒有標籤管理員*.

## 設定全域排除 {#exclusions}

排除您絕不想建議給訪客的全域層級上的任何項目。 請參閱[排除項目](/help/c-recommendations/c-products/exclusions.md)。

## 設定 [!DNL Recommendations] 設定 {#concept_C1E1E2351413468692D6C21145EF0B84}

使用設定來管理您的 [!DNL Recommendations] 實作。

若要存取 [!UICONTROL Recommendations設定] 選項，開啟 [!DNL Target] 在 [!DNL Adobe Experience Cloud]，然後按一下 **[!UICONTROL Recommendations]** > **[!UICONTROL 設定]**.

![](assets/recs_settings.png)

可使用下列選項: 

| 設定 | 說明 |
|--- |--- |
| 自訂全域 Mbox | (可選) 指定用來提供 [!DNL Target] 活動的自訂全域 mbox。依預設，使用的全域mbox [!DNL Target] 用於 [!DNL Recommendations].<br>注意：此選項設定於 [!DNL Target] [!UICONTROL 管理] 頁面。 開啟 [!DNL Target]，然後按一下 [!UICONTROL 管理] > [!UICONTROL 可視化體驗撰寫器]. |
| 垂直產業 | 行業別用於協助將建議條件分類。此資訊可協助您的團隊成員尋找對特定頁面有意義的條件，例如最適合購物車頁面或媒體頁面的條件。 |
| 篩選不相容的條件 | 啟用此選項只會顯示讓所選頁面傳遞必要資料的條件。並非所有條件都會在每個頁面上正確執行。 頁面或mbox必須傳入 `entity.id` 或 `entity.categoryId` 讓目前項目/目前類別建議相容。 一般來說，最好只顯示相容的條件。不過，如果您要讓活動可以使用不相容的條件，請取消勾選此選項。<br>如果您使用標記管理解決方案，建議您停用此選項。<br>如需此選項的詳細資訊，請參閱 [Recommendations 常見問題集](/help/c-recommendations/c-recommendations-faq/recommendations-faq.md)。 |
| 預設主機群組 | 選取預設主機群組。<br>主機群組可用來將目錄中可用項目區分為不同用途。例如，您可以將主機群組用於開發和生產環境、不同品牌或不同地理位置。依照預設，「目錄搜尋」、「集合」和「排除項目」中的預覽結果是根據預設主機群組所產生。(您也可以使用「環境」篩選器，選取不同的主機群組來預覽結果。)依照預設，除非在建立或更新項目時指定環境 ID，否則新增的項目可在所有主機群組中使用。提供的建議取決於要求中指定的主機群組。<br>如果沒有看見您的產品，請確定您使用正確的主機群組。例如，假設您將建議設定為使用測試環境，並將主機群組設為「測試」，則可能需要在測試環境中重建集合，才會顯示產品。若要查看每個環境中可用的產品，請對每個環境使用「目錄搜尋」。您也可以針對所選的環境 (主機群組)，預覽 Recommendations 集合和排除項目的內容。<br>**注意：** 變更選定環境後，您必須按一下「搜尋」來更新傳回的結果。<br>[!UICONTROL 「環境」]篩選器可在 [!DNL Target] UI 中的以下位置使用:<ul><li>「目錄搜尋」(「建議 > 目錄搜尋」)</li><li>「建立集合」對話方塊 ([!UICONTROL 「Recommendations > 集合 > 新建」])</li><li>「更新集合」對話方塊 ([!UICONTROL 「Recommendations > 集合 > 編輯」])</li><li>「建立排除項目」對話方塊 ([!UICONTROL 「Recommendations > 排除項目 > 新建」])</li><li>「更新排除項目」對話方塊 ([!UICONTROL 「Recommendations > 排除項目 > 編輯」])</li></ul>如需詳細資訊，請參閱[主機](/help/administrating-target/hosts.md)。 |
| 縮圖基底 URL | 設定產品目錄的基底 URL 可讓您在傳入縮圖 URL 時，使用相對 URL 來指定產品的縮圖。<br>例如:<br>`"entity.thumbnailURL=/Images/Homepage/product1.jpg"`<br>設定相對於縮圖基底 URL 的 URL。 |
| Recommendations API Token | 在「建議 API」呼叫中 (例如「下載 API」) 使用此 Token。 |
