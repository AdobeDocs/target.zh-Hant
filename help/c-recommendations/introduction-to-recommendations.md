---
description: Target Recommendations簡介活動：根據先前使用者活動或其他演算法自動顯示可能吸引客戶的產品或內容。Recommendations 可協助引導客戶至他們可能不知道的相關項目。
keywords: Recommendations;
seo-description: Adobe Target Recommendations活動簡介，可根據先前使用者活動或其他演算法自動顯示可能吸引客戶的產品或內容。Recommendations 可協助引導客戶至他們可能不知道的相關項目。
seo-title: Adobe Target中Recommendations活動簡介
solution: Target
title: 建議簡介
title-outputclass: premium
topic: Premium
badge: premium
translation-type: tm+mt
source-git-commit: 04a4585e1d56f1754b65a248715fa5bdd4f8986f

---


# ![高階](/help/assets/premium.png) 推薦推薦

The text in this article comes from the *Introduction to Recommendations* webinar, which you can view in its entirety below.

*「Recommendations簡介* 」網路研討會包含深入探討如何運用此值 [!DNL Adobe Target Recommendations]。瞭解此 [!DNL Target] 活動如何根據先前的造訪最佳化即時建議，藉此自動顯示可能使您的客戶感興趣的產品或內容。此外，深入探討 [!DNL Target] UI，瞭解如何建置 [!DNL Recommendations] 活動的逐步概覽。

## 簡介

我們都知道在零售業看到的建議種類。客戶會期待這些建議，並將它們用作探索其他可用選項的起點。如果您想一下自己的購物行為，這些建議就能正常運作。我們幾乎每個人都購買了一個我們在建議中看到的產品，無論是在商店還是在數位財產上。

下圖顯示一個建議，顯示一般透過新手機購買的配件，包括充電站、大小寫和耳機。

![建議顯示其他人使用新手機購買的配件。](/help/c-recommendations/assets/intro-1.png)

但我們不一定會想的是，數位品牌如何提高客戶期望。我們使用媒體和內容的方式越來越受到個人化推薦的驅動。想想開啓Netflix、Spotify或YouTube時所看到的第一件事。這些品牌透過建議開始客戶體驗。在提供更多替代方案的世界中，您可以在互動點識別客戶最相關的內容。

![顯示數位優先品牌的建議](/help/c-recommendations/assets/intro-2.png)

Marketers use [!DNL Adobe Target] to drive personalized experiences across a wide variety of industries, customer types, and channels.

[!DNL Adobe Target] 隨時隨地提供個人化內容。

![說明Target如何在不同位置提供建議的插圖](/help/c-recommendations/assets/intro-3.png)

