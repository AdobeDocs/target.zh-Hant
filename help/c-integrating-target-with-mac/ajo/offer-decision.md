---
keywords: 可視化體驗撰寫器選項；體驗撰寫器選項；體驗選項；選件決策；offer decisioning;ajo；歷程最佳化程式
description: 了解如何新增中建立的優惠方案決策 [!DNL Adobe Journey Optimizer] 至活動。
title: '如何使用選件決策？ '
feature: Visual Experience Composer (VEC)
source-git-commit: 39d278747cec838ef7855116c820e3c80160d364
workflow-type: tm+mt
source-wordcount: '1005'
ht-degree: 0%

---

# 使用優惠方案決策

使用 [!DNL Adobe Target] with [!DNL Adobe Journey Optimizer] 選件決策，以決定並傳送下一個最佳選件給網頁和行動裝置上的訪客。

新增在中建立的優惠方案決策 [!DNL Adobe Journey Optimizer] to [!DNL Target] 活動（手動） [!UICONTROL A/B測試] 或 [!UICONTROL 體驗鎖定])使用 [!UICONTROL 可視化體驗撰寫器] (VEC)或 [!UICONTROL 表單式撰寫器] 在您的傳入管道上，測試並提供個人化優惠方案給訪客， [!DNL Target].

>[!NOTE]
>
>此主題中說明的優惠方案決策功能預計於2022年1月13日發行，並搭配 [!DNL Target Standard/Premium] 22.1.1版。

