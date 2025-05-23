---
keywords: 歡迎套件;target 歡迎套件;介紹;簡介;開始
description: 閱讀我們的專家小組所提供有關使用 Adobe [!DNL Target] 當做測試與個人化工作之一部分的提示。
title: 何處可以找到有關使用 Target 的提示和訣竅？
feature: Overview
exl-id: 86437ad1-83ea-4670-b503-6c3c1fff0c16
source-git-commit: 52f11998149cddeb4245a0f07280562d79332a04
workflow-type: tm+mt
source-wordcount: '2883'
ht-degree: 72%

---

# 第 4 章：使用 Target 的提示

根據我們與許多[!DNL Target]使用者的合作，我們觀察到您從[!DNL Target]解決方案中獲得更多價值的方式。 我們在本章中提供的許多秘訣中已加以總結。 雖然您可能還沒準備好立即使用這些概念，但請繼續閱讀這份清單。您使用解決方案的經驗越多，程式越成熟，您就會越瞭解這些秘訣如何協助您使用[!DNL Target]完成更多工作。

## 提示 1：透過增加訪客個人檔案，深化個人化。

您可以立即使用 [!DNL Target] 資料個人化體驗。但是，將您自己的資料加入組合中，以更深度的個人化。您可以使用 [!DNL Adobe Analytics] 的歷史資料和 [!DNL Adobe Audience Manager] 的即時資料來擴充您的個人檔案。您也可以使用 [!DNL Adobe Experience Cloud] 中「人員」核心服務中的「客戶屬性」功能，輕鬆將 CRM 資料、第二方合作夥伴資料及第三方購買的資料匯入 [!DNL Target]。

例如，您可以將銷售點系統的購買資料與訪客資料建立關聯。若要這麼做，只需建立包含最多 200 個離線變數的 CSV 檔案，然後透過檔案上傳直接上傳至 [!DNL Adobe Experience Cloud]，或使用 FTP 代管並排程您的檔案，以定期更新。 一旦您的客戶屬性位於 [!DNL Adobe Experience Cloud]中，您就可以將它們對應至 [!DNL Experience Cloud] 解決方案，例如 [!DNL Adobe Analytics] 和 [!DNL Target]，以便用於分析、測試和個人化。

