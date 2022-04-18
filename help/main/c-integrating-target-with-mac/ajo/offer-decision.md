---
keywords: 視覺體驗合成器選項；體驗合成器選項；體驗選項；提供決策；offer decisioning;ajo;journey optimizer選項
description: 瞭解如何添加在中建立的聘用決定 [!DNL Adobe Journey Optimizer] 到活動。
title: 如何使用優惠決定？
feature: Visual Experience Composer (VEC)
exl-id: cec46d5c-bb5e-4cc9-8785-370f158d3f8e
source-git-commit: b34f58bee9759eb7c621f8cbf763837d7eafb3fe
workflow-type: tm+mt
source-wordcount: '995'
ht-degree: 1%

---

# 使用報價決策

使用 [!DNL Adobe Target] 與 [!DNL Adobe Journey Optimizer] 提供決策，以確定並提供下一個最佳服務，供您在Web和移動設備上訪問。

添加在中建立的聘用決定 [!DNL Adobe Journey Optimizer] 至 [!DNL Target] 活動（手冊） [!UICONTROL A/BTest] 或 [!UICONTROL 體驗目標])使用 [!UICONTROL 視覺體驗作曲家] (VEC)或 [!UICONTROL 基於表單的作曲家] 通過您的入站渠道test並向訪問者提供個性化服務， [!DNL Target]。

有關 [!DNL Adobe Journey Optimizer] 提供決策，請參閱 *[!DNL Journey Optimizer]* 文檔：

* [開始使用 Journey Optimizer](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/get-started.html)

* [關於決策管理](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioniong/get-started/starting-offer-decisioning.html)

## 必要條件

在中使用優惠決定 [!DNL Target]，您需要：

* [!DNL Adobe Target Standard] 或 [!DNL Adobe Target Premium] 使用 [Adobe Experience PlatformWeb SDK](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md)。

   該功能在實施時不可用 [!DNL Target] 使用at.js或其他 [!DNL Target] SDK。

* [!DNL Adobe Journey Optimizer Ultimate] (AJ0 +Offer decisioning)或 [!DNL Adobe Experience Platform] 和 [!UICONTROL offer decisioning] 應用程式服務載入項。

## 示例使用案例

以下示例是如何使用 [!DNL Target]/[!DNL Adobe Journey Optimizer] 整合在 [!DNL Target] 活動：

### 體育商品

作為體育聯盟的營銷人員，您希望將首頁（案頭和移動網站）上的內容個性化。 您希望對基於多個維度的內容進行個性化，並向商店提供與特許經營商品相關的優惠。 您感興趣：

* 遊客最喜愛的團隊
* 最近的運動員/運動員活動（例如，團隊運動、合同更新或傷害）

例如，您希望為以下每個區域提供個性化體驗：多特蒙德，法蘭克福和波鴻，以及這些球隊內隱和明確的擁躉。 作為度量標準，您希望查看訪問並點擊商品站點。

要設計 [!UICONTROL A/BTest] 活動（50/50拆分），將預設體驗與個性化體驗（包括針對每個地區和團隊的優惠決定）進行分割。 您希望使用此活動來確定個性化體驗與控制的轉換和提升。

### 遊戲流平台

作為遊戲組織的營銷人員，您希望為不同地理位置的台式機和移動用戶提供個性化的遊戲流平台服務：德國、法國、墨西哥和巴西。 當訪問者從其中一個地理位置訪問案頭或移動網站時，您希望以本地語言提供遊戲流服務，並為本地貨幣提供相應的價格。

在 [!DNL Adobe Journey Optimizer]，您可以為每個目標地區建立個性化首頁英雄服務，並建立具有預設首頁英雄的備用服務。 然後，您可以建立包含這些聘用及其資格規則的聘用決定。 然後，在 [!DNL Target]，您可以建立 [!DNL Experience Targeting] (XT)活動，並在您的案頭或移動網站中插入提供決策，以便向訪問者提供個性化體驗。

## 建立使用優惠決策的體驗：

1. 編輯或建立手動 [!UICONTROL A/BTest] 或 [!UICONTROL 體驗目標] (XT) [!UICONTROL 視覺體驗作曲家] (VEC)，按一下頁面元素顯示 [選項菜單](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)。

   ![Visual Experience Composer中的「選項」菜單](assets/options-menu1.png)

   >[!NOTE]
   >
   >您還可以建立使用 [!UICONTROL 提供決定] 的 [[!UICONTROL 基於表單的體驗作曲家]](/help/main/c-experiences/form-experience-composer.md)。

