---
keywords: Recommendations;介紹;簡介;研討會;示範
description: 了解 Adobe [!DNL Target] 中的 Recommendations 活動，這些活動會根據先前的使用者活動或其他演算法，自動顯示可能吸引客戶的內容。
title: 什麼是 Recommendations 活動？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
exl-id: bc4d9a46-ea21-4687-b8a0-7f2e1dc33ebf
source-git-commit: 2a25fdb42ce4470f9126b7e0e7f6fd9e60c350e5
workflow-type: tm+mt
source-wordcount: '2114'
ht-degree: 90%

---

# Recommendations 簡介

本文中的文字內容來自&#x200B;*Recommendations 簡介*&#x200B;網路研討會，您可在下方查看其完整內容。

*Recommendations 簡介*&#x200B;網路研討會包含有關如何運用 [!DNL Adobe Target Recommendations] 的值的深入探討。瞭解此 [!DNL Target] 活動如何根據先前的造訪最佳化即時建議，藉此自動顯示可能使您的客戶感興趣的產品或內容。此外，深入探討 [!DNL Target] UI，瞭解如何建置 [!DNL Recommendations] 活動的逐步概覽。

## 簡介

我們都瞭解在零售業所看到的建議種類。客戶對這些種類的建議有越來越高的期望，並使用它們做為探索其他可用選項的起點。如果您思考一下自己的購物行為，就會發現這些種類的建議十分有效。我們當中的所有人幾乎都買了在某處 (無論是商店或是數位屬性) 的建議中第一眼看到的產品。

下圖說明顯示經常搭配新手機購買之配件的建議，包括充電座、保護套和耳機。

![顯示其他人已搭配新手機購買之配件的建議。](/help/main/c-recommendations/assets/intro-1.png)

但我們不總是在想，數位優先品牌如何提高客戶期望的標準。 我們使用媒體和內容的方式，越來越受到個人化建議的推動。試想一下您在開啟 Netflix、Spotify 或 YouTube 時第一眼看到的內容。這些品牌透過建議開啟了客戶體驗。在有更多替代方案可用的世界中，您必須在客戶進行互動時為其找出最相關的內容。

![顯示數位優先品牌的建議](/help/main/c-recommendations/assets/intro-2.png)

行銷人員使用 [!DNL Adobe Target] 推動各行各業、各種客戶類型及管道的個人化體驗。

[!DNL Adobe Target] 可隨時隨地提供個人化內容。

![插圖顯示 Target 如何在各種位置提供建議](/help/main/c-recommendations/assets/intro-3.png)

