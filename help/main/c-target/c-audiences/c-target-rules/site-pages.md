---
keywords: 網站頁面；目標網站頁面；鎖定目標；目前頁面；目標目前頁面；上一頁；目標上一頁；登陸頁面；目標登陸頁面；http標題
description: 瞭解如何使用鎖定訪客 [!DNL Adobe Target] 位在您網站特定頁面上的訪客。
title: 我可以根據網站頁面鎖定訪客嗎？
feature: Audiences
exl-id: 4c770b7b-775f-4483-aced-43f18a9a68c1
source-git-commit: 1383088bb2f6be0432e6f140400d8723048c8530
workflow-type: tm+mt
source-wordcount: '891'
ht-degree: 25%

---

# 網頁

您可以透過以下方式鎖定訪客： [!DNL Adobe Target] 存取您網站上特定頁面的使用者。

1. 在 [!DNL Target] 介面中，按一下&#x200B;**[!UICONTROL 「對象」]**>**[!UICONTROL 「建立對象」]**。
1. 為對象命名並新增選擇性說明。
1. 拖放 **[!UICONTROL 網頁]** 放入對象產生器窗格。

   ![網頁受眾](assets/target_site_pages.png)

1. 按一下 **[!UICONTROL 選取]** 從下拉式清單中選取下列其中一個選項，然後視需要設定規則。

   規則中後續下拉式清單中的可用選項和評估程式，會依您選擇的選項而有所不同。 下圖顯示當您選擇時，可用的選項 [!UICONTROL 目前頁面]：

   ![目前頁面](assets/current-page.png)

   當您選擇時，下列選項可在初始下拉式清單中使用 [!UICONTROL 選取].

   * **[!UICONTROL 目前頁面]：** 使用者正在檢視的頁面。

      如果您選擇此選項，則可在第二個下拉式清單中使用下列選項：

      * [!UICONTROL URL] (如需如何操作的詳細資訊， [!DNL Target] 評估URL，請參閱 [鎖定目標和對象常見問題集](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md).)
      * [!UICONTROL 網域]
      * [!UICONTROL 查詢]
      * [!UICONTROL 子網域]
      * [!UICONTROL 頂層網域]
      * [!UICONTROL 路徑]
      * [!UICONTROL 雜湊 (#) 片段]
   * **[!UICONTROL 上一頁]：** 按一下目前頁面之前已檢視使用者的頁面。 使用者必須從上一頁點按至目前頁面，才能追蹤頁面。 如果使用者在瀏覽器中鍵入新URL，則不會追蹤上一頁。 本頁面實際內容視乎網站設計而定。例如，如果目前頁面顯示特定產品的資訊，則上一頁可能是訪客選取特定專案的類別頁面。 例如，顯示某個型別之數個相機的頁面，或是指向最後一頁的首頁。

      如果您選擇此選項，則可在第二個下拉式清單中使用下列選項：

      * [!UICONTROL URL] (如需Target如何評估URL的詳細資訊，請參閱 [鎖定目標和對象常見問題集](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md).)
      * [!UICONTROL 網域]
      * [!UICONTROL 查詢]
      * [!UICONTROL 子網域]
      * [!UICONTROL 頂層網域]
      * [!UICONTROL 路徑]
   * **著陸頁面:** 著陸頁面為存取您的網站時，訪客看到的第一頁。例如，如果訪客在 Google 上點按一個連接進入類別頁面，那麼該類別頁面即為著陸頁面。如果該連接引導至您的首頁，那麼首頁即為著陸頁面。按訪客作業記憶著陸頁面。您可以依據此作業中的訪客著陸頁面，在網站實施深度指向。

      如果您選擇此選項，則可在第二個下拉式清單中使用下列選項：

      * [!UICONTROL URL] (如需Target如何評估URL的詳細資訊，請參閱 [鎖定目標和對象常見問題集](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md).)
      * [!UICONTROL 網域]
      * [!UICONTROL 查詢]
      * [!UICONTROL 子網域]
      * [!UICONTROL 頂層網域]
      * [!UICONTROL 路徑]
      * [!UICONTROL 雜湊 (#) 片段]

      >[!NOTE]
      >
      >在變更子網域或直接更換 URL 時會重設 `landing.url` 物件。

   * **[!UICONTROL HTTP標頭]：** 此選項會評估以下專案的HTTP標頭中的資訊： [!DNL Target] 要求。 例如，如果HTTP標頭包含語言資訊，您可以建立包含 `Accept-Language: es` 以西班牙文存取頁面的目標訪客條件。

      如果您選擇此選項，則可在第二個下拉式清單中使用下列選項：

      * [!UICONTROL 接受]
      * [!UICONTROL Accept-Charset]
      * [!UICONTROL Accept-Encoding]
      * [!UICONTROL Accept-Language]
      * [!UICONTROL 授權]
      * [!UICONTROL Cache-Control]
      * [!UICONTROL 連線]
      * [!UICONTROL Content-Length]
      * [!UICONTROL Content-MDS]
      * [!UICONTROL Content-Type]
      * [!UICONTROL 日期]
      * [!UICONTROL Expect]
      * [!UICONTROL 開始日期]
      * [!UICONTROL 主機]
      * [!UICONTROL If-Match]
      * [!UICONTROL If-Modified-Since]
      * [!UICONTROL If-None-Match]
      * [!UICONTROL If-Range]
      * [!UICONTROL If-Unmodified-Since]
      * [!UICONTROL Max-Forwards]
      * [!UICONTROL Pragma]
      * [!UICONTROL Proxy-Authorization]
      * [!UICONTROL 範圍]
      * [!UICONTROL Referrer]
      * [!UICONTROL TE]
      * [!UICONTROL 升級]
      * [!UICONTROL User-Agent]
      * [!UICONTROL Via]
      * [!UICONTROL 警告]

   如果您選擇 [!UICONTROL 目前頁面]， [!UICONTROL 上一頁]，或 [!UICONTROL 登陸頁面]，則 [!UICONTROL 網域] 和 [!UICONTROL 查詢] 選項可供使用。 選擇這些選項時，請考量下列事項：

   * **網域:** 頁面的完整網域。指定網域時，最佳做法是使用「包含」。例如，「網域等於facebook.com」不接受 `m.facebook.com` 或 `www.facebook.com`. 「網域包含facebook.com」接受facebook.com的任何變體。
   * **查詢:** 第一個問號 (?) 之後的 URL 內容。

      `foo.html?e0a72cb2a2c7`





1. （選用）為對象設定其他規則。
1. 按一下&#x200B;**[!UICONTROL 「完成」]**。

您也可以使用自己的「使用者定義查詢參數」或「使用者定義標題」，以建立網站頁面對象。

使用:

* 查詢引數(如果使用者選取的規則為 [!UICONTROL 目前頁面]， [!UICONTROL 登陸頁面]，或 [!UICONTROL 上一頁]
* 標頭（如果使用者選取的規則是HTTP標頭）

## 疑難排解 {#ts}

* 為了讓登入頁面對象正常運作，請求必須具備 `mboxReferrer` 引數集(對於傳送API， `context.address.referringUrl` 引數)，此at.js JavaScript程式庫是使用 `document.referrer` 屬性。 此 `HTMLDocument` attribute會傳回使用者已導覽之頁面的URI。 當使用者直接導覽至頁面時（不是透過連結，而是透過書籤），此屬性的值是空字串。

   如果此行為不符合您的需求，請考慮執行下列其中一項動作：

   * 通過 [mbox引數](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/global-mbox/pass-parameters-to-global-mbox.html){target=_blank} 至 [!DNL Target] 用於鎖定目標。
   * 使用 [A/B測試活動](/help/main/c-activities/t-test-ab/test-ab.md) 而不是登陸頁面活動。 A/B測試活動不會切換相同訪客的體驗。
   * 使用 [訪客設定檔](/help/main/c-target/c-audiences/c-target-rules/visitor-profile.md) 而非。

* 對包含逗號的字串使用「開頭/結尾為」評估器時，這些字串會評估為一組值，其中每個值都以逗號分隔。 例如，如果您有標題的值： `Accept-Language: en,zh;q=0.9,en-IN;q=0.8,zh-CN;q=0.7` 它符合以下條件：
   * 以zh開頭，
   * 開頭為en，
   * 結尾為0.7，
   * 結尾為0.8。

## 訓練影片: 建立對象

此影片包括關於使用對象類別的資訊。

* 建立對象
* 定義對象類別

>[!VIDEO](https://video.tv.adobe.com/v/17392)
