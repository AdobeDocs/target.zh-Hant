---
keywords: 網頁；目標網頁；目標網頁；目標當前頁；上一頁；目標上一頁；登錄頁；目標登錄頁；http頭；
description: 瞭解如何使用 [!DNL Adobe Target] 在您網站的特定頁面上。
title: 我是否可以基於網站頁面來定向訪問者？
feature: Audiences
exl-id: 4c770b7b-775f-4483-aced-43f18a9a68c1
source-git-commit: b1e8ea2370fc15f4bfcd960ab2960cafe2db92b8
workflow-type: tm+mt
source-wordcount: '891'
ht-degree: 24%

---

# 網頁

您可以使用 [!DNL Adobe Target] 訪問您網站上的特定頁面。

1. 在 [!DNL Target] 介面中，按一下&#x200B;**[!UICONTROL 「對象」]**>**[!UICONTROL 「建立對象」]**。
1. 命名訪問群體並添加可選說明。
1. 拖放 **[!UICONTROL 網站頁]** 對話框。

   ![網頁受眾](assets/target_site_pages.png)

1. 按一下 **[!UICONTROL 選擇]** 下拉清單，選擇以下選項之一，然後根據需要配置規則。

   規則中後續下拉清單中的可用選項和計算器因您選擇的選項而異。 下圖顯示了如果選擇 [!UICONTROL 當前頁]:

   ![目前頁面](assets/current-page.png)

   選擇後，初始下拉清單中將提供以下選項 [!UICONTROL 選擇]。

   * **[!UICONTROL 當前頁]:** 用戶正在查看的頁面。

      如果選擇此選項，則第二個下拉清單中將提供以下選項：

      * [!UICONTROL URL] (有關如何 [!DNL Target] 評估URL，請參見 [目標和受眾常見問題](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md)。)
      * [!UICONTROL 網域]
      * [!UICONTROL 查詢]
      * [!UICONTROL 子網域]
      * [!UICONTROL 頂級域]
      * [!UICONTROL 路徑]
      * [!UICONTROL 雜湊 (#) 片段]
   * **[!UICONTROL 上一頁]:** 在按一下到當前頁之前查看用戶的頁。 用戶必須從上一頁按一下到當前頁，才能跟蹤要跟蹤的頁面。 如果用戶在瀏覽器中鍵入新URL，則不跟蹤上一頁。 本頁面實際內容視乎網站設計而定。例如，如果當前頁面顯示有關特定產品的資訊，則上一頁可能是訪問者選擇特定項目的類別頁面。 例如，顯示某種類型的多個攝像頭的頁面，或者可能是指向最終頁面的首頁。

      如果選擇此選項，則第二個下拉清單中將提供以下選項：

      * [!UICONTROL URL] (有關目標如何計算URL的詳細資訊，請參見 [目標和受眾常見問題](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md)。)
      * [!UICONTROL 網域]
      * [!UICONTROL 查詢]
      * [!UICONTROL 子網域]
      * [!UICONTROL 頂級域]
      * [!UICONTROL 路徑]
   * **著陸頁面:** 著陸頁面為存取您的網站時，訪客看到的第一頁。例如，如果訪客在 Google 上點按一個連接進入類別頁面，那麼該類別頁面即為著陸頁面。如果該連接引導至您的首頁，那麼首頁即為著陸頁面。按訪客作業記憶著陸頁面。您可以依據此作業中的訪客著陸頁面，在網站實施深度指向。

      如果選擇此選項，則第二個下拉清單中將提供以下選項：

      * [!UICONTROL URL] (有關目標如何計算URL的詳細資訊，請參見 [目標和受眾常見問題](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md)。)
      * [!UICONTROL 網域]
      * [!UICONTROL 查詢]
      * [!UICONTROL 子網域]
      * [!UICONTROL 頂級域]
      * [!UICONTROL 路徑]
      * [!UICONTROL 雜湊 (#) 片段]

      >[!NOTE]
      >
      >在變更子網域或直接更換 URL 時會重設 `landing.url` 物件。

   * **[!UICONTROL HTTP標頭]:** 此選項評估HTTP頭中的資訊 [!DNL Target] 請求。 例如，如果HTTP標頭包含語言資訊，則可以建立包含 `Accept-Language: es` 以西班牙語訪問該頁面的目標訪問者。

      如果選擇此選項，則第二個下拉清單中將提供以下選項：

      * [!UICONTROL 接受]
      * [!UICONTROL 接受 — 字元集]
      * [!UICONTROL 接受編碼]
      * [!UICONTROL Accept-Language]
      * [!UICONTROL 授權]
      * [!UICONTROL Cache-Control]
      * [!UICONTROL 連線]
      * [!UICONTROL Content-Length]
      * [!UICONTROL 內容 — MDS]
      * [!UICONTROL Content-Type]
      * [!UICONTROL 日期]
      * [!UICONTROL 預期]
      * [!UICONTROL 開始日期]
      * [!UICONTROL 主機]
      * [!UICONTROL If-Match]
      * [!UICONTROL If-Modified-Sine]
      * [!UICONTROL 無匹配]
      * [!UICONTROL If-Range]
      * [!UICONTROL If-Unmodified-Sine]
      * [!UICONTROL 最大轉發]
      * [!UICONTROL Pragma]
      * [!UICONTROL 代理授權]
      * [!UICONTROL 範圍]
      * [!UICONTROL Referrer]
      * [!UICONTROL TE]
      * [!UICONTROL 升級]
      * [!UICONTROL User-Agent]
      * [!UICONTROL 通過]
      * [!UICONTROL 警告]

   如果您選擇 [!UICONTROL 當前頁]。 [!UICONTROL 上一頁]或 [!UICONTROL 登錄頁]，也請參見Wiki頁。 [!UICONTROL 域] 和 [!UICONTROL 查詢] 選項。 選擇這些選項時，請考慮以下事項：

   * **網域:** 頁面的完整網域。指定網域時，最佳做法是使用「包含」。例如，「域等於facebook.com」不接受 `m.facebook.com` 或 `www.facebook.com`。 &quot;域包含facebook.com&quot;接受任何變體的facebook.com。
   * **查詢:** 第一個問號 (?) 之後的 URL 內容。

      `foo.html?e0a72cb2a2c7`





1. （可選）為受眾設定其他規則。
1. 按一下&#x200B;**[!UICONTROL 「完成」]**。

您也可以使用自己的「使用者定義查詢參數」或「使用者定義標題」，以建立網站頁面對象。

使用:

* 查詢參數(如果用戶選擇的規則為 [!UICONTROL 當前頁]。 [!UICONTROL 登錄頁]或 [!UICONTROL 上一頁]
* 如果用戶選擇的規則是HTTP標頭，則顯示標題

## 疑難排解 {#ts}

* 要使登錄頁訪問群體正常運行，請求必須具有 `mboxReferrer` 參數集(對於Delivery API, `context.address.referringUrl` at.js JavaScript庫從頁面中使用 `document.referrer` 屬性。 此 `HTMLDocument` 屬性返回用戶從中導航的頁的URI。 當用戶直接導航到頁面時（不是通過連結，而是通過書籤），此屬性的值是空字串。

   如果此行為與您的要求不匹配，請考慮執行下列操作之一：

   * 通過 [mbox參數](https://developer.adobe.com/target/implement/client-side/atjs/global-mbox/pass-parameters-to-global-mbox/) 至 [!DNL Target] 用於目標。
   * 使用 [A/BTest活動](/help/main/c-activities/t-test-ab/test-ab.md) 而不是登錄頁活動。 A/BTest活動不會為同一訪問者切換體驗。
   * 使用 [訪問者簡介](/help/main/c-target/c-audiences/c-target-rules/visitor-profile.md) 的雙曲餘切值。

* 當對包含逗號的字串使用「開頭/結尾為」計算器時，這些字串將作為值陣列計算，在該陣列中，將計算每個以逗號分隔的值。 例如，如果標題的值為： `Accept-Language: en,zh;q=0.9,en-IN;q=0.8,zh-CN;q=0.7` 它符合以下條件：
   * 以z開頭，
   * 以en開頭，
   * 以0.7結尾，
   * 以0.8結尾。

## 訓練影片: 建立對象

此影片包括關於使用對象類別的資訊。

* 建立對象
* 定義對象類別

>[!VIDEO](https://video.tv.adobe.com/v/17392)