1. 按一下 **[!UICONTROL 在前面插入]**。 **[!UICONTROL 在後面插入]**&#x200B;或 **[!UICONTROL 替換內容]**，然後按一下 **[!UICONTROL 提供決定]**。

   的 [!UICONTROL 提供決定] 選項 [手 [!UICONTROL A/BTest]](/help/main/c-activities/t-test-ab/test-ab.md#types) 或 [[!UICONTROL 體驗目標]](/help/main/c-activities/t-experience-target/experience-target.md) (XT)活動。 此選項不適用於其他活動類型。 菜單中的可用選項因所選元素而異。

   ![Visual Experience Composer中的「選項」菜單](assets/options-menu.png)

1. 在 **[!UICONTROL 添加聘用決定]** 對話框，選擇所需的沙盒和位置。

   A [沙坑](https://experienceleague.adobe.com/docs/experience-platform/sandbox/ui/overview.html){target=_blank} [!DNL Adobe Experience Platform] 允許您將實例分區到虛擬環境。 例如，您可能具有生產環境和轉移環境。 A [放置](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioniong/create-components/creating-placements.html){target=_blank，在 [!DNL Adobe Journey Optimizer] 有助於確保在適當的位置顯示適當的服務內容。

   ![「添加優惠決定」對話框中的「沙盒和放置」下拉清單](/help/main/c-integrating-target-with-mac/ajo/assets/sandbox-placement.png)

1. 選擇所需的優惠決定，然後按一下 **[!UICONTROL 建立]**。

   ![在「添加聘用決定」對話框中選擇聘用決定](assets/offer-decision.png)

   您的網站顯示在VEC中，您可以在其中查看新建立的聘用決策 [!UICONTROL 修改] 的下界。 可將滑鼠懸停在修改上，然後按一下 [!UICONTROL 預覽] 表徵圖以檢查聘用決定。

   ![預覽圖示](assets/preview-icon.png)

   您可以通過按一下產品底部的相應表徵圖來檢查產品中包含的各種產品 [!UICONTROL 提供預覽] 對話框，包括回退優惠。 回退優惠是當訪問者沒有資格獲得收藏中的任何個性化優惠時顯示的預設優惠。

   ![提供預覽](assets/offer-preview.png)

1. 通過完成 [!UICONTROL 目標] 和 [!UICONTROL 目標和設定] 三部分指導工作流的步驟。

   >[!IMPORTANT]
   >
   >確保 [!DNL Target] 活動是個性化的，請確保當前活動的開始/結束日期與中的服務決定的開始/結束日期同步 [!DNL Adobe Journey Optimizer]。 如果 [!DNL Target] 起始/終止日期在聘用決定的起始/終止日期範圍之外，預設日期 [!DNL Target] 內容顯示給訪問者。

   ![提供決策警告消息](/help/main/c-integrating-target-with-mac/ajo/assets/offer-decision-warning.png)

## 注釋和限制

處理聘用決定時，請考慮以下資訊：

* offer decisioning整合適用於 [!DNL Target] 基於 [Adobe Experience PlatformWeb SDK](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md)。 此功能在實施時不可用 [!DNL Target] 使用at.js或其他 [!DNL Target] SDK。

* 目標/Adobe Journey Optimizer整合支援 [手 [!UICONTROL A/BTest]](/help/main/c-activities/t-test-ab/test-ab.md#types) 和 [[!UICONTROL 體驗目標]](/help/main/c-activities/t-experience-target/experience-target.md) (XT)活動。 此功能不適用於其他活動類型。

* 文本/html內容類型的提供不支援deliveryURL內容傳遞。 只有客戶端負責顯式獲取和合成內容時，才通過基於表單的體驗合成器支援deliveryURL。

* [!DNL Target] 報告不提供服務決策級報告。

* 可視化 [QA連結](/help/main/c-activities/c-activity-qa/activity-qa.md) 為 [!DNL Target] 包含提供決策的體驗會影響 [!DNL Adobe Journey Optimizer] 來決定。
