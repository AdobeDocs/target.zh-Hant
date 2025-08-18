---
keywords: 網站頁面；目標網站頁面；鎖定目標；目前頁面；目標目前頁面；上一頁；目標上一頁；登陸頁面；目標登陸頁面；http標題
description: 瞭解如何使用 [!DNL Adobe Target] 鎖定網站特定頁面上的訪客。
title: 我可以根據網站頁面鎖定訪客嗎？
feature: Audiences
exl-id: 4c770b7b-775f-4483-aced-43f18a9a68c1
source-git-commit: fe1e97710e7692ba7724103853ed7438c3f361b1
workflow-type: tm+mt
source-wordcount: '800'
ht-degree: 19%

---

# 網頁

您可以使用存取您網站上特定頁面的[!DNL Adobe Target]來鎖定訪客。

1. 在[!DNL Target]介面中，按一下&#x200B;**[!UICONTROL Audiences]** > **[!UICONTROL Create Audience]**。
1. 為對象命名並新增選擇性說明。
1. 將&#x200B;**[!UICONTROL Site Pages]**&#x200B;拖放至對象產生器窗格。

   ![網頁客群](assets/target_site_pages.png)

1. 按一下&#x200B;**[!UICONTROL Select]**&#x200B;下拉式清單，選取下列其中一個選項，然後視需要設定規則。

   規則中後續下拉式清單中可用的選項和評估程式，會依您選擇的選項而有所不同。 下圖顯示選擇[!UICONTROL Current Page]時可用的選項：

   ![目前頁面](assets/current-page.png)

   當您選擇[!UICONTROL Select]時，下列選項可在初始下拉式清單中使用。

   * **[!UICONTROL Current Page]：**&#x200B;使用者正在檢視的頁面。

     如果您選擇此選項，則可在第二個下拉式清單中使用下列選項：

      * [!UICONTROL URL] （如需[!DNL Target]如何評估URL的詳細資訊，請參閱[鎖定目標和對象常見問題集](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md)。）
      * [!UICONTROL Domain]
      * [!UICONTROL Query]
      * [!UICONTROL Subdomain]
      * [!UICONTROL Top-Level Domain]
      * [!UICONTROL Path]
      * [!UICONTROL Hash (#) fragment]

   * **[!UICONTROL Previous Page]：**&#x200B;使用者在點按目前頁面之前檢視的頁面。 使用者必須從上一頁按一下到目前頁面，才能追蹤頁面。 如果使用者在瀏覽器中鍵入新URL，則不會追蹤上一頁。 本頁面實際內容視乎網站設計而定。例如，如果目前頁面顯示特定產品的相關資訊，則上一頁可能是訪客選取特定專案的類別頁面。 例如，顯示數部特定型別相機的頁面，或是導向最終頁面的首頁。

     如果您選擇此選項，則可在第二個下拉式清單中使用下列選項：

      * [!UICONTROL URL] （如需Target如何評估URL的詳細資訊，請參閱[鎖定目標和對象常見問題集](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md)。）
      * [!UICONTROL Domain]
      * [!UICONTROL Query]
      * [!UICONTROL Subdomain]
      * [!UICONTROL Top-Level Domain]
      * [!UICONTROL Path]

   * **[!UICONTROL Landing Page]：**&#x200B;登入頁面是訪客存取您的網站時看到的第一頁。 例如，如果訪客在 Google 上點按一個連接進入類別頁面，那麼該類別頁面即為著陸頁面。如果該連接引導至您的首頁，那麼首頁即為著陸頁面。按訪客作業記憶著陸頁面。您可以依據此作業中的訪客著陸頁面，在網站實施深度指向。

     如果您選擇此選項，則可在第二個下拉式清單中使用下列選項：

      * [!UICONTROL URL] （如需Target如何評估URL的詳細資訊，請參閱[鎖定目標和對象常見問題集](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md)。）
      * [!UICONTROL Domain]
      * [!UICONTROL Query]
      * [!UICONTROL Subdomain]
      * [!UICONTROL Top-Level Domain]
      * [!UICONTROL Path]
      * [!UICONTROL Hash (#) fragment]

     >[!NOTE]
     >
     >在變更子網域或直接更換 URL 時會重設 `landing.url` 物件。

   * **[!UICONTROL HTTP Header]：**&#x200B;此選項會評估[!DNL Target]要求的HTTP標頭中的資訊。 例如，如果HTTP標頭包含語言資訊，您可以建立包含`Accept-Language: es`條件的規則，以定位存取西班牙文頁面的訪客。

     如果您選擇此選項，則可在第二個下拉式清單中使用下列選項：

      * [!UICONTROL Accept]
      * [!UICONTROL Accept-Charset]
      * [!UICONTROL Accept-Encoding]
      * [!UICONTROL Accept-Language]
      * [!UICONTROL Authorization]
      * [!UICONTROL Cache-Control]
      * [!UICONTROL Connection]
      * [!UICONTROL Content-Length]
      * [!UICONTROL Content-MDS]
      * [!UICONTROL Content-Type]
      * [!UICONTROL Date]
      * [!UICONTROL Expect]
      * [!UICONTROL From]
      * [!UICONTROL Host]
      * [!UICONTROL If-Match]
      * [!UICONTROL If-Modified-Since]
      * [!UICONTROL If-None-Match]
      * [!UICONTROL If-Range]
      * [!UICONTROL If-Unmodified-Since]
      * [!UICONTROL Max-Forwards]
      * [!UICONTROL Pragma]
      * [!UICONTROL Proxy-Authorization]
      * [!UICONTROL Range]
      * [!UICONTROL Referrer]
      * [!UICONTROL TE]
      * [!UICONTROL Upgrade]
      * [!UICONTROL User-Agent]
      * [!UICONTROL Via]
      * [!UICONTROL Warning]

   若您選擇[!UICONTROL Current Page]、[!UICONTROL Previous Page]或[!UICONTROL Landing Page]，則可使用[!UICONTROL Domain]與[!UICONTROL Query]選項。 選擇這些選項時，請考量下列事項：

   * **網域:** 頁面的完整網域。指定網域時，最佳做法是使用「包含」。例如，「網域等於facebook.com」不接受`m.facebook.com`或`www.facebook.com`。 「網域包含facebook.com」接受facebook.com的任何變體。
   * **查詢：**&#x200B;第一個問號(？)之後的URL內容。

     `foo.html?e0a72cb2a2c7`

1. （選用）為對象設定其他規則。
1. 按一下 **[!UICONTROL Done]**。

您也可以使用自己的「使用者定義查詢參數」或「使用者定義標題」，以建立網站頁面對象。

使用:

* 若使用者選取的規則是[!UICONTROL Current Page]、[!UICONTROL Landing Page]或[!UICONTROL Previous Page]，則查詢引數
* 標頭（如果使用者選取的規則是HTTP標頭）

## 疑難排解 {#ts}

* 若要讓登入頁面對象正常運作，要求必須有`mboxReferrer`引數集（針對傳送API為`context.address.referringUrl`引數），at.js JavaScript資料庫會使用`document.referrer`屬性從頁面中取得該引數。 此`HTMLDocument`屬性會傳回使用者已導覽之頁面的URI。 當使用者直接導覽至頁面時（不是透過連結，而是例如透過書籤），此屬性的值是空字串。

  如果此行為不符合您的需求，請考慮執行下列其中一個動作：

   * 傳遞[mbox引數](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/global-mbox/pass-parameters-to-global-mbox.html){target=_blank}至[!DNL Target]以用於鎖定目標。
   * 使用[A/B測試活動](/help/main/c-activities/t-test-ab/test-ab.md)，而非登陸頁面活動。 A/B測試活動不會切換相同訪客的體驗。
   * 請改用[訪客設定檔](/help/main/c-target/c-audiences/c-target-rules/visitor-profile.md)。

* 對包含逗號的字串使用「開頭/結尾為」評估器時，這些字串會以一組值進行評估，而每個值都以逗號分隔。 例如，如果您有標頭的值： `Accept-Language: en,zh;q=0.9,en-IN;q=0.8,zh-CN;q=0.7`，則它符合條件，例如：
   * 以zh開頭，
   * 開頭為en，
   * 結尾為0.7，
   * 結尾為0.8。

## 訓練影片: 建立客群

此影片包括關於使用對象類別的資訊。

* 建立客群
* 定義對象類別

>[!VIDEO](https://video.tv.adobe.com/v/17392)
