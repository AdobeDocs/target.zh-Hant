---
keywords: welcome kit;target welcome kit;intro;introduction;getting started
description: Adobe Target歡迎套件——第2章- Target總覽
title: Adobe Target歡迎套件——第2章- Target總覽
feature: Overview
translation-type: tm+mt
source-git-commit: cf47b7f3625bb1c3430b9fba00c573f489efc448
workflow-type: tm+mt
source-wordcount: '2504'
ht-degree: 17%

---


# 第二章：Adobe Target總覽

在開始使用[!DNL Adobe Target]之前，請先從高階角度概述解決方案。 在本章中，請瞭解解決方案的主要功能、您可使用的品牌觸點、實作選項、重要的使用者介面功能和工作流程、治理功能，以及它在整體[!DNL Adobe Experience Cloud]中的角色。 除非注明[!DNL Adobe Target Premium]功能，否則本章中介紹的項目可同時用於[!DNL Adobe Target Premium]和[!DNL Adobe Target Standard]。 如需詳細資訊，請參閱[ Target簡介](/help/c-intro/intro.md)。

## 功能與活動

測試和個人化是[!DNL Target]提供的兩種廣泛功能類型，在[!DNL Target]中建立「活動」時，您可使用這兩種功能。 您可能會看到「測試」一詞與「最佳化」可互換使用，而「個人化」與「定位」可互換使用。

在測試活動中，您會比較數位體驗的一種變化與一種或多種其他變化，以發現其中一種變化會導致大多數訪客採取所需動作。 [!DNL Target] 提供下列測試功能：A/B測試、多變數測試(MVT)和自動配置。

透過個人化活動，您可以針對特定訪客群組或每位訪客提供量身打造的數位體驗。 [!DNL Target] 提供下列個人化功能：體驗定位、自動定位、自動個人化和建議。

如需更深入瞭解使用每個功能的時機和方式，請參閱[ Target活動類型](/help/c-activities/target-activities-guide.md)。

| 活動類型 | 詳細資料 |
| --- | --- |
| A/B 測試 | 比較您網站或其他數位客戶觸點上的兩種或兩種以上體驗或優惠的變化，以瞭解哪些變化在預先指定的測試期間對關鍵業務衡量標準有最大改善。 A/B測試非常適合進行大型變更，例如新的網頁版面配置、不同的網站導覽方式，或對複製、影像和行動要求按鈕等數位體驗的個別元素進行不同的處理方式。 [了解詳情](/help/c-activities/t-test-ab/test-ab.md)。 |
| 自動分配 | 識別兩個或更多體驗中效能最佳的體驗，並自動重新分配更多流量給成功者，以在測試持續執行和學習時提高轉化率。 使用由[!DNL Adobe Sensei]提供支援的人工智慧。 [了解詳情](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)。 |
| Auto-Target<br>(Premium) | 運用[!DNL Target]中的Adobe Sensei AI，根據個別客戶個人檔案以及先前具有類似個人檔案的訪客的行為，判斷並提供每位訪客的最佳體驗。 Auto-Target可讓您大規模個人化。 [了解詳情](/help/c-activities/auto-target/auto-target-to-optimize.md)。 |
| Automated Personalization<br>(Premium) | 使用[!DNL Adobe Sensei]支援的進階機器學習演算法和自動化功能，檢視選件中影像、複製和其他元素的不同組合，並根據最佳達成商業目標（例如提高每位訪客的轉換率或收入）的結果，為每位訪客提供最佳組合。 [了解詳情](/help/c-activities/t-automated-personalization/automated-personalization.md)。 |
| 體驗鎖定目標 (XT) | 根據一組使用者定義的規則和准則，將內容傳送給特定的觀眾。 **[!UICONTROL 當您了]** 解受眾是有價值的，並且對體驗產生共鳴有良好的感覺時，Experience Targeting對於將特定體驗或內容定位給特定受眾非常有用。[了解詳情](/help/c-activities/t-experience-target/experience-target.md)。 |
| 多變數測試 (MVT) | 比較頁面上各種元素或數位體驗的可能組合——例如3種不同的背景影像、2種不同的復本和2種不同的按鈕顏色。 MVT會決定哪些組合對特定對象的效能最佳，以及哪些元素對結果的影響最大。 [了解詳情](/help/c-activities/c-multivariate-testing/multivariate-testing.md)。 |
| Recommendations<br>(Premium) | 使用Adobe Sensei AI，根據客戶先前的活動和其他客戶的活動，自動建議可能吸引客戶的產品或內容。 [了解詳情](/help/c-recommendations/recommendations.md)。 |

