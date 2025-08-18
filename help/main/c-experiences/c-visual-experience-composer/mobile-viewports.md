---
keywords: 回應式;行動檢視區;檢視區;裝置;行動;回應式網頁設計;rwd
description: 行動檢視區可協助您查看 Adobe [!DNL Target] 活動在各種大小的螢幕上的面貌。 尋找常用裝置檢視區大小和解析度清單。
title: 如何將行動檢視區用於回應式體驗？
feature: Visual Experience Composer (VEC)
exl-id: 1062e7a1-10b4-4746-bce9-67017978578d
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1350'
ht-degree: 94%

---

# 回應式體驗適用的行動檢視區

行動檢視區可讓您預覽您的 [!DNL Adobe Target] 活動在各種大小的螢幕上的面貌。

行動檢視區預覽功能是專為可適當呈現在各種裝置、視窗和螢幕大小的回應式網站所設計。 回應式網站會自動調整並適應任何螢幕大小，包括桌上型電腦、筆記型電腦、平板電腦或行動電話。

>[!NOTE]
>
> * 如果您的網站為回應式網站，且桌上型電腦頁面中的相同元素也透過不同的組態用於行動頁面中，請使用行動檢視區。 如果您有另一個行動網站具有不同的結構，例如 `m.mysite.com`，請改用[多頁活動](/help/main/c-experiences/c-visual-experience-composer/multipage-activity.md#concept_277E096063E14813AC5D8EDFA1D2ED48)。
>
>* 行動檢視區被重新導向產品建議覆蓋所重疊時會無法使用。

檢視區是以螢幕上的網頁填入的矩形大小來定義。 檢視區是瀏覽器視窗的大小減去捲軸和工具列。 瀏覽器使用「CSS 像素」。對於許多裝置，例如有視網膜螢幕的裝置，檢視區小於公布的裝置解析度。

底下是常用裝置的檢視區和解析度。 請記得在 [!DNL Target] 中使用檢視區大小。

>[!NOTE]
>
>各個網站都有列出常用裝置的檢視區大小。 如需範例，請參閱 `https://viewportsizer.com/devices/`。 如需最準確且最新的資訊，請查詢裝置製造商的網站。

| 裝置 | 檢視區大小（寬度x高度） | 裝置解析度 (寬度 x 高度) |
|---|---|---|
| iPhone 12 | 390 x 844 | 1170 x 2532 |
| iPhone 12 Mini | 360 x 780 | 1080 x 2340 |
| iPhone 12 Pro | 390 x 844 | 1170 x 2532 |
| iPhone 12 Pro Max | 428 x 926 | 1248 x 2778 |
| iPhone SE | 214 x 379 | 640 x 1136 |
| iPhone 11 Pro Max | 414 x 896 | 1242 x 2688 |
| iPhone 11 Xs Max | 414 x 896 | 1242 x 2688 |
| iPhone 11 | 414 x 896 | 828 x 1792 |
| iPhone 11 Xr | 414 x 896 | 828 x 1792 |
| iPhone 11 Pro | 375 x 812 | 1125 x 2436 |
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
| iPad Air 1 和 2 | 768 x 1024 | 1536 x 2048 |
| iPad Mini | 768 x 1024 | 768 x 1024 |
| iPad Mini 2 和 3 | 768 x 1024 | 1536 x 2048 |
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

若要將活動傳送給特定裝置上的訪客，請在活動圖表中選擇適合該裝置的客群。 使用「行動裝置網頁撰寫器」，針對該裝置來編輯活動中的頁面。 若要在整個數位體驗中執行活動以確保該活動在所有裝置上都顯示良好，請勿套用目標定位。 而是要改用行動檢視區來預覽該活動在各種螢幕大小上的面貌。

如果是回應式網站，您的網站通常會有以下設計：當具有特定螢幕大小的裝置存取網站時，在不同檢視中開啟。 觸發新檢視的螢幕大小稱為 CSS 中斷點。 CSS 中斷點是指網站內容做出回應的點，用以根據裝置寬度向訪客顯示最佳版面。 CSS 中斷點也稱為[媒體查詢](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)。

將 CSS 中斷點儲存在 [!DNL Target] 中，就可以針對您定義的每一個檢視來預覽體驗。 其中每個體驗都會顯示在 [!DNL Target] 介面的行動檢視區中。 若要開啟每個螢幕大小的檢視，請在畫面頂端按一下該檢視區。

如果網站不是回應式網站，只要活動是以特定裝置為目標，您仍可使用「行動裝置網頁撰寫器」來檢視網站。

>[!IMPORTANT]
>
>您可以在行動檢視區內編輯體驗。 不過，這些變更會套用到所有檢視區和裝置，而不只是您正在使用的檢視區。 同樣地，在標準桌上型電腦檢視中編輯體驗時，將會變更所有螢幕大小的頁面，而不只是桌上型電腦檢視。 目前，[!DNL Target] 不支援檢視區特有的頁面變更。

## 行動檢視區設定 {#task_B4B161499DC0470584ED922A4D20FCAB}

打造您的體驗時，請設定您要提供的行動檢視區。

1. 按一下&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Visual Experience Composer]**。
1. 在&#x200B;**[!UICONTROL Mobile viewports configuration]**&#x200B;區段中，按一下&#x200B;**[!UICONTROL Add]**。

   ![新增檢視區](/help/main/c-experiences/c-visual-experience-composer/assets/viewpoert_add.png)

   或

   若要變更現有行動檢視區的設定，請選取該檢視區，然後按一下[!UICONTROL Edit] （鉛筆）圖示。

