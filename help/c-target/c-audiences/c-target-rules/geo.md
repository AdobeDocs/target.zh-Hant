---
keywords: 鎖定目標;a4t;地理;地理鎖定目標;地理鎖定目標準確度;國家;州;城市;郵遞區號;dma;行動電信業者;城市碼;區域碼;都市碼;設定檔指令碼;地理鎖定目標設定檔指令碼;地理鎖定目標行動
description: 根據使用者的地理位置，包括其國家/地區、州/省、城市、郵遞區號、DMA 或行動電信業者，使用 Adobe Target 受眾來鎖定使用者。
title: 觀眾中的地理選項
feature: Audiences
solution: Target,Analytics
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '970'
ht-degree: 88%

---


# 地理{#geo}

根據使用者的地理位置，包括其國家/地區、州/省、城市、郵遞區號、DMA 或行動電信業者來鎖定使用者。

地理位置參數可讓您依據訪客的地理位置來鎖定目標活動和體驗。您可以根據國家、州/省、城市、郵遞區號、緯度、經度、DMA 或行動電信業者來包含或排除訪客。此資料會根據訪客的 IP 位址，與每一個 Target 請求一併傳送。選取這些參數就像任何定位值一樣。

## 使用地理鎖定目標建立對象 {#section_49CBFFAAC8694C4AAD3DE4B2DB7B05DE}

1. 在 [!DNL Target] 介面中，按一下&#x200B;**[!UICONTROL 「對象」]**>**[!UICONTROL 「建立對象」]**。
1. 為對象命名。
1. 按一下「**[!UICONTROL 新增規則]** > **[!UICONTROL 地理]**」。