## 頻道

您可以使用[!DNL Target]來測試和個人化幾乎任何地方的數位體驗——例如您的網站、行動網站和行動應用程式等傳統數位觸點，也可以在資訊站、電子郵件、IoT裝置、遊戲主機，甚至Alexa和Cortana等語音助理上。 許多公司都開始在其網站上使用[!DNL Target]。 不過，最近的研究顯示，有更多人從行動裝置瀏覽品牌。 最佳化您的行動通道現在至關重要。 最理想的情況是，您可以跨所有觸點連結訪客的體驗，以提供順暢、一致的體驗。

| 管道 | 詳細資料 |
| --- | --- |
| 網站 | [!DNL Target] 可用於在多頁、單頁應用程式(SPA)和行動網站的頁面上執行A/B測試、多變數測試、體驗定位、自動分配、自動定位、自動個人化和建議活動，以改善訪客和客戶參與度、增加轉換率並增加收入。 |
| 行動網路 | [!DNL Target] 可用來執行您在行動網站頁面上網站上執行的所有相同活動類型，以類似方式改善訪客和客戶參與度、提高轉化率，並增加收入。 |
| 行動應用程式 | [!DNL Target] 可用來根據使用者行為和行動內容來測試和個人化行動應用程式體驗。[!DNL Target] 可讓您透過反覆測試、體驗鎖定和人工智慧支援的個人化，提供互動，以吸引和轉化客戶。若要在行動應用程式上使用[!DNL Target]，您必須使用Adobe Mobile Services SDK。 |
| 物聯網／隨處 | [!DNL Target] 提供伺服器端實作，讓您可以在傳統網站、行動網站和行動應用程式的活動中，在電子郵件和沒有瀏覽器或不使用JavaScript程式碼的觸點上，使用相同的測試和個人化功能。例如，您可以測試並個人化資訊站、機上盒、遊戲主機、語音助理和其他非傳統觸點。 |

## 實作

許多人可能會想使用[!DNL Target]來測試和個人化您的許多不同數位觸點，包括傳統的網頁和行動觸點，也包括缺乏瀏覽器或不使用JavaScript程式碼的觸點。 在某些情況下，內部或外部政策要求您擁有額外的控制與安全性。 您可能還有需要在後端伺服器上執行的程式，以利效能。 為了滿足這種廣泛的用途，我們提供您以不同方式實施[!DNL Target]的能力：用戶端、伺服器端或兩者的組合。

| 實施類型 | 詳細資料 |
| --- | --- |
| 用戶端 | 透過此[!DNL Target]實作，[!DNL Target]會將與活動相關的體驗直接傳送至用戶端瀏覽器。 瀏覽器會決定要顯示哪個體驗，然後顯示其內容。透過用戶端，您可以使用WYSIWYG編輯器、**[!UICONTROL Visual Experience Composer]**(VEC)或非視覺化介面（**[!UICONTROL 表單型Experience Composer]**）來建立您的測試和個人化體驗。 [了解詳情](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)。 |
| 伺服器端 | 在此類型的[!DNL Target]實作中，用戶端裝置會透過您的伺服器要求體驗，您的伺服器會將該要求傳送至[!DNL Target],[!DNL Target]會傳回回應給您的伺服器，而您的伺服器會決定要傳送哪些體驗給用戶端裝置，以供其呈現。 體驗不需要顯示在瀏覽器中；體驗可以透過語音助理或透過某些其他非視覺體驗或非瀏覽器型裝置，顯示在電子郵件或資訊站中。由於伺服器位於用戶端與 [!DNL Target] 之間，如果您需要更多控制和安全性，或有要在伺服器上執行的複雜後端程序，這種類型的實施也是非常理想的選擇。[了解詳情](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md)。 |
| 混合實作 | 在此實作中，您可以選擇最適合特定使用案例的實作方法。 例如，您可能會使用用戶端實作來A/B測試首頁英雄橫幅中的選件，但也會使用伺服器端實作來判斷要在用戶端瀏覽器上顯示的內部搜尋結果、在智慧型汽車儀表板上顯示的體驗，或透過語音助手傳送的語音回應。 |

## 活動元素

在[!DNL Target]中，您可以建立個人化活動、最佳化活動，或可最佳化個人化方法的活動。 每個活動都包含關鍵元素——您正在測試或個人化的體驗或優惠、您要提供體驗的受眾或個人、您測量活動影響的量度，以及以視覺化方式顯示影響的報表。

