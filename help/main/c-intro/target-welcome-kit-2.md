---
keywords: 歡迎套件;target 歡迎套件;介紹;簡介;開始
description: 以高層級方式檢視 Adobe Target。了解可用的活動、頻道、實施、整合等。
title: 在哪裡可以找到 Target 的高層級簡介？
feature: Overview
exl-id: 19238d4c-b7e1-418d-96e5-c46a3769f7bf
source-git-commit: fe1e97710e7692ba7724103853ed7438c3f361b1
workflow-type: tm+mt
source-wordcount: '2524'
ht-degree: 84%

---

# 第 2 章：Adobe [!DNL Target] 總覽

在開始使用 [!DNL Adobe Target] 之前，先了解解決方案高層級概覽可能有所助益。在本章中，可以瞭解解決方案的主要功能、可使用解決方案的品牌拉觸點、實施選項、重要的使用者介面功能和工作流程、治理功能，及其在整體中的角色 [!DNL Adobe Experience Cloud]. 除非註明為 [!DNL Adobe Target Premium] 功能，否則本章中說明的項目可同時用於 [!DNL Adobe Target Premium] 和 [!DNL Adobe Target Standard]。 如需更多資訊，請參閱 [Target 簡介](/help/main/c-intro/intro.md)。

## 功能與活動

測試和個人化是兩種廣泛的功能型別， [!DNL Target] 優惠方案，以及您在中建立「活動」時可使用的專案 [!DNL Target]. 您可能會看到「測試」一詞與「最佳化」互換使用，而「個人化」與「目標定位」可互換使用。

在測試活動中，您會比較數位體驗的一種變化與一種或多種其他變化，以找出會導致大多數訪客採取所需動作的變化。 [!DNL Target] 提供下列測試功能：A/B測試、多變數測試 (MVT) 和自動分配。

透過個人化活動，您可以針對特定訪客群組或每位訪客提供量身打造的數位體驗。[!DNL Target]提供下列個人化功能：體驗鎖定、自動鎖定目標、Automated Personalization 和 Recommendations。

如需更深入地瞭解使用每個功能的時機和方式，請參閱 [Target 活動類型](/help/main/c-activities/target-activities-guide.md)。

| 活動類型 | 詳細資料 |
| --- | --- |
| A/B 測試 | 比較您網站或其他數位客戶接觸點上的兩種或更多種體驗或選件的變化，以瞭解哪些變化在預先指定的測試期間對關鍵業務衡量標準有最大改善。A/B測試非常適合進行大型變更，例如新的網頁頁面配置、不同的網站導覽方式，或對複製、影像和行動號召按鈕等數位體驗的個別元素進行截然不同的處理方式。[了解詳情](/help/main/c-activities/t-test-ab/test-ab.md)。 |
| 自動分配 | 從兩個或多個體驗中識別出效能最佳的體驗，並自動重新分配更多流量給成功者以增加轉換，同時測試會繼續執行和學習。使用由 [!DNL Adobe Sensei] 提供支援的人工智慧。[了解詳情](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)。 |
| 自動鎖定目標 <br>(Premium) | 運用 [!DNL Target] 中的 Adobe Sensei 人工智慧，根據個別客戶設定檔和先前具有類似設定檔的訪客行為，決定並提供每位訪客最佳體驗。 自動鎖定目標可讓您大規模個人化。[了解詳情](/help/main/c-activities/auto-target/auto-target-to-optimize.md)。 |
| Automated Personalization <br>(Premium) | 使用由 [!DNL Adobe Sensei] 支援的進階機器學習演算法和自動化功能，檢視選件中影像、複製和其他元素的不同組合，並根據能最好地達成商業目標者 (例如每位訪客的轉換或收入增加)，為每位訪客提供最佳組合。 [了解詳情](/help/main/c-activities/t-automated-personalization/automated-personalization.md)。 |
| 體驗鎖定 (XT) | 根據一組使用者定義的規則和標準，將內容傳送給特定的對象。 當您了解對象是有價值的，以及充分意識到哪些體驗會與之產生共鳴時，**[!UICONTROL 體驗鎖定]**&#x200B;對於鎖定特定體驗或內容並用於特定對象非常有用。[了解詳情](/help/main/c-activities/t-experience-target/experience-target.md)。 |
| 多變數測試 (MVT) | 比較頁面上或數位體驗中各種元素變化的可能組合——例如 3 種不同的背景影像、2 種不同複本和 2 種不同按鈕顏色。MVT 會決定哪些組合對特定對象具有最佳效能，以及哪些元素對結果的影響最大。[了解詳情](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)。 |
| Recommendations<br>(Premium) | 使用 Adobe Sensei 人工智慧，根據客戶先前的活動和其他客戶的活動，自動建議可能吸引客戶的產品或內容。[了解詳情](/help/main/c-recommendations/recommendations.md)。 |

