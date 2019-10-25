---
description: 定位位在某個特定頁面上的訪客或具有特定 mbox 參數的訪客。
keywords: 網站頁面;目標網站頁面;鎖定目標;目前頁面;目標目前頁面;上一頁;目標上一頁;登陸頁面;目標登陸頁面;mbox;目標 mbox
seo-description: 您可以使用Adobe Target定位位於特定頁面或具有特定mbox參數的訪客。
seo-title: Adobe target中的網站頁面
solution: Target
title: 網頁
topic: Standard
uuid: 1cf9fa94-dbec-4719-9a0a-79c1eb91a233
translation-type: tm+mt
source-git-commit: d47772b35e371af4b6484ff59209de1c8482b712

---


# 網頁{#site-pages}

您可以定位位於特定頁面或具有特定mbox參數的訪客。

>[!NOTE]
>
>對象網站頁面類型和比較運算子，現在會在 Target Classic 中比對類型和比較運算子。您也可以使用自己的「使用者定義查詢參數」或「使用者定義標題」，以建立網站頁面對象。

1. 在 [!DNL Target] 介面中，按一下&#x200B;**[!UICONTROL 「對象]** &gt; **[!UICONTROL 建立對象」]**。
1. 為對象命名。
1. 按一下&#x200B;**[!UICONTROL 「新增規則]** &gt; **[!UICONTROL 網站頁面」]**。

   ![網頁受眾](assets/target_site_pages.png)

1. 按一下&#x200B;**[!UICONTROL 「選取」]**，然後選取下列其中一個選項:

   * **目前頁面:**&#x200B;使用者目前所在的頁面，即活動中包含 mbox 的頁面。如果您以活動層級為目標，這可能是含有您用來定義進入條件的 mbox 的頁面，或是顯示內容的頁面。如果您依據體驗進行指向，目前頁面就是顯示 mbox 所在的頁面。對於成功量度或轉換指向，那麼它便是那些 mboxe 所在的頁面。
   * **上一頁:** 點按目前頁面之前使用者所在的頁面。(使用者必須從上一頁點選至目前頁面，才能讓該頁面受到追蹤。如果使用者是在瀏覽器中輸入新的 URL，則上一頁就不會被追蹤。)本頁面實際內容視乎網站設計而定。舉例來說，如果目前頁面顯示的是有關特定產品的資訊，則上一頁可能是使用者在其中選擇特定商品的分類頁面 (例如顯示多台特定類型相機的頁面)，也可能是引導使用者來到最後頁面的首頁。
   * **著陸頁面:** 著陸頁面為存取您的網站時，訪客看到的第一頁。例如，如果訪客在 Google 上點按一個連接進入類別頁面，那麼該類別頁面即為著陸頁面。如果該連接引導至您的首頁，那麼首頁即為著陸頁面。按訪客作業記憶著陸頁面。您可以依據此作業中的訪客著陸頁面，在網站實施深度指向。

      >[!NOTE]
      >
      >在變更子網域或直接更換 URL 時會重設 `landing.url` 物件。

   * **Mbox:** 您正在定位的 mbox。例如，如果您想要對總計 $100 或以上的訂單進行計數，您可將 `orderTotal` 作為一個 mbox 參數連同在此指定的指向進行傳送。
   * **網域:** 頁面的完整網域。指定網域時，最佳做法是使用「包含」。例如，「網域等於 facebook.com」不接受 `m.facebook.com` 或 `www.facebook.com`。「網域包含 facebook.com」則會接受 facebook.com 的任何變體。
   * **查詢:** 第一個問號 (?) 之後的 URL 內容。

      `foo.html?e0a72cb2a2c7`

1. (可選) 按一下&#x200B;**[!UICONTROL 「新增規則」]並設定對象的其他規則。**
1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

您也可以使用自己的「使用者定義查詢參數」或「使用者定義標題」，以建立網站頁面對象。

使用:

* 查詢參數，如果使用者選取的規則是「目前頁面」、「登陸頁面」或「上一頁」。
* 標題，如果使用者選取的規則是「HTTP 檔頭」。

如下所示:

![](assets/site_pages.png)

## 疑難排解 {#ts}

* 若要讓著陸頁面對象正常運作，請求必須正確設 `mboxReferrer` 定mbox參數。 at.js javaScript程式庫會 `mboxReferrer` 使用從頁面擷取 `document.referrer`。

   如果未正確設定這些參數，訪客在導覽至後續頁面後可能會離開活動。 例如，若著陸 `document.referrer` 頁面上使用了該變數，但後續頁面上未使用，則無 [!DNL Target] 法確保訪客仍留在活動中。

   如果您遇到這種情況，請考慮執行下列操作之一：

   * 請確定您的網站已正確 `document.referrer` 載入。
   * 傳遞 [mbox參數](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/pass-parameters-to-global-mbox.md) , [!DNL Target] 以便用於定位目的。
   * 使用 [A/B測試活動](/help/c-activities/t-test-ab/test-ab.md) ，而非著陸頁面活動。 A/B測試活動不會切換相同訪客的體驗。
   * 請改用 [訪客資料](/help/c-target/c-audiences/c-target-rules/visitor-profile.md) 。

## 訓練影片: 建立對象

此影片包括關於使用對象類別的資訊。

* 建立對象
* 定義對象類別

>[!VIDEO](https://video.tv.adobe.com/v/17392?captions=chi_hant)
