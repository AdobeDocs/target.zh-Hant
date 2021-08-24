---
keywords: 回應式；行動檢視區；檢視區；裝置；行動；回應式網頁設計；行
description: 行動檢視區可協助您查看Adobe [!DNL Target] 活動在各種大小的螢幕上的呈現方式。 尋找熱門裝置檢視區大小和解析度的清單。
title: 如何將行動檢視區用於回應式體驗？
feature: 可視化體驗撰寫器 (VEC)
exl-id: 1062e7a1-10b4-4746-bce9-67017978578d
source-git-commit: 2041a335c0396d1147ff57ee416942228daa7aa5
workflow-type: tm+mt
source-wordcount: '1159'
ht-degree: 38%

---

# 回應式體驗的行動檢視區

行動檢視區可讓您在各種大小的畫面上預覽[!DNL Adobe Target]活動。

行動檢視區預覽功能專為回應式網站而設計，在各種裝置、視窗和螢幕大小上皆呈現良好。 回應式網站會自動調整並適應任何螢幕大小，包括桌上型電腦、筆記型電腦、平板電腦或行動電話。

>[!NOTE]
>
> * 如果網站具回應力，而桌面頁面中的相同元素也透過不同的組態用於行動頁面中，請使用行動檢視區。如果您有獨立的行動網站具有獨立的結構，例如`m.mysite.com`，請改用[多頁活動](/help/c-experiences/c-visual-experience-composer/multipage-activity.md#concept_277E096063E14813AC5D8EDFA1D2ED48)。
   >
   >
* 行動檢視區被重新導向選件覆蓋所重疊時會無法使用。


檢視區是以螢幕上的網頁所填入的矩形大小來定義。檢視區是瀏覽器視窗的大小，減去捲軸和工具列。 瀏覽器使用「CSS 像素」。對於許多裝置，例如有視網膜螢幕的裝置，檢視區小於公布的裝置解析度。

以下是常用裝置的檢視區和解析度。 請記得在[!DNL Target]中使用檢視區大小。

>[!NOTE]
>
>有許多網站都有列出熱門裝置的檢視區大小。如需範例，請參閱 `https://viewportsizer.com/devices/`. 如需最準確的最新資訊，請造訪裝置製造商網站。

| 裝置 | 檢視區大小 （寬x高） | 裝置解析度（寬x高） |
|---|---|---|
| iPhone 12 | 390 x 844 | 1170 x 2532 |
| iPhone 12 Mini | 360 x 780 | 1080 x 2340 |
| iPhone 12 Pro | 390 x 844 | 1170 x 2532 |
| iPhone 12 Pro Max | 428 x 926 | 1248 x 2778 |
| iPhone SE | 214 x 379 | 640 x 1136 |
| iPhone 11 Pro Max | 414 x 896 | 1242 x 2688 |
| iPhone 11 Xs最大 | 414 x 896 | 1242 x 2688 |
| iPhone 11 | 414 x 896 | 828 x 1792 |
| iPhone 11 Xr | 414 x 896 | 828 x 1792 |
| iPhone 12 Pro | 375 x 812 | 1125 x 2436 |
| iPhone 11 X | 375 x 812 | 1125 x 2436 |
| iPhone 11 Xs | 375 x 812 | 1125 x 2436 |
| iPhone X | 375 x 812 | 1125 x 2436 |
| iPhone 8 Plus | 414 x 736 | 1080 x 1920 |
| iPhone 8 | 375 x 667 | 750 x 1334 |
| iPhone 7 Plus | 414 x 736 | 1080 x 1920 |
| iPhone 7 | 375 x 667 | 750 x 1334 |
| iPhone 6s Plus | 414 x 736 | 1080 x 1920 |
| iPhone 6s | 375 x 667 | 750 x 1334 |
| iPhone 6 Plus | 414 x 736 | 1080 x 1920 |
| iPhone 6 | 375 x 667 | 750 x 1334 |
| iPad Pro | 1024 x 1366 | 2048 x 2732 |
| iPad 第 3 代與第 4 代 | 768 x 1024 | 1536 x 2048 |
| iPad Air 1 與 2 | 768 x 1024 | 1536 x 2048 |
| iPad Mini | 768 x 1024 | 768 x 1024 |
| iPad Mini 2 與 3 | 768 x 1024 | 1536 x 2048 |
| Nexus 6P | 411 x 731 | 1440 x 2560 |
| Nexus 5X | 411 x 731 | 1080 x 1920 |
| Google Pixel | 411 x 731 | 1080 x 1920 |
| Google Pixel XL | 411 x 731 | 1440 x 2560 |
| Google Pixel 2 | 411 x 731 | 1080 x 1920 |
| Google Pixel 2 XL | 411 x 823 | 1440 x 2880 |
| Samsung Galaxy Note 5 | 480 x 853 | 1440 x 2560 |
| LG G5 | 360w x 640 | 1440 x 2560 |
| LG G4 | 360w x 640 | 1440 x 2560 |
| LG G3 | 360w x 640 | 1440 x 2560 |
| One Plus 3 | 480 x 853 | 1080 x 1920 |
| Samsung Galaxy S9 | 360 x 740 | 1440 x 2960 |
| Samsung Galaxy S9+ | 360 x 740 | 1440 x 2960 |
| Samsung Galaxy S8 | 360 x 740 | 1440 x 2960 |
| Samsung Galaxy S8+ | 360 x 740 | 1440 x 2960 |
| Samsung Galaxy S7 | 360 x 640 | 1440 x 2560 |
| Samsung Galaxy S7 Edge | 360 x 640 | 1440 x 2560 |
| Nexus 7 (2013) | 600 x 960 | 1200 x 1920 |
| Nexus 9 | 768 x 1024 | 1536 x 2048 |
| Samsung Galaxy Tab 10 | 800 x 1280 | 800 x 1280 |
| Chromebook Pixel | 1280 x 850 | 2560 x 1700 |

若要傳送活動給特定裝置上的訪客，請在活動圖表中為該裝置選擇適當的對象。 使用「行動裝置 Web 撰寫器」，針對該裝置來編輯活動中的頁面。若要在整個數位體驗中執行活動，以確保在所有裝置上都看起來不錯，請勿套用鎖定目標。 請改為使用行動檢視區，在每個螢幕大小上預覽活動。

對於回應式網站，通常您的網站是設計為在由具有特定螢幕大小的裝置存取時，以不同檢視開啟。 觸發新檢視的螢幕大小稱為 CSS 中斷點。CSS中斷點是網站內容根據裝置寬度回應，以向訪客顯示最佳配置的點。 CSS斷點也稱為[媒體查詢](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)。

將CSS中斷點儲存在[!DNL Target]中，以便您可以針對所定義的每個檢視預覽體驗。 這些體驗會顯示在[!DNL Target]介面的行動檢視區中。 若要開啟每一個螢幕大小的檢視，請在畫面頂端按一下該檢視區。

如果您的網站沒有回應，如果您的活動鎖定在特定裝置上，請使用行動網站撰寫器來檢視網站。

>[!IMPORTANT]
>
>您可以從行動檢視區內編輯體驗。 不過，這些變更會套用至所有檢視區和裝置，而不只是您正在使用的檢視區。 同樣地，在標準桌面檢視中編輯體驗時，將會變更所有螢幕大小的頁面，而不只是桌面檢視。目前，[!DNL Target]不支援檢視區專屬的頁面變更。

## 行動檢視區設定 {#task_B4B161499DC0470584ED922A4D20FCAB}

設定在建立體驗時要提供使用的行動檢視區。

1. 按一下「**[!UICONTROL 管理]** > **[!UICONTROL 可視化體驗撰寫器]**」。
1. 在&#x200B;**[!UICONTROL 行動檢視區設定]**&#x200B;區段中，按一下&#x200B;**[!UICONTROL 新增]**。

   ![新增檢視區](/help/c-experiences/c-visual-experience-composer/assets/viewpoert_add.png)

   或

   若要變更現有行動檢視區的設定，請選取該檢視區，然後按一下「[!UICONTROL 編輯]（鉛筆）」圖示。

1. 輸入行動檢視區的名稱。

   為您的行動檢視區提供易於識別的描述性名稱。名稱的長度最多可為 36 個字元。

1. 指定行動裝置的螢幕大小，包括寬度和高度。

   寬度可以是150到968像素。 高度可以是150到1280像素。

1. (可選) 選取裝置的作業系統。

   選項:

   * Android
   * iOS 
   * Windows
   * Symbian
   * Blackberry

   如果您使用[增強體驗撰寫器](/help/c-experiences/experiences.md#section_34265986611B4AB8A0E4D6ACC25EF91D)並選擇作業系統， 會在您檢視頁面時模擬該裝置。[!DNL Target]例如，如果回應式網站上的Android與iOS的外觀和風格不同，[!DNL Target]會模擬該行為。

1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

>[!NOTE]
>
>如果您嘗試刪除正在使用的行動檢視區，會顯示下列訊息：「此檢視區目前與一或多個活動相關聯。 您必須先從這些活動中移除視區，才能刪除它。」

## 建立回應式體驗 {#task_D6332438B5EE48CCA8AF199270F1CAEF}

將行動檢視區新增至您的[!DNL Target]活動，為行動螢幕建立回應式體驗。

1. 建立[所需的活動](/help/c-activities/activities.md)。
1. 在[!UICONTROL 可視化體驗撰寫器](VEC)中，按一下&#x200B;**[!UICONTROL Settings]**&#x200B;齒輪圖示，然後選取&#x200B;**[!UICONTROL Add Mobile Viewports]**。

   ![新增行動檢視區選項](/help/c-experiences/c-visual-experience-composer/assets/add-mobile-viewports.png)

1. 按一下&#x200B;**[!UICONTROL 「裝置」]**&#x200B;圖示，然後啟用應該具有行動檢視區的每個裝置。

   ![啟用行動檢視區](/help/c-experiences/c-visual-experience-composer/assets/mobileviewports.png)

   行動檢視區會根據寬度從最小到最大列出。

1. 視需要編輯行動檢視區。

   您對體驗所做的任何變更都會套用至所有裝置上的體驗。 例如，您可以變更標題中的文字。

   將游標移至檢視區的名稱來查看檢視區的大小。

   ![iPhone 11 Pro Max回應式體驗](/help/c-experiences/c-visual-experience-composer/assets/iphone11.png)

1. 如果需要，請按一下所需的方向圖示，在直向和橫向模式之間切換。

   ![方向選項](/help/c-experiences/c-visual-experience-composer/assets/orientation.png)

## 訓練影片

以下影片含有本文章探討之概念的詳細資訊。

### 可視化體驗撰寫器 (2/2) (上午 07:29)  ![概述徽章](/help/assets/overview.png)

下列示範影片包含透過可視化體驗撰寫器來使用行動檢視區的相關資訊:

* 重新命名和複製體驗
* 建立重新導向體驗
* 將活動鎖定在單一 URL 或一組 URL
* 建立多頁活動
* 針對回應性網站預覽和建置體驗
* 使用覆蓋來強調顯示元素的類型

>[!VIDEO](https://video.tv.adobe.com/v/17401)

### Adobe Target中的帳戶偏好設定![概述徽章](/help/assets/overview.png)

此影片包含設定行動檢視區的相關資訊，從影片的4:40開始。

>[!VIDEO](https://video.tv.adobe.com/v/17379)
