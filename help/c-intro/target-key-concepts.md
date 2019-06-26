---
description: 能幫助您瞭解 Adobe Target 特色與功能之重要概念的相關資訊。
keywords: 概覽和參考資料;act
seo-description: 能幫助您瞭解 Adobe Target 特色與功能之重要概念的相關資訊。
seo-title: Target 重要概念
solution: Target
subtopic: 快速入門
title: Target 重要概念
topic: Standard
uuid: c62ac156-b4cf-494c-979f-33f889abd118
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Target 重要概念{#target-key-concepts}

能幫助您瞭解 Adobe Target 特色與功能之重要概念的相關資訊。

## 活動和測試 {#section_BEA0A0C51A8847579B566060206DE7E8}

活動會決定網站訪客可能遇到的體驗。

例如，您可以設計一個活動來測試兩個不同的登陸頁面，其中一個強調夏季女鞋的相關資訊，另一個以一般夏季服飾為主。此活動會決定條件來控制各個登陸頁面何時出現，也會決定量度來判斷哪個頁面較成功。此活動設定在滿足特定條件時 (例如在特定日期之間) 開始或結束，或在核准活動後開始，並於停用時結束。

設計活動時，您應該謹慎規劃。決定活動何時開始及持續時間。然後，列出您的選件並分別將目標對象指定至每個選件。

Target 包含數種活動類型。下表提供每種活動類型的概覽，以及可協助您深入瞭解的連結。為協助您更完善地選擇適用於您的用途的最佳活動類型，我們也建立了 [Adobe Target 活動指南](/help/c-activities/target-activities-guide.md)。

| 活動類型 | 說明 |
|--- |--- |
| [A/B 測試](/help/c-activities/t-test-ab/test-ab.md) | A/B 測試會比較兩個或更多版本的網站內容，以查看哪個版本在預先指定的測試持續時間最能改善您的轉換。<br>**注意:** 您現在可以[在 A/B 測試活動中包含建議](/help/c-recommendations/recommendations-as-an-offer.md)。若要使用此功能，您必須具備 [Target Premium 授權](/help/c-intro/intro.md#premium)。 |
| [自動分配](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | 自動分配會從兩個或多個體驗中識別獲勝者，並自動重新分配更多流量給獲勝者以增加轉換，同時測試會繼續執行和學習。<br>**注意:** 您現在可以[在自動分配活動中包含建議](/help/c-recommendations/recommendations-as-an-offer.md)。若要使用此功能，您必須具備 [Target Premium 授權](/help/c-intro/intro.md#premium)。 |
| [自動鎖定目標](/help/c-activities/auto-target-to-optimize.md)<br>![Target Premium](/help/assets/premium.png) | 自動鎖定目標使用進階機器學習來識別多個高效能之市場行銷人員定義的體驗，並根據訪客的個別客戶設定檔與具有類似設定檔之先前訪客的行為，提供每位訪客量身打造的最佳體驗，以便個人化內容並促進轉換。<br>**注意:** 您現在可以[在自動鎖定目標活動中包含建議](/help/c-recommendations/recommendations-as-an-offer.md)。若要使用此功能，您必須具備 [Target Premium 授權](/help/c-intro/intro.md#premium)。 |
| [使用 Analytics 資料](/help/c-activities/t-test-ab/t-test-create-ab/create-a4t.md) (A4T) | 您可以將活動設為使用 [!DNL Adobe Analytics] 作為報表來源。此活動類型需要您將 [!DNL Adobe Experience Cloud] 帳戶與 [!DNL Analytics] 和 [!DNL Target] 連結在一起。 |
| [多變數測試](/help/c-activities/c-multivariate-testing/multivariate-testing.md) | 多變數測試 (MVT) 會比較頁面上元素中選件的組合，以判斷哪個組合對特定對象執行時效果最佳，並識別哪個元素最能影響活動的成功。 |
| [體驗鎖定目標](/help/c-activities/t-experience-target/experience-target.md) | 體驗鎖定目標 (XT) 會根據一組市場行銷人員定義的規則和條件為特定對象提供內容。<br>**注意:** 您現在可以[在體驗鎖定目標活動中包含建議](/help/c-recommendations/recommendations-as-an-offer.md)。若要使用此功能，您必須具備 [Target Premium 授權](/help/c-intro/intro.md#premium)。 |
| [自動個人化](/help/c-activities/t-automated-personalization/automated-personalization.md)<br>![Target Premium](/help/assets/premium.png) | 自動個人化 (AP) 結合選件或訊息，並使用進階機器學習來根據訪客的個別客戶設定檔比對每位訪客的不同變數，以便個人化內容並促進轉換。 |
| [Recommendations](/help/c-recommendations/recommendations.md)<br>![Target Premium](/help/assets/premium.png) | 建議會根據網站使用者在網站上的活動，決定如何向使用者建議產品。<br>例如，您可能鼓勵買背包的人考慮買登山鞋和登山杖。您可以利用「購買了此項目、也購買了其他項目的使用者」演算法建立建議，以顯示通常一起購買的商品。或者，您可以鼓勵訪客多花一些時間在您的媒體網站上，並利用「瀏覽過此項目、也瀏覽了其他項目的使用者」演算法，根據他們正在看的影片來建議類似的影片。<br>**附註:** 您現在可以在 A/B 測試 (包括自動分配和自動鎖定目標) 與體驗鎖定目標 (XT) 活動中加入建議。請參閱[以選件方式使用 Recommendations](/help/c-recommendations/recommendations-as-an-offer.md)。 |

## 位置 {#section_F18FBF1ED23340ED9F39C51971A4E874}

首先，位置為網站上的頁面。它也可能是指行動應用程式中的位置、一封電子郵件或是您執行最佳化的任何其他位置。

位置對活動和體驗很重要。您決定任何位置是否可執行下列其中一項或兩項動作，或都不可執行:

* 為訪客顯示並切換內容。
* 記錄訪客行為。

在 [!DNL Target Standard] 中，位置可以是頁面上的任何元素，前提是您要追蹤的每一個頁面的 [!DNL Target] 區段中，都必須包含一行用於啟用 `<head>` 的程式碼。這行程式碼會呼叫必要的 JavaScript 程式庫，以收集資訊並將已鎖定的目標體驗傳送給訪客。

請參閱[at. js的優點，](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#benefits) 以瞭解有關位置實作與 [!DNL Target Standard] mbox實作之間差異的詳細資訊 [!DNL Target Classic]。

位置結合對象，可提供幾乎無窮盡的選項，以鎖定客戶提供資訊。例如，假設訪客以前從來沒到過網站，則您可以向新客戶顯示優惠券。同樣地，可變更頁面來顯示更適合回訪客戶的選件。

您還可以利用位置來追蹤訪客在您網站中的行進情形，或追蹤訪客是否已完成特定的成功量度，例如將項目新增至購物車，或是完成購物。

## 體驗和頁面設計 {#section_B806FB752EC1470784755C1EB3D4AC70}

體驗 (有時又叫做方式) 可定義在您頁面上顯示的內容以及其他頁面元素，例如連結。

體驗會決定符合特定鎖定條件時，特定位置會顯示哪個選件。例如，當再度訪問旳訪客造訪您的網站時，體驗會決定在頁面頂端顯示兩天運送期的選件。當首次造訪的訪客檢視頁面時，體驗也會決定在相同位置顯示 10% 折扣。

體驗由選件、影像資產或其他 HTML 元素 (例如連結) 組成，這些元素出現在頁面上，有助於將訪客推向您希望的結果。[!DNL Target] 會結合位置、選件及體驗，以決定在特定測試期間顯示在您網站上的內容。

體驗也可能是不同的頁面設計。例如，一個體驗可能有一組連結橫跨在頁面頂端，而另一個體驗有不同的連結，或相同的連結但以不同順序排列。您可以測試一個影像是否比另一個影像提供更大的提升度，或一個廣告靠近頁面頂端或放在不同位置是否更可能被點閱。

[!DNL Target] 會遍及您所有數位接觸點的每一位訪客來最佳化體驗，以及測試不同體驗來判斷何者最成功。只要仔細規劃體驗的目標鎖定，即可確保網站訪客在頁面上的正確位置看見最有關的選件，提高造訪成功的機會。

## 選件 {#section_973D4CC4CEB44711BBB9A21BF74B89E9}

選件是促銷活動或活動期間在您的網頁上顯示的內容。

當您測試網頁時，可利用您位置中的不同選件來測量每一個體驗是否成功。

選件可以包含不同類型的內容，包括:

* 影像
* 文字
* HTML
* 連結
* 按鈕

例如，網頁可能顯示兩個選件其中一個，視訪客以前是否來過您的網站而定。

一個*體驗*決定當符合特殊條件時所顯示的內容。

## 受眾 {#section_3F32DA46BDF947878DD79DBB97040D01}

將您鎖定的內容最佳化至符合特定條件的活動加入者。

對象定義活動的目標，在任何可鎖定目標之處皆可使用。

[!DNL Target] 對象是一組已定義的訪客條件。選件可以鎖定特定對象 (或區段) 作為目標。只有屬於該對象的訪客，才能看到以他們為目標的體驗。

例如，您可以將活動的目標，鎖定在由使用特定瀏覽器或作業系統的訪客所組成的對象。

或者，您可以將活動鎖定在來自相同地區的訪客，或從特定搜尋引擎存取您網頁的人。

對象可儲存供多個活動重複使用，也可以針對特定行銷活動而建立。

| 對象類型 | 說明 |
|--- |--- |
| 可重複使用的對象 | 可重複使用的對象可供任何測試選取。如果變更其中一個對象，則所有用到此對象的活動中皆會變更此對象。 |
| 自訂群體 | 自訂區段 (也稱為行銷活動專用區段) 專供 Target Classic 中的行銷活動使用。它們是某個促銷活動的一部分，不可在其他促銷活動中重複使用。 |
| 共用對象 | [!DNL Adobe Experience Cloud] 解決方案之間可以共用對象。相關範例請參閱 [Experience Cloud 對象](https://marketing.adobe.com/resources/help/en_US/mcloud/audience_library.html)。 |

如需瞭解訪客設定檔如何追蹤網站訪客的相關資訊，請參閱[訪客設定檔](../c-target/c-visitor-profile/visitor-profile.md#concept_5E53D1A6DF224D7BAE76F4AE390B9DA1)。

## 訓練影片:

以下影片含有本文章探討之概念的詳細資訊。

### 活動類型 (9:03)

此影片說明 [!DNL Target Standard/Premium] 中的可用活動類型。

* 說明 [!DNL Adobe Target] 中包括的活動類型
* 選取達成目標的適當活動類型
* 說明適用所有活動類型的三個步驟引導工作流程

>[!VIDEO](https://video.tv.adobe.com/v/17386?captions=chi_hant)

### 在 Adobe Target 中使用對象 (6:21)

此影片說明如何在 [!DNL Target Standard/Premium] 中使用對象。

* 說明詞語「對象」
* 說明將對象用於最佳化的兩個方式
* 在對象清單中尋找對象
* 將活動鎖定至對象
* 對活動中的被動報表使用對象

>[!VIDEO](https://video.tv.adobe.com/v/17398?captions=chi_hant)