1. 輸入行動檢視區的名稱。

   為您的行動檢視區提供易於識別的描述性名稱。名稱的長度最多可為 36 個字元。

1. 指定行動裝置的螢幕大小，包含寬度和高度。

   寬度可以是 150 到 968 像素。 高度可以是 150 到 1280 像素。

1. (可選) 選取裝置的作業系統。

   選項:

   * Android
   * iOS 
   * Windows
   * Symbian
   * Blackberry

   如果您使用[增強型體驗撰寫器](/help/main/c-experiences/experiences.md#section_34265986611B4AB8A0E4D6ACC25EF91D)並選擇作業系統，[!DNL Target] 會在您檢視頁面時模擬該裝置。 例如，如果您的回應式網站在 Android 與 iOS 上的外觀與風格有一些不同，[!DNL Target] 會模擬該行為。

1. 按一下 **[!UICONTROL Save]**。

>[!NOTE]
>
>如果您嘗試刪除使用中的行動檢視區，將會顯示以下訊息：「此檢視區目前與一或多個活動有關聯。 您必須先從這些活動中移除該檢視區，才能將其刪除。」

## 打造回應式體驗 {#task_D6332438B5EE48CCA8AF199270F1CAEF}

將行動檢視區新增到您的 [!DNL Target] 活動，為手機螢幕打造回應式體驗。

1. 建立[所需的活動](/help/main/c-activities/activities.md)。
1. 在[!UICONTROL Visual Experience Composer] (VEC)中，按一下&#x200B;**[!UICONTROL Settings]**&#x200B;齒輪圖示，然後選取&#x200B;**[!UICONTROL Add Mobile Viewports]**。

   ![「新增行動檢視區」選項](/help/main/c-experiences/c-visual-experience-composer/assets/add-mobile-viewports.png)

1. 按一下&#x200B;**[!UICONTROL Devices]**&#x200B;圖示，然後啟用每個應該具有行動檢視區的裝置。

   ![啟用行動檢視區](/help/main/c-experiences/c-visual-experience-composer/assets/mobileviewports.png)

   行動檢視區會根據寬度從最小到最大列出。

1. 視需要編輯行動檢視區。

   您對體驗所做的所有變更都會套用到所有裝置上的體驗。 例如，您可變更標題中的文字。

   將游標移至檢視區名稱的上方即可查看檢視區的大小。

   ![iPhone 11 Pro Max 回應式體驗](/help/main/c-experiences/c-visual-experience-composer/assets/iphone11.png)

1. 如有需要，請按一下所要的方向圖示，在直向與橫向模式之間切換。

   ![方向選項](/help/main/c-experiences/c-visual-experience-composer/assets/orientation.png)

## 培訓影片

以下影片含有本文章探討之概念的詳細資訊。

### 視覺化體驗撰寫器(2/2) (7:29) ![總覽徽章](/help/main/assets/overview.png)

下列示範影片包含透過視覺體驗撰寫器來使用行動檢視區的相關資訊:

* 重新命名和複製體驗
* 建立重新導向體驗
* 將活動鎖定在單一 URL 或一組 URL
* 建立多頁活動
* 針對回應性網站預覽和建置體驗
* 使用覆蓋來強調顯示元素的類型

>[!VIDEO](https://video.tv.adobe.com/v/17401)

### Adobe Target 中的帳戶偏好設定 ![概觀徽章](/help/main/assets/overview.png)

此影片包含設定行動檢視區的相關資訊，從影片中的4:40處開始。

>[!VIDEO](https://video.tv.adobe.com/v/17379)