| 元素類型 | 詳細資料 |
| --- | --- |
| 體驗 | 選件、影像、文字、按鈕、影片或將這些不同元素加以組合，放在頁面、整個網頁或一組頁面上，可能會形成購買漏斗或一些其他的頁面邏輯順序。也可以是語音助理的回應、客戶服務指令碼，或甚至是飲料機的個人化口味。您可以在 [!DNL Target] 活動中測試或個人化體驗。[了解詳情](/help/c-experiences/experiences.md)。 |
| 選件 | 可能包含影像、文字、HTML、連結、視訊、動作呼叫按鈕、語音助理回應或任何其他類型內容的內容區塊。 優惠可能是折扣、免運費等。 選件可顯示在網頁上，但也可能在任何客戶觸點（例如語音助理或遊戲控制台）上體驗。 當您測試選件時，會比較其他選件或沒有選件來評估其成功程度。 [了解詳情](/help/c-experiences/c-manage-content/manage-content.md)。 |
| 對象 | 具有相同特性的一組人員，例如新訪客、回頭客或來自中西部的回頭客。受眾功能可讓您將不同的內容和體驗鎖定在特定對象，利用在正確時間向正確的人員顯示正確的訊息來最佳化您的數位行銷。如果訪客被識別為目標對象的一部分，[!DNL Target]會根據建立活動期間定義的准則，決定要顯示哪些體驗。 [了解詳情](/help/c-target/target.md)。 |
| 成功量度 | 關鍵業務度量，可讓您判斷在[!DNL Target]活動中特定體驗或選件是否成功。 例如，您可以判斷新選件是否會提高每位訪客帶來的收入，或將項目新增至購物車的機會。成功量度非常適合用於探索關於註冊、訂購或購買漏斗的問題，但也適合探索關於訪客或客戶參與度的問題。[了解詳情](/help/c-activities/r-success-metrics/success-metrics.md)。 |
| 報表 | 有關您活動的進度和結果的資訊，這些資訊可協助您根據資料做出決策。 報表資料可協助您決定要在何時終止測試、顯示哪個選件的體驗是獲勝者，以及提供判斷後續動作所需的前瞻分析或經驗談。[了解詳情](/help/c-reports/reports.md)。 |

## 活動建立工具

[!DNL Target] 提供三種主要方式來設定測試和個人化活動： [!UICONTROL Visual Experience Composer] (VEC)、 [!UICONTROL Form-based Experience Composer]，以及 [!UICONTROL Single Page Application(SPA)Visual Experience Composer]。兩者都會透過三個步驟來引導您完成活動設定程式：定義體驗、選取或定義對象，以及選取您用來測量活動結果的主要和次要成功度量。

| 工具 | 詳細資料 |
| --- | --- |
| 可視化體驗撰寫器 (VEC) | WYSIWYG使用者介面，可讓您輕鬆建立並測試網站情境中的個人化體驗與優惠。 您可以拖放、交換及修改網頁（或選件）或行動網頁的版面配置和內容，以建立[!DNL Target]活動的體驗和選件。 [了解詳情](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md)。 |
| [!UICONTROL 表單式體驗撰寫器] | 非視覺化體驗和選件建立介面，當Visual Experience Composer無法使用或實際使用時，此介面可用於建立用於A/B測試、體驗定位、自動個人化和建議活動的體驗。 例如，您可以使用表單式撰寫器，建立可在電子郵件、資訊站和語音助理中傳送的體驗和選件。[了解詳情](/help/c-experiences/form-experience-composer.md)。 |
| [!UICONTROL 單一頁面應用程式 (SPA) 可視化體驗撰寫器] | 適用於 SPA 的 VEC 能讓行銷人員在 SPA 上，自己動手建立測試並個人化內容，無需持續開發的相依性。VEC 可用來在熱門架構 (React 和 Angular) 上建立 A/B 測試和體驗鎖定目標 (XT) 活動。[了解詳情](/help/c-experiences/spa-visual-experience-composer.md)。 |

## 治理與控制

為了向適當的人員提供適當的角色和對[!DNL Target]的相關訪問級別和權限，我們有一個管理控制台。 對於[!UICONTROL Target Premium]使用者，我們提供更詳細的管理與控制
具有[!UICONTROL 企業權限]。