## 頻道

您可以使用 [!DNL Target] 測試和個人化幾乎任何地點的數位體驗——例如您的網站、行動網站和行動應用程式等傳統數位接觸點，或是資訊站、電子郵件、IoT 裝置、遊戲主機，甚至 Alexa 和 Cortana 等語音助理這類的接觸點。許多公司都開始在其網站上使用 [!DNL Target]。 不過，最近的研究顯示，有更多人從行動裝置瀏覽品牌。 最佳化您的行動裝置頻道現在至關重要。在理想狀況下，您可以跨所有接觸點連結訪客體驗，以提供順暢、一致的體驗。

| 頻道 | 詳細資料 |
| --- | --- |
| 網站 | [!DNL Target] 可用於在多頁面、單次頁面應用程式 (SPA) 和行動網站的頁面上執行 A/B 測試、Multivariate Testing、體驗鎖定、自動分配、自動鎖定目標、Automated Personalization 和 Recommendations 活動，以改善訪客和客戶參與度、提高轉化率並增加收入。 |
| 行動網頁 | [!DNL Target] 可用來執行您在您的網站或行動網站頁面上執行的所有相同活動類型，以類似方式改善訪客和客戶參與度、提高轉化率，並增加收入。 |
| 行動應用程式 | [!DNL Target] 可用於根據使用者行為和行動內容來測試及個人化行動應用程式體驗。[!DNL Target] 可讓您透過反覆測試、體驗鎖定和人工智慧支援的個人化，來提供能提高參與度及轉化率的互動。若要在行動裝置上使用 [!DNL Target] 應用程式，您必須使用 Adobe Mobile Services SDK。 |
| 物聯網/隨處 | [!DNL Target] 提供伺服器端實施，讓您可以在傳統網站、行動網站和行動應用程式的活動中，在電子郵件中，以及沒有瀏覽器或不使用JavaScript程式碼的接觸點上，使用相同的測試和個人化功能。 例如，您可以測試並個人化資訊站、機上盒、遊戲主機、語音助理和其他非傳統接觸點。 |

## 實施

許多人可能會想使用 [!DNL Target] 在許多不同的數位接觸點上進行測試和個人化，包括傳統的網頁和行動接觸點，也包括缺乏瀏覽器或不使用JavaScript程式碼的接觸點。 在某些情況下，內部或外部政策要求您擁有額外的控制與安全性層級。您可能也會有基於效能原因而需要在後端伺服器上執行的程序。為了滿足這些廣泛的用途，我們提供您以不同方式實施 [!DNL Target] 的能力：用戶端、伺服器端或兩者的組合。

| 實施類型 | 詳細資料 |
| --- | --- |
| 用戶端 | 透過 [!DNL Target] 的實施，[!DNL Target] 會將與活動相關聯的體驗直接傳送至用戶端瀏覽器。瀏覽器會決定要顯示哪個體驗，然後顯示其內容。透過用戶端，您可以使用 WYSIWYG 編輯器、**[!UICONTROL Visual Experience Composer]** (VEC) 或非視覺化介面 **[!UICONTROL Form-based Experience Composer]**，來建立您的測試和個人化體驗。[瞭解更多](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/at-js/how-atjs-works.html){target=_blank}. |
| 伺服器端 | 在此類型的 [!DNL Target] 實施中，用戶端裝置會透過您的伺服器請求體驗，您的伺服器會將該請求傳送至 [!DNL Target]，[!DNL Target] 會將回應傳回至您的伺服器，而您的伺服器會決定要傳送哪個體驗至用戶端裝置，以供其呈現。該體驗不需要顯示在瀏覽器中；它可以透過語音助理或某些其他非視覺體驗或非瀏覽器型裝置，在電子郵件或資訊站中顯示。由於伺服器位於用戶端與 [!DNL Target] 之間，如果您需要更多控制和安全性，或有要在伺服器上執行的複雜後端程序，這種類型的實施也是非常理想的選擇。[瞭解更多](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/server-side-overview.html){target=_blank}. |
| 混合實施 | 在此實施中，您可以選擇最適合特定使用案例的實施方法。例如，您可能會使用用戶端實施來 A/B 測試首頁上主頁橫幅中的一個選件，但也會使用伺服器端實施來決定要在用戶端瀏覽器上顯示的內部搜尋結果、要在智慧型儀表板上顯示的體驗，或要透過語音助手傳送的語音回應。 |

