---
description: Mobile Visual Experience Composer(CMS)支援設定Target活動的點按追蹤目標。
keywords: 行動應用程式CMS；行動視覺體驗撰寫器；行動體驗撰寫器選項；行動體驗選項；目標檢視；點按；點按追蹤；track
seo-description: Mobile Visual Experience Composer(CMS)支援設定Adobe Target活動的點按追蹤目標。
seo-title: 在行動應用程式CMS中設定點擊追蹤
solution: Target
title: 在行動應用程式CMS中設定點擊追蹤
topic: Standard
uuid: 7e4ce7c0-0027-417c-8dae-45b6f5045e65
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# 在行動應用程式CMS中設定點擊追蹤{#set-up-click-tracking-in-the-mobile-vec}

Mobile App CMS支援設定 [!DNL Target] 活動的點擊追蹤目標。

1. 在活動的「目標與設定」頁面上設定您的目標時，請選取[!UICONTROL 「轉換」]成功量度。

   ![](assets/mobile-vec-clicktrack1.png)

1. 針對動作，選取**[!UICONTROL 「點擊元素」]**，然後按一下**[!UICONTROL 「選取元素」]**。

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

* 選取多個元素時，如果訪客按一下任一元素，則會計算點按次數。若要分別計算每個點按次數，請為每個元素設定個別成功度量。
* 使用者按一下元素後，點擊事件會立即傳送至 Target。
* 在Mobile App CMS中，只允許選取已附加點按處理常式的元素。
* 您可以瀏覽至應用程式的任何區段，但請確定已為您選取以進行點擊追蹤的元素區段定義[檢視](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md#target-views)。
* 編輯活動時，若已在步驟 1 中選取裝置，則無需再次選取裝置。不過，如果您直接在點按追蹤頁面著陸，則會顯示裝置選擇畫面以選取授權裝置。