* **發佈**：網頁出版業者可 [!DNL Target Recommendations] 用來推薦文章給網站訪客，並提高參與度。
* **教學課程**&#x200B;影片： [!DNL Adobe Creative Cloud] 用來 [!DNL Target] 向Photoshop應用程式中的Photoshop使用者推薦影片教學課程。
* **遊戲**：遊戲公司可用來 [!DNL Target] 向使用者建議遊戲和內容。
* **B2B銷售**：企業對企業的公司向 [!DNL Target] B2B潛在客戶推薦視訊、白皮書和部落格文章；提供下載；為現有客戶提供協助(https://theblog.adobe.com/testing-shifts-high-gear-intel)。
* **旅行**：德國旅行訂閱者使用 [!DNL Target] 旅行社向旅行者推薦更多服務(https://2017.summit.adobe.com/na/sessions/summit-online/online-2017/#17608)。
* **零售**&#x200B;業：知名B2B零售商使用 [!DNL Target] 推薦頂級類別和產品，以便在瀏覽器及其行動應用程式(https://theblog.adobe.com/optimization-personalization-b2b-powerhouse-grainger/)中傳回訪客。

以下只是客戶使用Target提供個人化建議的幾種方式。

甚麼是絕佳建議？

![這個插圖顯示了三個建立建議的元素](/help/c-recommendations/assets/intro-4.png)

出色的建議應保持相關性和個人化。這表示您需要三項因素來推動相關性和個人化：

* **行銷人員控制項** ，有助於推動建議項目的相關性。身為行銷人員，您會將寶貴的內容帶入表格，而您知道產品或內容的屬性與建議模型有何關聯性。如果您要執行視訊網站，您知道使用者可能會想觀賞同一部導演的影片，但可能不在乎同一個工作室所製作的影片。[!DNL Target] 提供控制項，讓您利用此網域知識增強演算法。
* **精密的模型** 可讓您在目錄和互動活動中呈現數百萬個項目。[!DNL Target] 具有超過10年經驗的精密機器學習功能，我們每年處理數十億個建議。
* **使用者上下文** ，以確保建議及時且與您的使用者相關。您不想推薦剛看過的影片或剛加入購物車的襯衫。Target的豐富使用者設定檔可用於建議，以確保個人化。

## 實作Target Recommendations

從策略開始。

![顯示建議策略的插圖](/help/c-recommendations/assets/intro-5.png)

* **您想要建議哪些項目？** 首先，請考慮建議的項目。這可以是產品、影片或內容。
* **您要在哪裡顯示建議？** 接下來，請思考您想要提出建議的位置。廣泛的管道(網路、行動裝置、店內、資訊站等)。客戶歷程中的哪些部分包含建議？您網站上的哪些頁面包含建議？
* **如何判斷建議是否成功？** 假設您擁有沒有建議和建議的體驗，或者有兩種不同類型的建議。如何決定哪種體驗對客戶有更好的體驗？有些量度可能比其他度量更難測量。例如，建議對客戶終身價值的影響通常很難直接獲得。因此，接觸較不抽象的量度通常比較簡單，例如，每次瀏覽收入、平均訂購值或點按次數都比較容易。在某些情況下，您可能會想將量度最小化，例如支援呼叫數。

After you come up with your strategy, you are ready to start the implementation of [!DNL Target Recommendations].

建立建議實作有三個廣泛步驟：

![顯示建立建議實作步驟的圖例](/help/c-recommendations/assets/intro-6.png)

1. Teach [!DNL Target] about your context or products.
1. 擷取使用者行為。
1. 透過正確的上下文獲取建議。

### Teach [!DNL Target] about your context or products

When you start with [!DNL Recommendations], you pass information about every item you want to recommend. [!DNL Target] 提供多種整合選項以建立您的目錄。

![說明如何教授Target相關內容或產品的插圖](/help/c-recommendations/assets/intro-7.png)

最簡單、最常用的方法是從產品資訊管理系統或您的內容管理系統，每日或每周傳送CSV檔案。But you can also pass information on the data layer from your page using the [!DNL Adobe Target] Javascript library, leverage our APIs to pass information directly from your source system, or use our [!DNL Adobe Analytics] integration if you are already passing catalog data to [!DNL Analytics].

有時候，您可能需要同時使用多個選項，例如透過CSV檔案每天傳遞大部分資料，以及透過API更頻繁地傳遞庫存更新。

您的IT部門通常會參與協助設定此步驟。

您選擇的Whicever方法，應該包含三個類別中每個項目的中繼資料：

![顯示目錄中繼資料資訊的插圖](/help/c-recommendations/assets/intro-8.png)

* 您要顯示給接收建議之使用者的資料。例如，影片的名稱和縮圖影象URL。
* 用於套用行銷和銷售控制項的資料。例如，影片的分級，讓您不建議使用NC-17影片。
* 用於決定項目對其他項目相似性的資料。例如影片的天才或影片中的演員。

### 擷取使用者行為

Next, you should add tags or leverage you existing [!DNL Analytics] implementation to track the conversion events (such as views and purchases) that drive [!DNL Target] algorithms.

![顯示如何擷取使用者行為的插圖](/help/c-recommendations/assets/intro-9.png)

You need to ensure that [!DNL Target] is aware of the items that your users are viewing and purchasing. 如果購買與您的上下文無關，您可能會想要追蹤不同類型的轉換事件，例如下載PDF、完成調查、訂閱電子報、觀看影片等等。

If you are already using [!DNL Target] to run A/B Tests activities on your site, you might have already completed this step. Or if you are already using [!DNL Adobe Analytics] to report on site visits and conversion behavior, you can use [!DNL Analytics] as your behavioral datasource. If not, it’s easiest to set this up using a tag manager such as [Adobe Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md). It’s also possible to send offline or in-app interactions to [!DNL Target] via real-time API.

### 以正確的情境獲取建議

Pass information about the user and context at the point of interaction to [!DNL Target] to return relevant and personalized recommendations.

![顯示如何使用正確內容取得建議的插圖](/help/c-recommendations/assets/intro-10.png)

Besides user behavior in aggregate, you need to pass [!DNL Target] the specific context where recommendations are being shown. 其中包括頁面的相關資訊，以及來自使用者個人資料的資訊。[!DNL Target] 使用此資訊建立個人化建議。例如，在零售網站上，您想要瞭解訪客目前正在檢視的產品和產品類別。您也希望瞭解該使用者的相關資訊(我的最愛品牌、最喜愛的產品類別、忠誠度層等)。This information is important so that [!DNL Target] can filter items and improve the personalization of recommendations.

## 建立您的第一個Recommendations活動

What is a [!DNL Recommendations] activity?

![顯示具有良好建議活動之部分的插圖](/help/c-recommendations/assets/intro-11.png)

[!DNL Recommendations] 活動由下列元件組成：

* **對象**：誰應該看到這些建議？
* **標準**：建議您使用哪些項目？
* **設計**：建議如何顯示建議的項目？

![顯示建議活動的圖例：觀眾、標準和設計](/help/c-recommendations/assets/intro-12.png)

Out of the box, [!DNL Target] includes 14 built-in audiences, 42 built-in criteria, and 10 built-in design templates. 您可以自訂每個項目或新增自己的項目。We’ve had previous [webinars about building audiences](https://landing.adobe.com/acs/2018/na/adobe-target/registration.html) in [!DNL Target]. 本節著重於定義標準，並將建議定義精靈項目。

Target使用標準卡的概念。標準卡片有如個人化方式。

![標準卡片插圖](/help/c-recommendations/assets/intro-13.png)

請務必選擇或建立適當條件，才能達到您想要的個人化結果。標準就像漏斗，將您從整個目錄帶入您的最終建議集。

![漏斗插圖](/help/c-recommendations/assets/intro-14.png)

The following sections describe the various parts of this funnel and how they work in [!DNL Target]:

### 靜態篩選器(系列和排除)

靜態篩選是與目錄屬性相關的廣泛規則，您不需要經常變更。

![系列和排除插圖](/help/c-recommendations/assets/intro-16.png)

例如，在內容內容中，您可能想要在建議中包含所有影片，但排除評分為NC-17的影片。在零售環境中，您可能有多個不同的品牌，但您希望僅建議在美國提供產品。您也可能想要從區域私人標籤排除產品。

這些是廣泛適用的目錄屬性，您可能希望在多個建議中使用，且您不希望這些屬性經常變更。

### 演算法(建議金鑰和邏輯)

下一步是選擇建議索引鍵和邏輯。您可以在這裡決定建議的基礎。

![演算法插圖](/help/c-recommendations/assets/intro-17.png)

您首先需要選擇的是建議金鑰。建議索引鍵是您「查閱」以選擇建議的項目。這是您建議的項目。

您可以依據下列建議來建立建議：

* 訪客目前正在檢視的項目
* 訪客目前檢視的類別
* 訪客上次購買或新增至購物車的項目
* 與訪客或項目相關的自訂屬性

根據這些按鍵，您接著選擇建議邏輯：

* 具有類似屬性的項目
* 特定類別中檢視最多的項目
* 購買此項目的客戶也購買了這些項目
* 自訂屬性

Out of the box, [!DNL Target] includes a portfolio of algorithms.

![演算法插圖組合](/help/c-recommendations/assets/intro-15.png)

* **基於人氣的演算法** 包括「已檢視次數最多」和「最暢銷商品」。
* **內容型演算法** 包含內容相似性。
* **項目型協同篩選演算法** 包括已檢視/已檢視、已檢視/購買，以及購買/購買。請注意，「購買」可以是任何轉換。
* **個人化演算法** 包括最近檢視、網站相關性和描述檔增強的協作篩選。
* **攜帶自有演算法可** 讓您使用自己的自訂演算法。

### 線上業務規則

最後一個步驟是套用線上業務規則。這是您根據訪客在您的數位屬性上所做的行為，賦予您網域知識和目前內容的能力。

![線上業務規則插圖](/help/c-recommendations/assets/intro-18.png)

例如，在內容內容中，您可能想要排除訪客先前觀看過的影片、建議相同導演的影片，或是將影片放大至相同的Genle。在零售內容中，您可能想要排除無存貨產品、以$到$的價格顯示項目，或從相同品牌中增加項目。

## 示範

完成上述建議漏斗中說明的工作後，您將會留下最終建議。To watch an in-product demonstration inside [!DNL Target], the demo begins at 21:00 in the *Adobe Target Basics Webinar*, linked to below.

## Adobe Target 基礎網路研討會: Recommendations 簡介 {#intro-to-recs}

[建議簡介](https://forums.adobe.com/external-link.jspa?url=https%3A%2F%2Fadobecustomersuccess.adobeconnect.com%2Fp8gt31drhs3e%2F%3FOWASP_CSRFTOKEN%3D4bd6cac5d0806167ee0a5449ba93d6300548d09c922bcb751c38973897a5703a)