## 活動元素

在 [!DNL Target] 中，您可以建立個人化活動、最佳化活動，或可使個人化方法最佳化的活動。 每個活動都有關鍵元素 — 您正在測試或個人化的體驗或選件、您要提供體驗的對象或個人、您測量活動影響的量度，以及以視覺顯示該影響的報告。

| 元素類型 | 詳細資料 |
| --- | --- |
| 體驗 | 選件、影像、文字、按鈕、影片或將這些不同元素加以組合，放在頁面、整個網頁或一組頁面上，可能會形成購買漏斗或一些其他的頁面邏輯順序。也可以是語音助理的回應、客戶服務指令碼，或甚至是飲料機的個人化口味。您可以在 [!DNL Target] 活動中測試或個人化體驗。[了解詳情](/help/main/c-experiences/experiences.md)。 |
| 選件 | 可能包含影像、文字、HTML、連結、視訊、行動號召按鈕、語音助理回應或任何其他類型內容的內容區塊。 一項選件可能是折扣、免運費等。選件可顯示在網頁上，但也可能在任何客戶接觸點 (例如語音助理或遊戲主機) 上體驗。 當測試選件時，您將它與其他選件或無選件進行比較以評估其成功程度。[了解詳情](/help/main/c-experiences/c-manage-content/manage-content.md)。 |
| 對象 | 具有相同特性的一組人員，例如新訪客、回頭客或來自中西部的回頭客。對象功能可讓您將不同的內容和體驗鎖定在特定對象，利用在正確時間向正確的人員顯示正確的訊息來最佳化您的數位行銷。如果驗明訪客屬於目標對象，[!DNL Target] 會根據活動建立期間所定義的條件，決定要顯示的體驗。[了解詳情](/help/main/c-target/target.md)。 |
| 成功量度 | 可讓您決定在 [!DNL Target] 活動中特定體驗或選件成功程度的關鍵業務測量。例如，您可以判斷新選件是否會提高每位訪客帶來的收入，或將某個項目新增至購物車的機會。成功量度非常適合用於探索關於註冊、訂購或購買漏斗的問題，但也適合探索關於訪客或客戶參與度的問題。[了解詳情](/help/main/c-activities/r-success-metrics/success-metrics.md)。 |
| 報告 | 有關您活動的進度和結果的資訊，這些資訊可協助您根據資料做出決策。 報告資料可協助您決定要在何時終止測試、顯示哪個選件體驗是成功者，以及提供您決定後續動作所需的前瞻分析或經驗談。[了解詳情](/help/main/c-reports/reports.md)。 |

## 活動建立工具

[!DNL Target] 提供三種主要方式來設定測試和個人化活動：[!UICONTROL Visual Experience Composer] (VEC)、[!UICONTROL Form-based Experience Composer]，以及 [!UICONTROL Single Page Application (SPA)Visual Experience Composer]。兩者都會透過三個步驟來引導您完成活動設定程式：定義體驗、選取或定義對象，以及選取您用來測量活動結果的主要和次要成功量度。

| 工具 | 詳細資料 |
| --- | --- |
| Visual Experience Composer (VEC) | WYSIWYG 使用者介面，可讓您輕鬆建立並測試網站內容中的個人化體驗與選件。您可以拖放、交換及修改網頁 (或選件) 或行動網頁的版面和內容，以建立 [!DNL Target] 活動的體驗和選件。 [了解詳情](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md)。 |
| [!UICONTROL Form-based Experience Composer] | 非視覺化體驗和選件建立介面，適合在視覺化體驗撰寫器無法使用或不實用的情況下，用於建立可供A/B測試、體驗鎖定目標、Automated Personalization和Recommendations活動使用的體驗。 例如，您可以使用表單式撰寫器，建立可在電子郵件、資訊站和語音助理中傳送的體驗和選件。[了解詳情](/help/main/c-experiences/form-experience-composer.md)。 |
| [!UICONTROL Single Page Application (SPA) Visual Experience Composer] | 適用於 SPA 的 VEC，能讓行銷人員在 SPA 上自己動手建立測試並個人化內容，無需持續開發的相依性。VEC 可用來在熱門架構 (例如 React 和 Angular) 上建立 A/B 測試和體驗鎖定 (XT) 活動。[了解詳情](/help/main/c-experiences/spa-visual-experience-composer.md)。 |

## 治理與控制

為了向適當的人員提供適當的角色和對 [!DNL Target] 的相關訪問級別和權限，我們有一個管理控制台。對於 [!UICONTROL Target Premium] 使用者，我們以 [!UICONTROL Enterprise Permissions] 提供更詳細的管理與控制。