* **發佈**：網站發佈者使用 [!DNL Target Recommendations] 向網站訪客建議文章並促進更多互動。
* **影片教學課程**：[!DNL Adobe Creative Cloud] 使用 [!DNL Target]，在 Photoshop 應用程式中向 Photoshop 使用者建議影片教學課程。
* **遊戲**：遊戲公司使用 [!DNL Target]，在使用者的遊戲主機上向其建議遊戲和內容。
* **B2B 銷售**：[企業對企業公司使用 Target，向 B2B 潛在客戶建議影片、白皮書和部落格文章、提供下載，以及為現有客戶提供協助](https://theblog.adobe.com/testing-shifts-high-gear-intel)。

* **旅遊**：[某個德國旅行社使用 Target 向旅客建議旅館及其他內容](https://2017.summit.adobe.com/na/sessions/summit-online/online-2017/#17608)。

* **零售**：[某個領先業界的 B2B 零售商使用 Target，向瀏覽器及其行動應用程式中的回訪訪客建議最熱門的類別與產品](https://theblog.adobe.com/optimization-personalization-b2b-powerhouse-grainger/)。

這些只是客戶使用 Target 提供個人化建議的一些方式。

提供絕佳建議需要哪些要素？

![插圖顯示提供絕佳建議之三個元素](/help/main/c-recommendations/assets/intro-4.png)

絕佳建議應提供相關且個人化的內容。也就是說，您需要下列三個要素，來促進相關性和個人化:

* **行銷人員控制**，協助促進建議項目的相關性。身為行銷人員，您負責提供寶貴的內容，而且您知道哪些產品屬性或內容與建議模型相關且可供考慮。如果您經營影片網站，您知道使用者可能有興趣觀賞來自同一位導演的影片，但可能不介意觀賞由同一工作室製作的電影。 [!DNL Target] 能讓您擁有控制的能力，可讓您透過此領域知識增強演算法。
* **精密的模型**，將目錄和互動事件中的數百萬個項目轉換成有意義的資料。[!DNL Target] 具有根據長達十年經驗所打造的精密機器學習功能，而且我們每年處理數十億個建議。
* **使用者內容**，確保可為使用者提供及時且相關的建議。您不想建議某人剛觀看的影片，或某人剛新增至購物車的襯衫。 Target的豐富使用者設定檔可用於建議，以確保個人化。

## 實作 [!DNL Target] Recommendations

首先，請從策略開始。

![插圖顯示建議策略](/help/main/c-recommendations/assets/intro-5.png)

* **您想要建議哪些項目？** 首先，請思考您想要建議哪些項目。可能是產品、影片或內容。
* **您要在哪個位置顯示建議？** 接下來，請思考您要在哪個位置提供建議。廣泛來說，就是哪些管道 (網路、行動裝置、店內、資訊站等)？ 客戶使用之旅的哪些環節會包含建議？ 網站上的哪些頁面會包含建議？
* **如何判斷建議是否成功？** 假設您有一個不含建議的體驗以及一個含有建議的體驗，或者您有兩個不同類型的建議。如何判斷哪個體驗對客戶來說是更好的體驗？ 某些量度可能比其他量度更難測量。例如，建議對客戶期限值的影響通常很難直接取得。因此，通常取得一個較不抽象的量度以及一個較明確的量度會比較簡單，例如每次造訪帶來的收入、平均訂購值或點按次數。在某些情況下，您可能會想要將量度最小化，例如支援服務通話的數量。

在想出策略之後，您就可以開始實施 [!DNL Target Recommendations] 了。

建立建議實施包含三個廣泛的步驟:

![插圖顯示建立建議實施之步驟](/help/main/c-recommendations/assets/intro-6.png)

1. 教導 [!DNL Target] 您的內容或產品。
1. 擷取使用者行為。
1. 透過正確的內容取得建議。

### 教導 [!DNL Target] 您的內容或產品

開始使用 [!DNL Recommendations] 時，您傳送有關您要建議之所有項目的資訊。[!DNL Target] 提供可建立目錄的多個整合選項。

![插圖顯示如何教導 Target 您的內容或產品](/help/main/c-recommendations/assets/intro-7.png)

最簡單且最常用的方法就是，每天或每週從您的產品資訊管理系統或內容管理系統傳送 CSV 檔案。但您也可以使用 [!DNL Adobe Target] JavaScript 程式庫從頁面傳送資料層上的資訊、運用 API 直接從來源系統傳送資訊，或是如果您已將目錄資料傳送至 [!DNL Analytics]，則使用 [!DNL Adobe Analytics] 整合。

有時候您可能會想要一起使用多個選項，例如，每天透過 CSV 檔案傳送大多數資料，以及透過 API 更頻繁地傳送庫存更新。

IT 部門通常會參與此過程並協助您完成設定。

無論您選擇哪種方法，都應在三個類別中包含有關各個項目的中繼資料:

![插圖顯示目錄的中繼資料資訊](/help/main/c-recommendations/assets/intro-8.png)

* 您要向收到建議的使用者顯示的資料。例如，電影名稱和縮圖影像 URL。
* 適合用於套用行銷和推銷控制的資料。例如，電影分級，以免建議 NC-17 電影。
* 適合用於判斷項目與其他項目之相似度的資料。例如，電影類型或電影中的演員。

### 擷取使用者行為

接下來，您應新增標記或運用現有 [!DNL Analytics] 實施，追蹤推動 [!DNL Target] 演算法的轉換事件 (例如檢視和購買)。

![插圖顯示如何擷取使用者行為](/help/main/c-recommendations/assets/intro-9.png)

您必須確保 [!DNL Target] 知道使用者檢視及購買的項目。如果購買與您的內容無關，您可能想要追蹤不同類型的轉換事件，例如下載PDF、完成調查、訂閱電子報、觀看影片等。

如果您已使用 [!DNL Target] 在網站上執行 A/B 測試活動，您可能已完成此步驟。或者，如果您已使用 [!DNL Adobe Analytics] 回報網站造訪和轉換行為，您可使用 [!DNL Analytics] 做為行為資料來源。如果沒有，最簡單的做法是使用標籤管理員（例如中的標籤）進行此設定 [[!DNL Adobe Experience Platform]](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/deploy-at-js/implement-target-using-adobe-launch.html){target=_blank}. 您也可以將離線或應用程式內的互動傳送至 [!DNL Target] 透過即時API。

### 透過正確的內容取得建議

在進行互動的時間點將使用者與內容的相關資訊傳送至 [!DNL Target]，以傳回相關和個人化建議。

![插圖顯示如何透過正確的內容取得建議](/help/main/c-recommendations/assets/intro-10.png)

除了彙總形式的使用者行為以外，您還必須將顯示建議之特定內容傳送給 [!DNL Target]。這包括頁面的相關資訊和來自使用者設定檔的資訊。[!DNL Target] 使用此資訊提供個人化建議。例如，在零售網站上，您想要瞭解訪客正在檢視的產品和產品類別。您也想要瞭解關於該使用者的資訊 (最愛的品牌、最愛的產品類別、忠誠度級別等)。此資訊非常重要，這樣 [!DNL Target] 才能篩選項目並改善建議的個人化成效。

## 建立第一個 Recommendations 活動

什麼是 [!DNL Recommendations] 活動？

![插圖顯示建立良好 Recommendations 活動之環節](/help/main/c-recommendations/assets/intro-11.png)

[!DNL Recommendations] 活動由下列元件構成:

* **對象**：誰應該看到這些建議？
* **條件**：應建議哪些項目？
* **設計**：應如何顯示建議項目？

![插圖顯示構成 Recommendations 活動的元素：對象、條件和設計](/help/main/c-recommendations/assets/intro-12.png)

[!DNL Target] 隨附立即可用的 14 個內建對象、42 個內建條件，以及 10 個內建設計範本。您可以逐一自訂這些項目，或新增您自己的項目。我們之前 [關於建立受眾的網路研討會](https://landing.adobe.com/acs/2018/na/adobe-target/registration.html) in [!DNL Target]. 本節重點在於如何定義條件，這會定義將建議哪些項目。

Target 使用條件卡的概念。條件卡就像個人化的方式。

![條件卡插圖](/help/main/c-recommendations/assets/intro-13.png)

請務必選擇或建立正確的條件，以達到您想要的個人化結果。條件就像漏斗，能將您從整個目錄帶到最終的一組建議。

![漏斗插圖](/help/main/c-recommendations/assets/intro-14.png)

以下章節說明此漏斗的各個環節及其在 [!DNL Target] 中的運作方式:

### 靜態篩選 (集合和條件)

靜態篩選是可範圍適用的規則，與您不希望經常變更的目錄屬性相關。

![集合和排除插圖](/help/main/c-recommendations/assets/intro-16.png)

例如，在內容環境中，您可能會想要在建議中包含所有電影，但排除分級為 NC-17 的電影。在零售內容中，您可能有位於全世界不同區域的多個品牌，但您只想要建議可在美國提供的產品。您可能也會想要從地區私人標籤中排除產品。

這些全都是可廣泛適用的目錄屬性，您可能想要用於多個建議，且不希望它們經常變更。

### 演算法 (建議索引鍵和邏輯)

下一步是選擇建議索引鍵和邏輯。這是您決定建議之基礎的位置。

![演算法插圖](/help/main/c-recommendations/assets/intro-17.png)

您需要選擇的第一個項目是建議索引鍵。建議索引鍵是您「查詢」以選擇建議的內容。這是建議所根據的內容。

建議可以根據下列內容:

* 訪客目前正在檢視的項目
* 訪客目前正在檢視的類別
* 訪客上次購買或新增至購物車的項目
* 與某個訪客戶項目有關的自訂屬性

接著，您可根據這些索引鍵選擇想要的建議邏輯:

* 具有類似屬性的項目
* 某個特定類別中檢視次數最多的項目
* 已購買此項目的客戶也購買了這些項目
* 自訂屬性

[!DNL Target] 隨附一應俱全且立即可用的演算法。

![一應俱全的演算法插圖](/help/main/c-recommendations/assets/intro-15.png)

* **基於人氣的演算法**&#x200B;包含檢視次數最多和最暢銷商品。
* **基於內容的演算法**&#x200B;包含內容相似度。
* **基於項目的合作篩選演算法**&#x200B;包含已檢視/已檢視、已檢視/已購買，以及已購買/已購買。請注意，「已購買」可能是任何轉換。
* **個人化演算法**&#x200B;包含最近查看的、網站相關性，以及已增強設定檔的合作篩選。
* **自備演算法**&#x200B;可讓您使用自己的自訂演算法。

### 線上業務規則

最後一個步驟是套用線上業務規則。透過此步驟，您可讓演算法擁有領域知識，以及根據訪客正在數位屬性上執行之作業的目前內容。

![線上業務規則插圖](/help/main/c-recommendations/assets/intro-18.png)

例如，在內容環境中，您可能會想要排除訪客之前已觀看的電影、建議同一位導演的電影，或提升相同類型的電影。在零售內容中，您可能會想要排除沒有庫存的產品、顯示價格範圍介於 $5 到 $500 美元之間的項目，或提升來自相同品牌的項目。

## 示範

在您如上所述完成建議漏斗插圖中的工作後，就剩下最終建議了。若要觀看 [!DNL Target] 內的產品內示範，此示範會在 21:00 於 *Adobe Target 基礎網路研討會*&#x200B;中開始進行，連結如下。

## Adobe [!DNL Target] 基礎網路研討會：Recommendations 簡介 {#intro-to-recs}

[Recommendations 簡介](https://adobecustomersuccess.adobeconnect.com/p8gt31drhs3e/?OWASP_CSRFTOKEN=4bd6cac5d0806167ee0a5449ba93d6300548d09c922bcb751c38973897a5703a)
