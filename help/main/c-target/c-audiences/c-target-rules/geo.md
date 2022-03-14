---
keywords: 鎖定目標;a4t;地理;地理鎖定目標;地理鎖定目標準確度;國家;州;城市;郵遞區號;dma;行動電信業者;城市碼;區域碼;都市碼;設定檔指令碼;地理鎖定目標設定檔指令碼;地理鎖定目標行動
description: 瞭解如何在 [!DNL Adobe Target] 根據用戶的地理位置來確定目標用戶。
title: 我能否根據地點確定訪問者？
feature: Audiences
solution: Target,Analytics
exl-id: e4a71a4d-e8f3-4f94-a1a7-fd250f4d5095
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '987'
ht-degree: 49%

---

# 地理

在 [!DNL Adobe Target] 根據用戶的地理位置來確定目標用戶。

地理位置參數使您能夠根據訪問者的地理位置確定活動和體驗。 您可以根據國家、州/省、城市、郵遞區號、緯度、經度、DMA 或行動電信業者來包含或排除訪客。此資料隨每個資料一起發送 [!DNL Target] 請求，並基於訪問者的IP地址。 選取這些參數就像任何定位值一樣。

## 建立具有地域目標的受眾 {#section_49CBFFAAC8694C4AAD3DE4B2DB7B05DE}

1. 在 [!DNL Target] 介面中，按一下&#x200B;**[!UICONTROL 「對象」]**>**[!UICONTROL 「建立對象」]**。
1. 命名訪問群體並添加可選說明。
1. 拖放 **[!UICONTROL 吉奧]** 對話框。