1. 按一下&#x200B;**[!UICONTROL 「選取」]**，然後選取下列其中一個選項:

   * 國家
   * 狀態
   * 城市
   * 郵遞區號
   * 緯度
   * 經度
   * DMA
   * 行動電信業者

   會將訪客的 IP 位址與 mbox 請求一併傳遞，每次瀏覽 (作業) 傳遞一次，以解決該訪客的地理定位參數問題。

   關於行動電信業者，[!DNL Target] 會使用 IP 位址註冊資料 (擁有 IP 位址區塊)，根據[行動裝置國碼 (MCC) 和行動網路碼 (MNC)](https://www.mcc-mnc.com) 來決定適當的行動電信業者。

1. 指定運算子和適當的值。
1. (可選) 按一下&#x200B;**[!UICONTROL 「新增規則」]**&#x200B;並設定對象的其他規則。
1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

下圖顯示某個受眾，鎖定從緯度大於 44 度和經度小於 22 度之位置存取活動的使用者。

![](assets/target_geo.png)

## 準確度 {#section_D63D5FFCB49C42F9933AFD0BD7C79DF1}

地理鎖定目標的準確度取決於幾項因素。WiFi 連線比行動電話通訊網路更準確。當訪客使用行動數據連線時，地理查閱的準確度會受到一些因素的影響，包括位置、提供者與 [DeviceAtlas](https://deviceatlas.com/device-data/user-agent-tester) 之間的資料關係，以及其他因素。行動通訊基地台網路連線可能比有線或 WiFi 連線更不準確。另外，訪客的 IP 位址可能對應至 ISP 位置，而此位置可能與訪客的實際位置不同。使用[Geolocation API](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation_API)可解決某些行動地理位置問題。

下表顯示 [DigitalEnvoy](https://www.digitalelement.com/solutions/) 針對有線或 WiFi 網際網路連線所提出的 IP 型地理位置資訊的準確度。DigitalEnvoy 提供的資料是業界最準確的。全球準確度在國家/地區層級超過 99.9%，在城市層級也能達到 97%。準確度資訊不適用於行動通訊基地台網路。

| 國家 | 狀態 | 城市 | 地區 |
|--- |--- |--- |--- |
| 美國 | 99.99% | 96% | 94% |
| 加拿大 | 百分之九十九點九九 | 96% | 94% |
| 歐洲 | 百分之九十九點九九 |  |  |
| 英國 | 百分之九十九點九九 |  | 87% |
| 德國 | 百分之九十九點九九 | 95% | 93% |
| 斯堪地那維亞 | 99% | 90% 出頭 | 約 85% |
| 西班牙 | 百分之九十九點九九 | 約 90% | 95% 以上 |
| 亞洲 | 99% | 約 95% | 90% 出頭 |
| 日本 | 百分之九十九點九九 | 約 95% | 90% 出頭 |
| 澳大利亞 | 百分之九十九點九九 | 94% | 91% |

## 在設定檔指令碼中使用地理鎖定目標  {#section_92C93138542C4A94997E3F4BE3F5DA28}

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

## 使用地理定位值做為 Token {#section_E7F7FDF62C3B4934A6565D04B24655F6}

您現在可以直接使用 `profile.geolocation` 值做為選件、外掛程式等中的 Token。

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

## 地理定位常見問題解答 {#section_DD308A53AF0F48FA8C81423580561FE7}

**如何指定緯度和經度?**

* 緯度/經度的值應該為數值 (度數)。
* 緯度/經度的值最大精確度為五位小數。
* 緯度的值應該介於 -90 和 90 之間。
* 經度的值應該介於 -180 和 180 之間。

**行動裝置的地理鎖定目標如何運作?**

絕大多數的行動裝置使用者透過 WiFi 存取內容，這表示 Target 的 IP 型地理鎖定目標可以像桌上型電腦一樣準確。透過行動通訊基地台的連線可能較不準確，因為訪客的 IP 位址是以接收訊號的基地台為準。使用[Geolocation API](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation_API)可解決某些行動地理位置問題。

**地理功能如何處理來自 AOL 的訪客?**

由於 AOL 使用代理伺服器處理流量的方式之故，我們只能夠在國家/地區層級上鎖定目標。所以，舉例來說，鎖定法國為目標的行銷活動就會成功鎖定法國的 AOL 使用者為目標。但是定位至巴黎的促銷活動，便無法成功定位巴黎的 AOL 使用者。如果您希望特別定位 AOL 使用者，則您可以將區域欄位設定為「aol」。事實上，您可以指定兩個定位條件來定位美國的 AOL 使用者國家完全符合「美國」，而地區完全符合「aol」。

**地理鎖定目標提供的位置精度如何?**

* 國家/地區 - 全球
* 州/省/區域 - 全球
* 城市 - 全球
* 郵遞區號 - 美國、德國、加拿大
* DMA/ITV (英國) - 美國、英國
* 行動電信業者 - 全球

**如何以來自不同位置的使用者身分來測試我的活動?**

您可以用不同位置的 IP 位址來覆寫您的 IP 位址，然後使用 `mboxOverride.browserIp url` 參數。所以，如果貴公司位於英國，但您的全球促銷活動目標訪客位在紐西蘭的奧克蘭，則您可以使用這種 URL，假設 `60.234.0.39` 是奧克蘭境內的 IP 位址:

`https://www.mycompany.com?mboxOverride.browserIp=60.234.0.39`

在這樣做之前，您需要先清除 Cookie。

>[!NOTE]
>
>`mboxOverride.browserIp` is supported in at.js 1.** jxonly.at.js 2不支援此功能。*x* 版本不支援此函數。

**波多黎各和香港等地區要如何對應至地理鎖定目標結構?**

波多黎各、香港和其他地區視同個別的「國家/地區」值。

**當活 [!DNL Target] 動以地理位置定位功能定位時，是否會擷取（並儲存）郵遞區號等資訊？**

否，[!DNL Target]僅使用作業期間的地理資料，則會捨棄資料。

## 訓練影片：建立觀眾![教學課程標章](/help/assets/tutorial.png)

此影片包括關於使用對象類別的資訊。

* 建立對象
* 定義對象類別

>[!VIDEO](https://video.tv.adobe.com/v/17392)
