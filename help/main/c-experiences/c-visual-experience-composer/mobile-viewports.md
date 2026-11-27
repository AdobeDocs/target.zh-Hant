---
keywords: 回應式;行動檢視區;檢視區;裝置;行動;回應式網頁設計;rwd
description: 行動檢視區可協助您檢視Adobe [!DNL Target]活動在各種大小的Screens上的面貌。 尋找常用裝置檢視區大小和解析度清單。
title: 如何將行動檢視區用於回應式體驗？
feature: Visual Experience Composer (VEC)
exl-id: 1062e7a1-10b4-4746-bce9-67017978578d
TQID: 'https://experienceleague.adobe.com/uBJtaoaCh28mRGwc-SlK-XhU6sOIK3RaT58-ZXxSsHw'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '1126'
ht-degree: 19%
---
# 回應式體驗適用的行動檢視區 {#mobile-viewports}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解如何設定行動檢視區，並使用它們來預覽和建置各種大小熒幕的體驗。

>[!ENDSHADEBOX]

行動檢視區會以各種裝置的熒幕大小顯示[!DNL Adobe Target]個活動。 它們專為回應式網站而設計，可自動調整以適合桌上型電腦、筆記型電腦、平板電腦和行動電話，並且可讓您檢查體驗是否會在每個網站上呈現良好。

>[!NOTE]
>
> * 當網站為回應式且行動頁面以不同版面配置重複使用案頭頁面元素時，請使用行動檢視區。 當行動網站是分開的並具有自己的結構時，例如`m.mysite.com`，請改用[多頁活動](/help/main/c-experiences/c-visual-experience-composer/multipage-activity.md#multipage-activity)。
>
>* 當重新導向選件覆蓋與行動檢視區重疊時，行動檢視區將不可用。

## 檢視區和CSS中斷點

檢視區是網頁所填滿的熒幕區域：瀏覽器視窗的大小減去卷軸和工具列。 瀏覽器會以CSS畫素來測量檢視區，因此在許多裝置上（例如配備網際網路熒幕的裝置），檢視區會小於公告的裝置解析度。 一律使用[!DNL Target]中的檢視區大小。 下表列出常用裝置的兩個值。

+++ 常用裝置的檢視區和解析度

>[!NOTE]
>
>各個網站都有列出常用裝置的檢視區大小。 如需範例，請參閱 `https://viewportsizer.com/devices/`。 如需最準確且最新的資訊，請查詢裝置製造商的網站。
>
>檢視區大小標示為「估計」。 為預估值。

| 裝置 | 檢視區大小（寬度x高度） | 裝置解析度 (寬度 x 高度) |
|---|---|---|
| iPhone 18 Pro Max | 440 x 956 | 1320 x 2868 |
| iPhone 18 Pro | 402 x 874 | 1206 x 2622 |
| iPhone 17 Pro Max | 440 x 956 | 1320 x 2868 |
| iPhone 17 Pro | 402 x 874 | 1206 x 2622 |
| iPhone航空 | 420 x 912 | 1260 x 2736 |
| iPhone 17 | 402 x 874 | 1206 x 2622 |
| iPhone 16e | 390 x 844 | 1170 x 2532 |
| iPad (A16) | 820 x 1180 | 1640 x 2360 |
| iPad mini (A17 Pro) | 744 x 1133 | 1488 x 2266 |
| iPad Air 11英吋(M3 / M4) | 820 x 1180 | 1640 x 2360 |
| iPad Pro 11英吋(M5) | 834 x 1210 | 1668 x 2420 |
| Google Pixel 11 | 412 x 924 （東部標準時間） | 1080 x 2424 |
| Google Pixel 11 Pro | 410 x 914 （估計值） | 1280 x 2856 |
| Google Pixel 11 Pro XL | 448 x 997 （東部標準時間） | 1344 x 2992 |
| Google Pixel 10 | 412 x 924 | 1080 x 2424 |
| Google Pixel 10 Pro | 410 x 914 （估計值） | 1280 x 2856 |
| Google Pixel 10 Pro XL | 448 x 997 （東部標準時間） | 1344 x 2992 |
| Samsung Galaxy S26 | 360 x 780 | 1080 x 2340 |
| Samsung Galaxy S26 Ultra | 412 x 891 | 1440 x 3120 |
| iPhone Duo （展開） | 890 x 626 （估計值） | 2670 x 1878 |
| iPhone Duo （摺疊） | 466 x 678 （東部標準時間） | 1398 x 2034 |
| Samsung Galaxy Z Fold 7 （摺疊） | 412 x 960 （估計值） | 1080 x 2520 |
| Samsung Galaxy Z Flip 8 | 360 x 840 （估計值） | 1080 x 2520 |
| Google Pixel 11 Pro Fold （展開） | 791 x 820 （估計值） | 2076 x 2152 |

+++

回應式網站會以特定熒幕大小切換至不同的版面。 這些大小稱為CSS中斷點或[媒體查詢](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)。 將網站的CSS中斷點儲存在[!DNL Target]中可預覽每個檢視，然後按一下顯示頂端的檢視區，即可開啟該熒幕大小的檢視。

若要將活動傳送至特定裝置，請在活動圖表中選取該裝置的閱聽眾，然後在行動裝置網頁撰寫器中編輯該裝置的頁面。 當活動鎖定特定裝置時，相同的工具可用來檢視沒有回應的網站。 若要在所有裝置上執行活動，請套用無目標定位，並使用行動檢視區預覽每個熒幕大小的活動。

>[!IMPORTANT]
>
>體驗可從行動檢視區內編輯，但變更會套用至所有檢視區和裝置，而不僅套用至使用中的檢視區。 同樣地，在案頭檢視中編輯體驗會變更所有熒幕大小的頁面。 [!DNL Target]目前不支援檢視區特有的頁面變更。

## 行動檢視區設定 {#task_B4B161499DC0470584ED922A4D20FCAB}

定義建立體驗時可用的行動檢視區。

1. 按一下&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 視覺化體驗撰寫器]**。
1. 在&#x200B;**[!UICONTROL 行動檢視區組態]**&#x200B;區段中，按一下&#x200B;**[!UICONTROL 新增]**。

   ![新增檢視區](/help/main/c-experiences/c-visual-experience-composer/assets/viewpoert_add.png)

   或

   若要變更現有行動檢視區的設定，請選取該檢視區，然後按一下&#x200B;**[!UICONTROL 編輯]** （鉛筆）圖示。

