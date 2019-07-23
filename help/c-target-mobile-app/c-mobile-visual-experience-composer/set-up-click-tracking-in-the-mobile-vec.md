---
description: 行動版可視化體驗撰寫器 (VEC) 支援設定 Target 活動的點擊追蹤目標。
keywords: 行動應用程式 VEC;行動版可視化體驗撰寫器;行動版體驗撰寫器選項;行動體驗選項;目標檢視;點按;點擊追蹤;追蹤
seo-description: 行動版可視化體驗撰寫器 (VEC) 支援設定 Adobe Target 活動的點擊追蹤目標。
seo-title: 在行動應用程式 VEC 中設定點擊追蹤
solution: Target
title: 在行動應用程式 VEC 中設定點擊追蹤
topic: Standard
uuid: 7e4ce7c0-0027-417c-8dae-45b6f5045e65
translation-type: tm+mt
source-git-commit: 2966ba0a89e6bfe1a7e6048e741100a95c09b8ff

---


# 在行動應用程式 VEC 中設定點擊追蹤{#set-up-click-tracking-in-the-mobile-vec}

行動應用程式 VEC 支援設定 [!DNL Target] 活動的點擊追蹤目標。

1. 在活動的「目標與設定」頁面上設定您的目標時，請選取[!UICONTROL 「轉換」]成功量度。

   ![](assets/mobile-vec-clicktrack1.png)

1. 針對動作，選取&#x200B;**[!UICONTROL 「點擊元素」]**，然後按一下&#x200B;**[!UICONTROL 「選取元素」]**。

   您的行動應用程式隨即在行動版可視化體驗撰寫器 (VEC) 中開啟。

   ![](assets/mobile-vec-clicktrack2.png)

1. 選取您要追蹤的任何元素。

   請參閱以下的[!UICONTROL 「考量事項」]區段，以取得選取元素的相關提示。

   ![](assets/mobile-vec-clicktrack3.png)

1. 按一下畫面上方的核取記號來儲存您的選擇項目。

若需重新開始，您也可以編輯和變更點擊選取項目或將其刪除。

![](assets/mobile-vec-clicktrack4.png)

當活動加入者點擊選取的元素時，該點擊會被計為轉換。

## 考量事項 {#considerations}

選取元素時，有數個項目要考慮:

* 如果選取了多個元素且訪客點按任何其中一個元素，則會計入該點按。若要個別計算每個點按，請為每個元素設定個別的成功量度。
* 使用者按一下元素後，點擊事件會立即傳送至 Target。
* 在行動應用程式 VEC 中，只能選取已附加點按處理常式的元素。
* 您可以瀏覽至應用程式的任何區段，但請確定已為您選取以進行點擊追蹤的元素區段定義[檢視](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md#target-views)。
* 編輯活動時，若已在步驟 1 中選取裝置，則無需再次選取裝置。但是，若直接登陸點擊追蹤頁面，您會看到可選取授權裝置的裝置選取畫面。
* 「Modifications」(修改)面板會顯示在Mobile App CMS中，顯示您已設定以進行點按追蹤的元素。

   ![顯示點按追蹤的修改面板
   ](/help/c-target-mobile-app/c-mobile-visual-experience-composer/assets/click-track-modifications-panel.png)