如需逐步指示，請參閱[自訂屬性](https://experienceleague.adobe.com/docs/target/using/audiences/visitor-profiles/working-with-customer-attributes.html?lang=zh-Hant&?lang=zh-Hant)。

**很高興知道**：由於 [!DNL Target] 此平台是開放且不可知的平台，可以搭配不同的技術運作，因此您可以以多種不同的方式新增 CRM 或購買的資料。這表示您可以選擇最適合您組織的方法。

如需詳細資訊，請參閱[將資料匯入Target](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=zh-Hant){target=_blank}的方法。

## 提示 2：將 [!DNL Target] 客群與其他 Adobe Experience Cloud 客群混合，以實現更深度的個人化。

混合不同 [!DNL Adobe Experience Cloud] 解決方案的客群，可讓您更全面地瞭解客戶，並更深入地個人化客戶。例如，雖然 [!DNL Target] 提供即時客群資料，但 [!DNL Adobe Analytics] 提供歷史客群資料。結合這兩者可協助您識別客戶的行為何時一致，以及何時可能有機會對新行為採取行動。 建立活動時，只要按一下「所有訪客」旁的下拉式功能表即可。 接著，核取最多20個對象的方塊，按一下「合併多個對象」，然後按一下「儲存」。

如需逐步指示，請參閱[結合多個客群](/help/main/c-target/combining-multiple-audiences.md)。

**很高興知道**：[!DNL Adobe Audience Manager] 客群會自動在 [!DNL Target] 中使用。但 [!DNL Adobe Analytics] 客群共用需要手動設定。在[!DNL Analytics]的對象建立程式中，只要勾選標示「讓這成為Experience Cloud對象」的方塊即可。 然後從[!DNL Target]按一下「匯入Experience Cloud對象」。

## 提示 3：從 [!DNL Target] 匯出資料以搭配協力廠商工具使用。

使用回應權杖，管理員可輕鬆將資料從 [!DNL Target] 取出並放入協力廠商工具。當您想要將資料新增至調查工具中收集的資料時，這會很有幫助。例如，如果調查顯示某個人口的體驗分數為「9」，而另一個人的體驗分數為「4」，則您可以使用您的資料來檢視哪些人看到體驗A，哪些人看到體驗B。您也可以使用回應Token將[!DNL Target]資料匯出至內部資料倉儲。 只要按一下「管理」，然後將所要的回應Token旁的開關切換至開啟位置。 接著，建立活動。然後，資料就可以傳輸給第三方廠商。您可以使用偵錯工具來驗證 [!DNL Target] 是否正在匯出資料。

如需逐步指示，請參閱[回應權杖](/help/main/administrating-target/response-tokens.md)。

**有用的提示**：在管理員啟動與第三方相關的回應Token之前，開發人員必須先與該第三方公司建立合作關係。

如需逐步指示，請參閱[回應權杖](/help/main/administrating-target/response-tokens.md)。

**請先執行此動作**：請確定您使用的是 at.js 1.1 版或更新版本。如果您使用舊版，將會看到回應Token，但at.js將無法使用。

## 提示 4：從這些關鍵變數建立客群，以增加活動的價值。

在建立目標客群或測試促銷和產品建議時，請先考慮下列變數：

* 行為。網站造訪模式與購買模式
* 反向連結。反向連結網站和促銷活動
* 時間。每日時間、一週中的天數和季節性因素
* 離線。在實體商店造訪及購買模式
* 環境。原產國、作業系統、瀏覽器類型

## 提示 5：為使用者提供完成工作所需的存取權等級。

讓您輕鬆處理組織的資料，同時確保資料安全。 [!DNL Target Premium] 可讓管理員控制授予不同內部和外部團隊的存取權等級。

如需詳細資訊，請參閱[企業使用者權限](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)。

**有用的提示**：新增使用者時，如果先前未將團隊成員的名稱新增至您的組織，例如第三方代理商員工的名稱，輸入其電子郵件地址和密碼將觸發電子郵件邀請以加入團隊的工作區。

使用 Target Standard？ 您仍然可以為具有唯讀、編輯和批准者角色的用戶[分配三個訪問級別](/help/main/administrating-target/c-user-management/c-user-management/user-management.md)！

## 提示 6：透過在客戶歷程中的每個頁面測試產品建議，瞭解該產品建議在客戶歷程中的表現。

瞭解產品建議 (例如免費運送) 在您網站上跨多個頁面的客戶歷程中的效能。

如需逐步指示，請參閱[多頁活動](/help/main/c-experiences/c-visual-experience-composer/multipage-activity.md)。

**有用的提示**：在您指定頁面範圍之後變更URL將會重設體驗。 這表示您指定的變數將不再出現。如果您需要變更 URL，請記得重新定義體驗。

## 提示 7：測試包含不同客群的產品建議，以發現客群是否有不同的偏好。

使用「體驗版本」，您可以針對您想要的客群，執行一項包含各種變數的測試。例如，您可以建立提供免運費的橫幅廣告，包括美國、英國和歐盟客戶的影像和貨幣變化，而不需針對三個不同的客群執行測試。

如需逐步指示，請參閱A/B測試中的[多個體驗對象](/help/main/c-activities/t-test-ab/t-test-create-ab/target-experience-to-multiple-audiences.md)。

## 提示 8：在類似頁面上複製活動體驗，以節省時間。

在單一網頁上建立變數（例如新的按鈕顏色），並自動套用至共用相同範本的所有頁面。您可以指定頁面，或將變數套用至網站上所有類似的頁面。

如需逐步指示，請參閱[在類似頁面上加入相同的體驗](/help/main/c-experiences/c-visual-experience-composer/temtest.md)。

## 提示 9：建立一次性客群，以減少客群資料庫的雜亂。

如果您鎖定的是您知道不會再鎖定的區段（例如，受意外天氣事件影響的客戶），建立一次性使用的對象可協助您完成工作，而不會增加對象庫的雜亂。 這可讓您更輕鬆地找到您一再使用的客群。

如需逐步指示，請參閱[建立僅限活動的客群](/help/main/c-target/creating-activity-only-audience.md)。

**高請求的功能**：我們的客戶要求我們盡可能避免單一使用客群自動儲存至客群庫。現在，他們不再需要手動刪除客群，讓其資料庫井然有序。

## 提示 10：不讓測試執行標準 QA 程式，以更快的速度執行簡單測試。

沒有什麼比讓活動準備就緒，然後等待數週，以完成標準 QA 流程更糟的了。您只需將幾個 QA 連結傳遞給同事，即可在各種瀏覽器上試用，以進行大部分的 QA 活動。您最可能想要針對大幅改變網站功能的工作進行更多 QA 測試，但實際上，這些活動應該更少，而更基本的活動應該更多。新增更佳的權限控制項，讓更少的人能將內容完全推展至現場，也增加了有意義的限制，讓您在不犧牲速度和效率的情況下完成所需的工作。另一個選擇是擁有指定的 IT 資源，以便及時監督 QA 流程。

如需逐步指示，請參閱[活動 QA](/help/main/c-activities/c-activity-qa/activity-qa.md)。

## 提示 11：在高流量頁面上執行測試，讓測試更快達到統計意義。

許多行銷人員會啟動客群細分和鎖定的最佳化計畫，而不需檢查所呈現的流量層級和客群是否會在測試時段內為其最佳化和轉換目標提供重要結果。要避免這種常見錯誤，請事先回答以下問題：

* 該頁面有多少個每日獨特訪客？
* 頁面的轉換率是多少？
* 您預期需要執行測試多久才能放心地稱為完成？

**實用提示**：使用[!DNL Adobe Target] [樣本大小電腦](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6)協助判斷成功測試所需的樣本大小。

## 提示 12：設計更簡單的測試，以確保您能夠建立並實作這些測試。

在考慮到如何設計測試的各個方面後，一個計畫就會變得非常複雜。根據您的業務與測試，以及您的群組設計、編碼、執行和分析結果的能力，判斷測試是否過於雄心勃勃。 如果是，請準備好減少其範圍和複雜性。從小開始比完全不執行測試更好。如果您從未啟動測試，就無法提供具影響力的提升。 在團隊的抱負與您的資源與能力的實際狀況之間取得平衡，是很重要的。

## 提示 13：將複雜的測試分成較小的測試活動，以便實現。

與其使用多種變數來開發大型測試和複雜的開發，不如使用最小變數來開發較不複雜的系列小型測試。這可讓您根據特定變數，更深入地瞭解測試效能。它還減少了大型項目開發時可能出現的技術問題。

![將複雜的測試分成較小測試插圖](/help/main/c-intro/assets/break-complex-tasks.png)

## 提示 14：在更接近轉換漏斗的端部進行測試，以最大化您的測試影響。

在離訪客點按「完整購買」、「提交應用程式」或完成轉換的頁面較近的位置進行測試，通常會產生最具影響力的結果。到達漏斗終點的訪客更符合資格、投入更多時間並準備購買，因此測試其偏好和動作的深入資訊可協助您進行有利的變更。由於購買路徑上的頁面對轉換率至關重要，因此在這些頁面上進行的測試應在推出之前，先由主要利益相關方進行。

![轉換漏斗插圖](/help/main/c-intro/assets/conversion-funnel.png)

## 提示 15：不斷更新您的測試，以進行反覆改進。

如果您的假設沒有被證明是正確的，請考慮如何改進測試。請記住，即使測試體驗沒有哪個表現更好，您的實驗並不是浪費時間。 成功的測試並不總能提高收入或轉換率。 如果測試確實支援您的假設，您就會著手開發一般理論。 但即使您有明確的贏取結果，也不要止步於此。 行銷人員常常會犯錯誤，只測試一次，然後指望這些結果，而不真正瞭解導致成功的因素。相反地，計畫對這些結果進行反複研究，以找出領先者為何領先。這將引導您獲得更深入的見解，以便用於未來的宣傳活動。

## 提示 16：比較測試和個人化活動以瞭解想法，以改進目標鎖定。

比較不同位置測試中不同對象的轉換效能，有助於集中精確公司的最佳化策略。 使用測試比較來識別哪些客群最有價值進行測試、哪些客群應該接收目標體驗，以及哪些類型的體驗最有可能引發回應。

例如，金融服務客戶針對包含專業體育賽事獎勵的信用卡執行促銷活動。透過對其著陸頁面進行部分工廠多元化測試，客戶得以最佳平衡信用卡產品建議訊息與運動獎勵，以鎖定與客戶群不同的客群。這種方式讓公司能夠在重大體育賽事的時間敏感視窗中，利用並最大化轉換率。

## 提示 17：如果您知道可以對資料採取行動，請只啟動測試，讓測試變得有用。

如果您不清楚如何處理資料，測試就毫無意義。 這包括瞭解您的關鍵成功量度、推播成功者需要採取哪些動作、您要如何追蹤測試結果，以及您將如何處理客群資訊。為了快速且成功地進行測試，參與測試的每個群組（開發人員、創意人員、測試專家和其他人員）在測試啟動前都必須瞭解其角色。

## 提示 18：在啟動測試之前，請確定企業支援推送成功者。

成功的最佳化組織相信測試的概念，並瞭解他們對於哪些體驗能贏得測試的專業意見並不總是成立。 他們根據堅實的資料基礎來決定成功者，並且急切且願意在結果生效後即時推動成功體驗，即使它不符合他們的期望或看似違反直覺。

例如，Adobe醫療服務客戶最近展示測試的價值，顯示團隊認為的主要橫幅實際上對轉換有負面影響。如果您的組織尚未完全接受測試，最好先進行更簡單、範圍更小的測試，以便逐步變更測試結果。

## 提示 19：讓每個人都知道您已啟動測試，以避免在網站變更時擔心。

設定活動以使用QA參數的好處之一，就是您可以與團隊中的每個人共用這些連結。您可以讓更多人知道此活動，並確保他們在點選測試變體時，不認為網站運作不正常。

完成測試後，您可以通訊促銷活動啟動、測試結果，尤其是所學的課程，協助您建立對測試結果的認知和興趣。與組織中的每個人分享結果也避免重新測試假設、教育每個人什麼有效，並協助他們根據您的發現，從根本上挑戰自己對什麼有效的想法。 您最好準備一個範本，每次都用來分享您的發現和關鍵學習。
然後，考慮建立可共用的書籍或 Microsoft PowerPoint 資料夾，以累積擷取這些學習內容。

## 提示 20：運用行動功能來建立更具創意的行動活動。

平板電腦和智慧型手機的使用者體驗需要將焦點放在觸控式控制項上，作為主要訪客互動，而非滑鼠點按和鍵盤控制項。運用行動顯示控制項，包括手指滑動、觸控、拖曳、夾捏和縮放。使用簡單、大型的按鈕來指定互動和導覽，例如大型購物車或視訊播放按鈕。如果針對行動零售進行設計，請整合針對裝置類型最佳化的多樣化產品視覺化。隨時尋找將使用者體驗焦點轉移到內嵌、大型檢視器或全螢幕互動式縮放和平移、360度旋轉和增強視訊功能的機會。

## 提示 21：透過最佳化行動搜尋，協助行動訪客找到他們想要的。

行動使用者擁有高意願。他們大多在 m-commerce 網站上使用搜尋功能，因此行動網站搜尋最佳化至關重要。若要改善行動裝置的搜尋引擎最佳化 (SEO)，請使用明確的導覽提示，以方便瀏覽。此外，在搜尋輸入方塊中實作自動建議和自動修正，以解決行動輸入的困難。針對螢幕大小和位置提供最佳化、吸引人且相關的搜尋結果。

## 提示 22：使用行動 SEM 促銷活動的每日定位時間，更能觸及行動客群。

瞭解如何及何時觸及您的對象，以及如何透過「日分」您的行動行銷活動在一天中分為不同的區段，更好地管理您的每日廣告支出。

許多行銷人員犯了以下錯誤：在特定裝置使用量最大時，未能分配足夠預算以捕捉到該份額的聲音，因此會留下大量收入並佔據上風。

例如，平板電腦的使用量通常會在晚上時段尖峰，而且許多使用者在看電視時會瀏覽。相反地，智慧型手機使用者通常會在外出時存取內容。最高轉換時間也因產業而異，因此瞭解您的獨特客戶何時最有可能採取行動非常重要。

## 請記住

在接下來的章節之前，請先考慮以下想法：「測試和個人化活動的靈感。」

### 當您建立測試時，不要裝飾，要有意為之。

* 以轉換點為焦點的目標眼路來控制流量。
* 確定您使用房地產是有利的。
* 運用影像焦點來確保影像不是裝飾，而是適合您使用。
* 使用簡化的複本，減少雜亂、摩擦和模糊。
* 當您需要使用者採取動作時，請確定您有「有效動作呼叫」。
* 盡可能透過使用者產生的內容來增加可信度。

### 簡化您的網站。

* 請勿「迫使」客戶閱讀。 他們不會。
* 輕鬆掃描。
* 使用項目符號複製區塊。
* 確保您的複本遵循清楚、循序的思考流程。

### 使用有效的行動號召 (CTA)

* 站在客戶的立場。
* 使用行動導向語言。
* 考慮轉換的動機。
* 處理轉換的結果。
* 請確定有 CTA！

