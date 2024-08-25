---
keywords: 鎖定目標;a4t;地理;地理鎖定目標;地理鎖定目標準確度;國家;州;城市;郵遞區號;dma;行動電信業者;城市碼;區域碼;都市碼;設定檔指令碼;地理鎖定目標設定檔指令碼;地理鎖定目標行動
description: 瞭解如何在 [!DNL Adobe Target] 中建立對象，以根據使用者的地理位置鎖定使用者。
title: 我可以根據位置鎖定訪客嗎？
feature: Audiences
solution: Target,Analytics
exl-id: e4a71a4d-e8f3-4f94-a1a7-fd250f4d5095
source-git-commit: 195028613dec0294c816703b9145e720e3209d74
workflow-type: tm+mt
source-wordcount: '1014'
ht-degree: 41%

---

# 地理

在[!DNL Adobe Target]中使用受眾，根據使用者的地理位置鎖定使用者。

地理位置引數可讓您根據訪客的地理位置來鎖定目標活動和體驗。 您可以根據國家、州/省、城市、郵遞區號、緯度、經度、DMA 或行動電信業者來包含或排除訪客。此資料會根據訪客的IP位址，與每個[!DNL Target]要求一併傳送。 選取這些參數就像任何定位值一樣。

## 使用地理鎖定目標建立對象 {#section_49CBFFAAC8694C4AAD3DE4B2DB7B05DE}

1. 在[!DNL Target]介面中，按一下&#x200B;**[!UICONTROL Audiences]** > **[!UICONTROL Create Audience]**。
1. 為對象命名並新增選擇性說明。
1. 將&#x200B;**[!UICONTROL Geo]**&#x200B;拖放至對象產生器窗格。