如需 [!DNL Adobe Journey Optimizer]，請參閱 [開始使用Journey Optimizer](https://experienceleague-review.corp.adobe.com/docs/journey-optimizer/using/get-started/get-started.html) 在 *Journey Optimizer* 檔案。

如需優惠方案決策的詳細資訊，請參閱 [關於決策管理](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioniong/get-started/starting-offer-decisioning.html) 在 *[!DNL Journey Optimizer]檔案*.

## 必要條件

若要在中使用優惠方案決策 [!DNL Target]，您需要下列項目：

* [!DNL Adobe Target Standard] 或 [!DNL Adobe Target Premium] 使用實作 [Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md).

   實作時無法使用此功能 [!DNL Target] 搭配at.js或其他 [!DNL Target] SDK。

* [!DNL Adobe Journey Optimizer Ultimate] (AJ0 +Offer decisioning)或 [!DNL Adobe Experience Platform] 和 [!UICONTROL offer decisioning] 應用程式服務附加元件。

## 範例使用案例

以下範例是您如何使用 [!DNL Target]/[!DNL Adobe Journey Optimizer] 整合以在 [!DNL Target] 活動：

### 體育銷售

身為運動聯盟的行銷人員，您想要個人化首頁（桌上型電腦和行動網站）上的內容。 您想要根據訪客最喜愛的團隊和最近的播放器動作來個人化內容，以向他們提供購買相關加盟商品的優惠。 例如，若要為下列每個區域提供個人化體驗：多特蒙德、法蘭克福和波鴻，以及那些內隱和明確支援這些團隊的用戶。 作為量度，您想要查看商品網站的造訪和點按。

您想要在預設體驗和個人化體驗之間設計A/B測試活動(50/50分割)（包括針對每個地區和團隊的選件決策）。 您想要使用此活動來判斷個人化體驗與控制的轉換和提升度。

### 遊戲流平台

身為體育組織的行銷人員，您想要針對來自不同地理位置的案頭和行動使用者提供遊戲串流平台的個人化優惠方案：德國、法國、墨西哥和巴西。 當訪客從其中一個地理位置存取案頭或行動網站時，您想要以本地語言傳送遊戲串流優惠，並以本地貨幣為對應價格。

在 [!DNL Adobe Journey Optimizer]，您可以為每個目標地理位置建立個人化首頁主圖優惠方案，以及以預設首頁主圖建立後援優惠方案。 然後，您可以建立包含這些優惠方案及其適用性規則的優惠方案決策。 然後，在 [!DNL Target]，您可以建立 [!DNL Experience Targeting] (XT)活動，並將該優惠方案決策插入您的案頭或行動網站，以向訪客提供個人化體驗。

## 建立使用優惠方案決策的體驗：

1. 編輯或建立手冊時 [!UICONTROL A/B測試] 或 [!UICONTROL 體驗鎖定] (XT) [!UICONTROL 可視化體驗撰寫器] (VEC)，按一下頁面元素以顯示 [選項菜單](/help/c-experiences/c-visual-experience-composer/viztarget-options.md).

   ![可視化體驗撰寫器中的「選項」功能表](assets/options-menu1.png)

   >[!NOTE]
   >
   >您也可以建立使用 [!UICONTROL 選件決策] 在 [[!UICONTROL 表單式體驗撰寫器]](/help/c-experiences/form-experience-composer.md).

1. 按一下 **[!UICONTROL 插入在前]**, **[!UICONTROL 插入在後]**，或 **[!UICONTROL 取代內容]**，然後按一下 **[!UICONTROL 優惠方案決策]**.

   此 [!UICONTROL 優惠方案決策] 選項 [手動 [!UICONTROL A/B測試]](/help/c-activities/t-test-ab/test-ab.md#types) 或 [[!UICONTROL 體驗鎖定]](/help/c-activities/t-experience-target/experience-target.md) (XT)活動。 此選項不適用於其他活動類型。 功能表中的可用選項會依所選元素而有所不同。

   ![可視化體驗撰寫器中的「選項」功能表](assets/options-menu.png)

1. 在 **[!UICONTROL 新增優惠方案決策]** 對話框，選擇所需的沙箱和位置。

   A [沙箱](https://experienceleague.adobe.com/docs/experience-platform/sandbox/ui/overview.html){target=_blank}，位於 [!DNL Adobe Experience Platform] 可讓您將執行個體分割到虛擬環境。 例如，您可能有生產環境和預備環境。 A [刊登](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioniong/create-components/creating-placements.html){target=_blank} [!DNL Adobe Journey Optimizer] 有助於確保正確的選件內容顯示在正確的位置。

   ![新增優惠方案決策對話方塊中的沙箱和版位下拉式清單](/help/c-integrating-target-with-mac/ajo/assets/sandbox-placement.png)

1. 選取所需的優惠方案決策，然後按一下 **[!UICONTROL 建立]**.

   ![在新增優惠方案決策對話方塊中選取的優惠方案決策](assets/offer-decision.png)

   您的網站會顯示在VEC中，您可以在 [!UICONTROL 修改] 右側的窗格。 您可以將滑鼠移到修改上，然後按一下 [!UICONTROL 預覽] 圖示來檢查優惠方案決策。

   ![預覽圖示](assets/preview-icon.png)

   您可以按一下 [!UICONTROL 選件預覽] 對話方塊，包括後援優惠方案。 備援優惠方案是當訪客不符合集合中任何個人化優惠方案的資格時，所顯示的預設優惠方案。

   ![選件預覽](assets/offer-preview.png)

1. 完成建立活動，方法是 [!UICONTROL 定位] 和 [!UICONTROL 目標與設定] 三步驟引導式工作流程的步驟。

   >[!IMPORTANT]
   >
   >確保 [!DNL Target] 活動已個人化，請確定目前活動的開始/結束日期與 [!DNL Adobe Journey Optimizer]. 若 [!DNL Target] 開始/結束日期不在選件決策的開始/結束日期範圍內（預設值） [!DNL Target] 內容會對訪客顯示。

   ![優惠方案決策警告訊息](/help/c-integrating-target-with-mac/ajo/assets/offer-decision-warning.png)

## 附註和限制

處理優惠方案決策時，請考量下列附註和限制：

* offer decisioning整合適用於 [!DNL Target] 根據 [Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md). 實作時無法使用此功能 [!DNL Target] 搭配at.js或其他 [!DNL Target] SDK。

* Target/Adobe Journey Optimizer整合支援 [手動 [!UICONTROL A/B測試]](/help/c-activities/t-test-ab/test-ab.md#types) 和 [[!UICONTROL 體驗鎖定]](/help/c-activities/t-experience-target/experience-target.md) (XT)活動。 此功能不適用於其他活動類型。

* 具有文字/html內容類型的選件不支援deliveryURL內容傳送。 只有在用戶端負責明確擷取和撰寫內容時，表單式體驗撰寫器才支援deliveryURL。

* [!DNL Target] 報表不提供選件決策層級的報表。

* 視覺化 [QA連結](/help/c-activities/c-activity-qa/activity-qa.md) for [!DNL Target] 包含選件決策的體驗會影響設定於 [!DNL Adobe Journey Optimizer] 來做決定。