| 工具 | 詳細資料 |
| --- | --- |
| [!UICONTROL Adobe Admin Console for Enterprise] | 新增使用者至 Adobe Target，並從 Adobe Admin Console 指派權限。[了解詳情](/help/main/administrating-target/c-user-management/c-user-management/user-management.md)。 |
| [!UICONTROL 企業權限]<br> (Premium) | 一種正式管理企業內部使用者存取 [!DNL Target] 權限的方法。根據不同的部門、全域位置、管道和其他邏輯群組，將使用者新增至 [!DNL Target]、根據其角色指派權限，以及建立團隊的工作區。您可以將觀察者、編輯者、發佈者或核准者的角色指派給使用者。[了解詳情](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)。 |

## 整合

[!DNL Target] 可與許多第一方、第二方和第三方系統整合。這些整合對於讓您存取這些系統中的訪客和客戶資料非常有價值，以便用於建立對象以進行測試和個人化。作為 [!DNL Adobe Experience Cloud] 的一部分，[!DNL Target] 與 [!DNL Experience Cloud] 解決方案及其核心服務緊密整合。

| 整合 | 詳細資料 |
| --- | --- |
| Adobe Experience Cloud | [!DNL Target] 與其他 [!DNL Adobe Experience Cloud] 解決方案一起提供嵌入式功能，可大規模個人化體驗。將 [!DNL Target] 的強大功能與 [Adobe Analytics](/help/main/c-integrating-target-with-mac/a4t/a4t.md)、[Experience Cloud Audiences](/help/main/c-integrating-target-with-mac/mmp.md)、[Adobe Campaign](/help/main/c-integrating-target-with-mac/campaign-and-target.md)、[Adobe Audience Manager](/help/main/c-integrating-target-with-mac/audience-manager-target-integration.md) (AAM) 和 [Adobe Experience Manager](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md) (AEM) 一起運用。 |
| Target APIs (Premium) | [!UICONTROL Target] 提供超過 40 種 API，您可用來將 Adobe Target 與第一方、第二方和第三方系統整合。[了解詳情](/help/main/api/api-overview.md)。 |

## 請記住

在前往接下來的章節之前，請先考慮：「開發您的測試和個人化概念。」

### 最佳化的最佳作法

* **好策略**：我們的目標和假設是什麼？它們是否一致？ 例如，我們想增加貸款申請書的提交量，因此我們假設減少申請表中的欄位數量可以做到這一點。
* **嚴謹的方法**：我們是否從正確的地方開始進行測試？例如，您需要有足夠流量且對企業重要量度能造成影響的地點。
* **正確的設定**：我們的活動設定能達成目標嗎？例如，如果我們嘗試增加貸款申請提交量，我們應鎖定對貸款感興趣的人，並測量「提交」按鈕的點選量。
* **深入分析**：測試活動是否運行到完成？結果如何？執行您的活動，直到達到 95% 到 99% 之間的統計信賴度。記錄您認為成功體驗獲得成功的原因，並將此知識套用至其他地方。
* **反覆測試**：我們是否在從以往活動學到的知識基礎上再接再厲？如果您發現成功策略，請嘗試改進或進行可搭配使用的變更，以進一步改善成功量度。

### 意見可能會對您的結果產生負面影響

* 可能會對您的有效性產生負面影響的意見。最高薪人士的意見(HIPPO)、態度、偏見。 例如，CEO 想要縮小搜尋方塊的大小，以便讓每個頁面有更多空間。我們應該進行測試以確保這不會減少搜尋次數。
* 你是根據意見行事的嗎？我不喜歡測試的外觀。 客戶根本不喜歡這種體驗。 雖然直覺很有用，但A/B測試已經一再證明，直覺並不總是正確的。
* 還是說，你有最佳化的心態？我很高興得知哪一種體驗能成功。 我們有足夠的意見可進行測試嗎？

### 假設也可能對結果產生負面影響

* 可能對您的有效性產生負面影響的假設。羊群心理 (我們的競爭對手就是這麼做的)。例如，我們所有的競爭者都使用帶有旋轉影像的主頁橫幅，因此我們也應該使用。
* 假設我們知道某些專案正常或不正常的原因。 假設我們不需要測試某樣事物。 例如，我們總是按從最高價格到最低價格的預設來列出酒店客房。
* 你是根據假設行事的嗎？我們不需要測試，我們已經檢查分析。 (我們需要檢查分析，但可能有更多是無法從分析得知的。)
* 還是說，你有最佳化的心態？我們測試一切。