1. 按一下&#x200B;**[!UICONTROL 「選取」]**，然後選取下列其中一個選項:

   * [!UICONTROL 國家/地區]
   * [!UICONTROL 狀態]
   * [!UICONTROL 城市]
   * [!UICONTROL 郵遞區號]
   * [!UICONTROL 經度]
   * [!UICONTROL 緯度]
   * [!UICONTROL DMA]
   * [!UICONTROL 行動電信業者]

   會將訪客的 IP 位址與 mbox 請求一併傳遞，每次瀏覽 (作業) 傳遞一次，以解決該訪客的地理定位參數問題。

   對於 [!UICONTROL 移動運營商]。 [!DNL Target] 使用IP地址註冊資料（擁有IP地址塊的用戶）來確定適當的移動運營商， [移動國家代碼(MCC)和移動網路代碼(MNC)](https://www.mcc-mnc.com)。

1. 指定運算子和相應的值。
1. （可選）為受眾設定其他規則。
1. 按一下&#x200B;**[!UICONTROL 「完成」]**。

下圖顯示的受眾是從緯度大於44度、經度小於22度訪問活動的用戶。

![](assets/target_geo.png)

## 準確度 {#section_D63D5FFCB49C42F9933AFD0BD7C79DF1}

地理鎖定目標的準確度取決於幾項因素。WiFi 連線比行動電話通訊網路更準確。當訪客使用行動數據連線時，地理查閱的準確度會受到一些因素的影響，包括位置、提供者與 [DeviceAtlas](https://deviceatlas.com/device-data/user-agent-tester) 之間的資料關係，以及其他因素。行動通訊基地台網路連線可能比有線或 WiFi 連線更不準確。此外，訪問者的IP地址可能映射到訪問者的ISP位置，這可能與訪問者的實際位置不同。 利用MS-PC技術，可以解決移動地理位置問題 [地理位置API](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation_API)。

下表顯示 [DigitalEnvoy](https://www.digitalelement.com/solutions/) 針對有線或 WiFi 網際網路連線所提出的 IP 型地理位置資訊的準確度。DigitalEnvoy 提供的資料是業界最準確的。全球準確度在國家/地區層級超過 99.9%，在城市層級也能達到 97%。準確度資訊不適用於行動通訊基地台網路。

| 國家 | 狀態 | 城市 | 地區 |
|--- |--- |--- |--- |
| 美國 | 99.99% | 96% | 94% |
| 加拿大 | 99.99% | 9成6 | 9成4 |
| 歐洲 | 99.99% |  |  |
| 英國 | 99.99% |  | 87% |
| 德國 | 99.99% | 95% | 93% |
| 斯堪地那維亞 | 99% | 90% 出頭 | 約 85% |
| 西班牙 | 99.99% | 約 90% | 95% 以上 |
| 亞洲 | 9成9 | 約 95% | 90% 出頭 |
| 日本 | 99.99% | 約 95% | 90% 出頭 |
| 澳大利亞 | 99.99% | 9成4 | 91% |

## 在配置檔案指令碼中使用地理目標 {#section_92C93138542C4A94997E3F4BE3F5DA28}

您可以在設定檔指令碼中使用地理資訊。

例如，使用:

* `profile.geolocation.country`
* `profile.geolocation.state`
* `profile.geolocation.city`
* `profile.geolocation.zip`
* `profile.geolocation.dma`
* `profile.geolocation.domainName`
* `profile.geolocation.ispName`
* `profile.geolocation.connectionSpeed`
* `profile.geolocation.mobileCarrier`

因此，您可以使用以下程式碼來撰寫稱為「來自北美」的目標運算式:

`return profile.geolocation.country == 'united states' || profile.geolocation.country == 'canada' || profile.geolocation.country == 'mexico';`

## 將地理目標值用作標籤 {#section_E7F7FDF62C3B4934A6565D04B24655F6}

您可以使用 `profile.geolocation` 值直接作為優惠、插件等中的標籤。

例如，使用:

* `${profile.geolocation.country}`
* `${profile.geolocation.state}`
* `${profile.geolocation.city}`
* `${profile.geolocation.zip}`
* `${profile.geolocation.dma}`
* `${profile.geolocation.domainName}`
* `${profile.geolocation.ispName}`
* `${profile.geolocation.connectionSpeed}`
* `${profile.geolocation.mobileCarrier}`
* `${profile.geolocation.latitude}`
* `${profile.geolocation.longitude}`

## 以地域為目標的常見問題 {#section_DD308A53AF0F48FA8C81423580561FE7}

以下問題經常被問及：

### 如何指定緯度和經度?

* 緯度和經度值應為度數值。
* 緯度和經度的值最大精度可以為五位小數。
* 緯度的值應該介於 -90 和 90 之間。
* 經度的值應該介於 -180 和 180 之間。

### 地理定位在移動設備上如何工作？

大多數移動設備用戶通過WiFi訪問內容，這意味著 [!DNL Target]基於IP的地理定位與案頭一樣準確。 透過行動通訊基地台的連線可能較不準確，因為訪客的 IP 位址是以接收訊號的基地台為準。利用MS-PC技術，可以解決移動地理位置問題 [地理位置API](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation_API)。

### 地理功能如何處理來自 AOL 的訪客?

由於AOL代理其流量的方式， [!DNL Target] 只能在國家層面上瞄準他們。 例如，針對法國的活動成功地針對了法國的AOL用戶。 但針對巴黎的運動並沒有成功地瞄準巴黎的AOL用戶。 如果您希望特別定位 AOL 使用者，則您可以將區域欄位設定為「aol」。事實上，您可以指定兩個定位條件來定位美國的 AOL 使用者國家完全符合「美國」，而地區完全符合「aol」。

### 地理定位提供的位置精細度為何？

* 國家/地區 - 全球
* 州/省/區域 - 全球
* 城市 - 全球
* 郵遞區號 - 美國、德國、加拿大
* DMA/ITV (英國) - 美國、英國
* 行動電信業者 - 全球

### 如何以來自不同位置的使用者身分來測試我的活動?

* **at.js 1.*x***:您可以使用不同位置的IP地址覆蓋您的IP地址，並使用 `mboxOverride.browserIp url` 的下界。 例如，如果您的公司在英國，但您的全球活動針對紐西蘭奧克蘭的訪問者，則使用這種URL樣式假定 `60.234.0.39` 是奧克蘭的IP地址：

   `https://www.mycompany.com?mboxOverride.browserIp=60.234.0.39`

   在測試活動之前清除Cookie。

   >[!NOTE]
   >
   >`mboxOverride.browserIp` 在at.js 1中支援。*x* 版。at.js 2不支援此功能。*x*。

* **at.js 2.*x***:使用at.js 2覆蓋IP地址。*x*，安裝瀏覽器擴展/插件（如Chrome或Firefox的X-Forwarded-For標頭）。 此擴展允許您在頁面請求中傳遞x-forwarded-for頭。

### 波多黎各和香港等地區要如何對應至地理鎖定目標結構?

波多黎各、香港和其他地區視同個別的「國家/地區」值。

### 是 [!DNL Target] 當活動以地理位置目標功能為目標時，是否捕獲（並儲存郵遞區號）資訊？

不， [!DNL Target] 僅在會話期間使用geo資料，然後丟棄資料。

## 培訓視頻：建立受眾 ![教程徽章](/help/main/assets/tutorial.png)

此影片包括關於使用對象類別的資訊。

* 建立對象
* 定義對象類別

>[!VIDEO](https://video.tv.adobe.com/v/17392)