1. 輸入行動檢視區的描述性名稱。 名稱的長度最多可為 36 個字元。
1. 輸入行動裝置的熒幕大小。 寬度可以是150到968畫素，高度可以是150到1280畫素。
1. (可選) 選取裝置的作業系統。

   選項:

   * Android
   * iOS
   * Windows
   * Symbian
   * Blackberry

   如果已啟用[增強體驗撰寫器](/help/main/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#enable-eec)並選取作業系統，[!DNL Target]會在檢視頁面時模擬該裝置。 例如，如果回應式網站在Android與iOS中的外觀與風格不同，[!DNL Target]會模擬該行為。

1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

>[!NOTE]
>
>嘗試刪除使用中的行動檢視區會顯示下列訊息：「此檢視區目前與一或多個活動相關聯。 您必須先從這些活動中移除該檢視區，才能將其刪除。」

## 打造回應式體驗 {#task_D6332438B5EE48CCA8AF199270F1CAEF}

將行動檢視區新增至[!DNL Target]個活動，為行動熒幕建立回應式體驗。

1. 建立[所需的活動](/help/main/c-activities/activities.md)。
1. 在&#x200B;**[!UICONTROL 視覺化體驗撰寫器]** (VEC)中，按一下&#x200B;**[!UICONTROL 設定]**&#x200B;齒輪圖示，然後選取&#x200B;**[!UICONTROL 新增行動檢視區]**。

   ![「新增行動檢視區」選項](/help/main/c-experiences/c-visual-experience-composer/assets/add-mobile-viewports.png)

1. 按一下&#x200B;**[!UICONTROL 裝置]**&#x200B;圖示，然後啟用每個應該具有行動檢視區的裝置。

   ![啟用行動檢視區](/help/main/c-experiences/c-visual-experience-composer/assets/mobileviewports.png)

   行動檢視區會根據寬度從最小到最大列出。

1. 視需要在行動檢視區中編輯體驗。 任何變更都會套用到所有裝置上的體驗，例如標題文字的變更。 將滑鼠懸停在檢視區名稱上，即可檢視檢視區的大小。

   ![iPhone 11 Pro Max 回應式體驗](/help/main/c-experiences/c-visual-experience-composer/assets/iphone11.png)

1. （選用）按一下方向圖示，在直向與橫向模式之間切換。

   ![方向選項](/help/main/c-experiences/c-visual-experience-composer/assets/orientation.png)

## 培訓影片

以下影片包含行動檢視區的詳細資訊。

### 視覺化體驗撰寫器(2/2) (7:29) ![總覽徽章](/help/main/assets/overview.png)

下列示範影片包含使用視覺化體驗撰寫器來使用行動檢視區的相關資訊：

* 重新命名和複製體驗
* 建立重新導向體驗
* 將活動鎖定在單一 URL 或一組 URL
* 建立多頁活動
* 針對回應性網站預覽和建置體驗
* 使用覆蓋來強調顯示元素的類型

>[!VIDEO](https://video.tv.adobe.com/v/17401)

### Adobe Target 中的帳戶偏好設定 ![概觀徽章](/help/main/assets/overview.png)

此影片包含設定行動檢視區的相關資訊，從影片中的4:40處開始。

>[!VIDEO](https://video.tv.adobe.com/v/3507634?captions=chi_hant)
