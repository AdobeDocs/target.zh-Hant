---
keywords: 響應；移動視區；視區；設備；移動；響應性；mobile viewports;viewport;devices;mobile;ropsend web design;rwd
description: 移動視區可幫助您瞭解Adobe [!DNL Target] 活動可在各種大小的螢幕上查看。 查找常用設備視區大小和解析度的清單。
title: 如何使用移動視區來獲得響應性體驗？
feature: Visual Experience Composer (VEC)
exl-id: 1062e7a1-10b4-4746-bce9-67017978578d
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1155'
ht-degree: 37%

---

# 回應式體驗的行動檢視區

移動視區可預覽 [!DNL Adobe Target] 各種大小的螢幕上的活動。

移動視區預覽功能設計用於在各種設備、窗口和螢幕尺寸上呈現良好的響應站點。 響應性站點可自動調整並適應任何螢幕大小，包括台式機、筆記型電腦、平板電腦或行動電話。

>[!NOTE]
>
> * 如果網站具回應力，而桌面頁面中的相同元素也透過不同的組態用於行動頁面中，請使用行動檢視區。如果您有一個單獨的移動站點，其結構是獨立的，例如 `m.mysite.com`，使用 [多頁活動](/help/main/c-experiences/c-visual-experience-composer/multipage-activity.md#concept_277E096063E14813AC5D8EDFA1D2ED48) 的雙曲餘切值。
>
>* 行動檢視區被重新導向選件覆蓋所重疊時會無法使用。


檢視區是以螢幕上的網頁所填入的矩形大小來定義。視區是瀏覽器窗口的大小，減去捲動條和工具欄。 瀏覽器使用「CSS 像素」。對於許多裝置，例如有視網膜螢幕的裝置，檢視區小於公布的裝置解析度。

以下是常用設備的視區和解析度。 切記在中使用視區大小 [!DNL Target]。

>[!NOTE]
>
>有許多網站都有列出熱門裝置的檢視區大小。如需範例，請參閱 `https://viewportsizer.com/devices/`. 有關最準確、最新的資訊，請咨詢設備製造商的網站。

| 裝置 | 檢視區大小 （寬x高） | 設備解析度（寬x高） |
|---|---|---|
| iPhone 12 | 390 x 844 | 1170 x 2532 |
| iPhone12迷你 | 360 x 780 | 1080 x 2340 |
| iPhone12 Pro | 390 x 844 | 1170 x 2532 |
| iPhone12 Pro Max | 428 x 926 | 1248 x 2778 |
| iPhoneSE | 214 x 379 | 640 x 1136 |
| iPhone11 Pro Max | 414 x 896 | 1242 x 2688 |
| iPhone11 Xs最大 | 414 x 896 | 1242 x 2688 |
| iPhone 11 | 414 x 896 | 828 x 1792 |
| iPhone11 Xr | 414 x 896 | 828 x 1792 |
| iPhone11 | 375 x 812 | 1125 x 2436 |
| iPhone11 X | 375 x 812 | 1125 x 2436 |
| iPhone11 Xs | 375 x 812 | 1125 x 2436 |
| iPhoneX | 375 x 812 | 1125 x 2436 |
| iPhone 8 Plus | 414 x 736 | 1080 x 1920 |
| iPhone 8 | 375 x 667 | 750 x 1334 |
| iPhone 7 Plus | 414 x 736 | 1080 x 1920 |
| iPhone 7 | 375 x 667 | 750 x 1334 |
| iPhone6s+ | 414 x 736 | 1080 x 1920 |
| iPhone 6s | 375 x 667 | 750 x 1334 |
| iPhone 6 Plus | 414 x 736 | 1080 x 1920 |
| iPhone 6 | 375 x 667 | 750 x 1334 |
| iPadPro | 1024 x 1366 | 2048 x 2732 |
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

要向特定設備上的訪問者傳遞活動，請在活動圖中為該設備選擇適當的訪問者。 使用「行動裝置 Web 撰寫器」，針對該裝置來編輯活動中的頁面。要在整個數字型驗中運行活動，確保活動在所有設備中都看起來不錯，請不要應用目標。 而是使用移動視區在每個螢幕大小上預覽活動。

對於響應性站點，通常您的站點設計為在由具有特定螢幕大小的設備訪問時以不同視圖開啟。 觸發新檢視的螢幕大小稱為 CSS 中斷點。CSS斷點是網站內容根據設備寬度做出響應的點，以向訪問者顯示最佳佈局。 也調用了CSS斷點 [媒體查詢](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)。

將CSS斷點保存到 [!DNL Target] 這樣，您就可以為定義的每個視圖預覽您的體驗。 這些體驗的每一個都顯示在 [!DNL Target] 。 若要開啟每一個螢幕大小的檢視，請在畫面頂端按一下該檢視區。

如果您的站點沒有響應，則使用Mobile Web Composer查看您的活動針對特定設備的站點。

>[!IMPORTANT]
>
>可以從移動視區中編輯體驗。 但是，這些更改適用於所有視區和設備，而不僅適用於您正在使用的視區。 同樣地，在標準桌面檢視中編輯體驗時，將會變更所有螢幕大小的頁面，而不只是桌面檢視。目前， [!DNL Target] 不支援視區特定的頁面更改。

## 移動視區配置 {#task_B4B161499DC0470584ED922A4D20FCAB}

配置在建立體驗時要使用的移動視區。

1. 按一下 **[!UICONTROL 管理]** > **[!UICONTROL 視覺體驗作曲家]**。
1. 在 **[!UICONTROL 移動視區配置]** ，按一下 **[!UICONTROL 添加]**。

   ![添加視區](/help/main/c-experiences/c-visual-experience-composer/assets/viewpoert_add.png)

   或

   要更改現有移動視區的配置，請選擇該視區，然後按一下 [!UICONTROL 編輯] （鉛筆）表徵圖。

1. 輸入行動檢視區的名稱。

   為您的行動檢視區提供易於識別的描述性名稱。名稱的長度最多可為 36 個字元。

1. 指定移動設備的螢幕大小，包括寬度和高度。

   寬度可以為150到968像素。 高度可以為150到1280像素。

1. (可選) 選取裝置的作業系統。

   選項:

   * Android
   * iOS 
   * Windows
   * Symbian
   * Blackberry

   如果您使用[增強體驗撰寫器](/help/main/c-experiences/experiences.md#section_34265986611B4AB8A0E4D6ACC25EF91D)並選擇作業系統， 會在您檢視頁面時模擬該裝置。[!DNL Target]比如說，如果你的敏感網站上的安卓和iOS的外觀不同， [!DNL Target] 模仿那種行為。

1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

>[!NOTE]
>
>如果嘗試刪除正在使用的移動視區，將顯示以下消息：「此視區當前與一個或多個活動關聯。 您必須先從這些活動中移除視區，才能刪除它。」

## 建立快速響應的體驗 {#task_D6332438B5EE48CCA8AF199270F1CAEF}

將移動視區添加到 [!DNL Target] 為移動螢幕建立響應體驗的活動。

1. 建立 [期望的活動](/help/main/c-activities/activities.md)。
1. 在 [!UICONTROL 視覺體驗作曲家] (VEC)，按一下 **[!UICONTROL 設定]** 「齒輪」表徵圖，然後選擇 **[!UICONTROL 添加移動視區]**。

   ![添加移動視區選項](/help/main/c-experiences/c-visual-experience-composer/assets/add-mobile-viewports.png)

1. 按一下&#x200B;**[!UICONTROL 「裝置」]**&#x200B;圖示，然後啟用應該具有行動檢視區的每個裝置。

   ![啟用移動視區](/help/main/c-experiences/c-visual-experience-composer/assets/mobileviewports.png)

   行動檢視區會根據寬度從最小到最大列出。

1. 視需要編輯行動檢視區。

   您對體驗所做的任何更改都將應用於所有設備上的體驗。 例如，您更改標題中的文本。

   將游標移至檢視區的名稱來查看檢視區的大小。

   ![iPhone11 Pro Max響應體驗](/help/main/c-experiences/c-visual-experience-composer/assets/iphone11.png)

1. 如果需要，按一下所需的方向表徵圖可在縱向模式和橫向模式之間切換。

   ![方向選項](/help/main/c-experiences/c-visual-experience-composer/assets/orientation.png)

## 訓練影片

以下影片含有本文章探討之概念的詳細資訊。

### 可視化體驗撰寫器 (2/2) (上午 07:29) ![概述徽章](/help/main/assets/overview.png)

下列示範影片包含透過可視化體驗撰寫器來使用行動檢視區的相關資訊:

* 重新命名和複製體驗
* 建立重新導向體驗
* 將活動鎖定在單一 URL 或一組 URL
* 建立多頁活動
* 針對回應性網站預覽和建置體驗
* 使用覆蓋來強調顯示元素的類型

>[!VIDEO](https://video.tv.adobe.com/v/17401)

### Adobe Target帳戶首選項 ![概述徽章](/help/main/assets/overview.png)

此視頻包含有關設定移動視區的資訊，從視頻的4:40開始。

>[!VIDEO](https://video.tv.adobe.com/v/17379)