1. 按一下&#x200B;**[!UICONTROL Select]**，然後選取下列其中一個選項：

   * [!UICONTROL Country/Region]
   * [!UICONTROL State]
   * [!UICONTROL City]
   * [!UICONTROL Zip Code]
   * [!UICONTROL Longitude]
   * [!UICONTROL Latitude]
   * [!UICONTROL DMA]
   * [!UICONTROL Mobile Carrier]

   訪客的地理資訊是根據 [!DNL Target] 位置請求 (Mbox 請求) 的起始 IP 位置來判定。IP 對地理位置的解析是在新工作階段的首次呼叫時完成。也就是說，如果訪客的 IP 位址在造訪期間發生變更，地理資訊仍會根據首次呼叫的 IP 位址。

   針對[!UICONTROL Mobile Carrier]，[!DNL Target]會使用IP位址註冊資料（擁有IP位址區塊），使用[行動裝置國碼(MCC)和行動網路碼(MNC)](https://www.mcc-mnc.com)來決定適當的行動電信業者。

1. 指定運運算元和適當的值。
1. （選用）為對象設定其他規則。
1. 按一下 **[!UICONTROL Done]**。

下圖顯示某個受眾，鎖定從緯度大於44度和經度小於22度之位置存取活動的使用者。

![target_geo影像](assets/target_geo.png)

## 準確度 {#section_D63D5FFCB49C42F9933AFD0BD7C79DF1}

地理鎖定目標的準確度取決於幾項因素。WiFi 連線比行動電話通訊網路更準確。當訪客使用行動資料連線時，地理查閱的準確度會受到一些因素的影響，包括位置、提供者與[DeviceAtlas](https://deviceatlas.com/device-data/user-agent-tester)的資料關係，以及其他因素。 行動通訊基地台網路連線可能比有線或 WiFi 連線更不準確。此外，訪客的IP位址可能會對應至訪客的ISP位置，而此位置可能與訪客的實際位置不同。 某些行動地理位置問題可以使用[地理位置API](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation_API)來解決。

下表顯示 [DigitalEnvoy](https://www.digitalelement.com/solutions/) 針對有線或 WiFi 網際網路連線所提出的 IP 型地理位置資訊的準確度。DigitalEnvoy 提供的資料是業界最準確的。全球準確度在國家/地區層級超過 99.9%，在城市層級也能達到 97%。準確度資訊不適用於行動通訊基地台網路。

| 國家 | 狀態 | 城市 | 地區 |
|--- |--- |--- |--- |
| 美國 | 99.99% | 96% | 94% |
| 加拿大 | 99.99% | 96% | 94% |
| 歐洲 | 99.99% |  |  |
| 英國 | 99.99% |  | 87% |
| 德國 | 99.99% | 95% | 93% |
| 斯堪地那維亞 | 99% | 90% 出頭 | 約 85% |
| 西班牙 | 99.99% | 約 90% | 95% 以上 |
| 亞洲 | 99% | 約 95% | 90% 出頭 |
| 日本 | 99.99% | 約 95% | 90% 出頭 |
| 澳大利亞 | 99.99% | 94% | 91% |

## 在設定檔指令碼中使用地理定位 {#section_92C93138542C4A94997E3F4BE3F5DA28}

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

## 使用地理定位值做為代號 {#section_E7F7FDF62C3B4934A6565D04B24655F6}

您可以直接使用`profile.geolocation`值做為選件、外掛程式等中的Token。

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

## 地理定位常見問題集 {#section_DD308A53AF0F48FA8C81423580561FE7}

以下是有關地理定位的常見問題：

### 如何指定緯度和經度？

+++查看詳細資料
* 經緯度的值應為以度為單位的數值。
* 經緯度的值最多可精確至五位小數。
* 緯度的值應該介於 -90 和 90 之間。
* 經度的值應該介於 -180 和 180 之間。

+++

### 行動裝置的地理鎖定目標如何運作？

+++檢視詳細資料
大部分行動裝置使用者透過WiFi存取內容，這表示[!DNL Target]以IP為基礎的地理鎖定目標與桌上型電腦一樣準確。 透過行動通訊基地台的連線可能較不準確，因為訪客的 IP 位址是以接收訊號的基地台為準。某些行動地理位置問題可以使用[地理位置API](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation_API)來解決。

+++

### 地理功能如何處理來自AOL的訪客？

+++檢視詳細資料
由於AOL代理其流量的方式，[!DNL Target]只能在國家層級鎖定這些流量。 例如，以法國為目標的促銷活動已成功以法國的AOL使用者為目標。 但以巴黎為目標的促銷活動無法成功鎖定巴黎的AOL使用者。 如果您希望特別定位 AOL 使用者，則您可以將區域欄位設定為「aol」。事實上，您可以指定兩個定位條件來定位美國的 AOL 使用者國家完全符合「美國」，而地區完全符合「aol」。

+++

### 地理鎖定目標提供的位置精度如何？

+++查看詳細資料
* 國家/地區 - 全球
* 州/省/區域 - 全球
* 城市 - 全球
* 郵遞區號 - 美國、德國、加拿大
* DMA/ITV (英國) - 美國、英國
* 行動電信業者 - 全球

+++

### 如何以來自不同位置的使用者身分來測試我的活動？

+++查看詳細資料
* **at.js 1.*x***：您可以使用其他位置的IP位址來覆寫您的IP位址，並使用`mboxOverride.browserIp url`引數。 例如，如果您的公司位於英國，但您的全球促銷活動目標訪客位在紐西蘭的奧克蘭，則您可以使用這種URL，假設`60.234.0.39`是奧克蘭境內的IP位址：

  `https://www.mycompany.com?mboxOverride.browserIp=60.234.0.39`

  在測試活動之前清除您的Cookie。

  >[!NOTE]
  >
  >at.js 1支援`mboxOverride.browserIp`。*x* 版。at.js 2.*x*。

* **at.js 2.*x***：若要使用at.js 2.*x*，安裝瀏覽器擴充功能/外掛程式(例如Chrome或Firefox的X-Forwarded-For Header)。 此擴充功能可讓您在頁面請求中傳遞x-forwarded-for標頭。

+++

### 波多黎各和香港等領土如何對應至地理定位結構？

+++檢視詳細資料
波多黎各、香港和其他地區被視為單獨的「國家」值。

+++

### 以地理位置定位功能鎖定活動時，[!DNL Target]是否會擷取（及儲存）如郵遞區號的資訊？

+++檢視詳細資料
否，[!DNL Target]只會在工作階段期間使用地理資料，然後會捨棄資料。

+++

## 訓練影片：建立對象![教學課程徽章](/help/main/assets/tutorial.png)

此影片包括關於使用對象類別的資訊。

* 建立客群
* 定義對象類別

>[!VIDEO](https://video.tv.adobe.com/v/17392)