| 工具 | 詳細資料 |
| --- | --- |
| [!UICONTROL Adobe Admin Console for Enterprise] | 將使用者新增至Adobe Target，並從Adobe Admin Console指派權限。 [了解詳情](/help/administrating-target/c-user-management/c-user-management/user-management.md)。 |
| [!UICONTROL 企業]權限<br>(Premium) | 正式管理企業內部使用者存取[!DNL Target]的方式。 將使用者新增至[!DNL Target]、根據其角色指派權限，並根據不同的部門、全域位置、頻道和其他邏輯群組為團隊建立工作區。 您可以為用戶分配觀察者、編輯者、發佈者或批准者的角色。 [了解詳情](/help/administrating-target/c-user-management/property-channel/property-channel.md)。 |

## 整合

[!DNL Target] 可與許多第一方、第二方和第三方系統整合。這些
整合對於讓您存取這些系統中的訪客和客戶資料非常有價值，以便用於建立受眾以進行測試和個人化。 作為[!DNL Adobe Experience Cloud]的一部分，[!DNL Target]與[!DNL Experience Cloud]解決方案及其核心服務緊密整合。

| 整合 | 詳細資料 |
| --- | --- |
| Adobe Experience Cloud | [!DNL Target] 與其他解決方案一起提供 [!DNL Adobe Experience Cloud] 了嵌入式功能，可大規模個人化體驗。運用[!DNL Target]的強大功能以及[Adobe Analytics](/help/c-integrating-target-with-mac/a4t/a4t.md)、[Experience Cloud Audiences](/help/c-integrating-target-with-mac/mmp.md)、[Adobe Campaign](/help/c-integrating-target-with-mac/campaign-and-target.md)、[Adobe Audience Manager](/help/c-integrating-target-with-mac/audience-manager-target-integration.md)(AAM)和[ Adobe Experience Manager](/help/c-experiences/c-manage-content/aem-experience-fragments.md)(AEM)。 |
| Target API(Premium) | [!UICONTROL Target] 提供超過40個API，您可使用這些API將Adobe Target與第一方、第二方和第三方系統整合。[了解詳情](/help/api/api-overview.md)。 |

## 請記住

在我們進入下一章之前，請先考慮以下想法：「開發您的測試和個人化概念。」

### 最佳化的最佳範例

* **好策略**:我們的目標和假設是什麼？它們是否一致？ 例如，我們想增加貸款申請書的提交量，因此我們假設減少申請表中的欄位數量將起到這一作用。
* **嚴謹** 的方法我們是否開始在正確的地方進行測試？例如，您需要具備足夠流量且影響重要量度的位置    對企業有利。
* **正確** 的設定我們的活動是為了達到目標嗎？例如，如果我們嘗試增加貸款申請提交，我們應針對對貸款感興趣的人，並測量「提交」按鈕的點擊。
* **深入分析**:測試活動是否運行到完成？結果如何？ 執行您的活動，直到達到95%到99%的統計信賴。 記錄您認為成功體驗成功的原因，並將學習套用至其他地方。
* **反覆測試**:我們是否在學習以往活動的基礎上再接再厲？如果您發現成功策略，請嘗試改進或進行可搭配使用的變更，以進一步改善您的成功度量。

### 意見可能會對您的結果產生負面影響

* 對您的效能有負面影響的意見。 Hight Pay Person』s Oppion(HIPPO)，態度，偏見。 例如，CEO想要縮小搜尋方塊的大小，讓每個頁面有更多空間。 我們應該進行測試，以確保不會減少搜尋次數。
* 你是在根據意見行事嗎？ 我不喜歡測試的外觀。 客戶根本不喜歡這種體驗。 雖然直覺很有用，但A/B測試已經一次又一次地證明，它並不總是特別出色。
* 還是說，你有最佳化的心態？ 我很高興看到哪一種體驗能贏。 我們有足夠的選項可進行測試嗎？

### 假設也可能對結果產生負面影響

* 對您的效能有負面影響的假設。 羊群心理（我們的競爭對手就是這樣做的）。 例如，我們所有的競爭者都使用帶有旋轉影像的英雄橫幅，因此我們也應該使用。
* 假設我們知道為什麼有些東西有效或無效。 假設我們不需要測試什麼。 例如，我們一律會依預設的最高到最低價格來列出酒店客房。
* 你是在假設下行事嗎？ 我們不需要測試，我們已檢查分析。 （是的，但是故事的內容可能比分析揭示的更多。）
* 還是說，你有最佳化的心態？ 我們測試一切。