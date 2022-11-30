---
keywords: 鎖定目標;a4t;地理;地理鎖定目標;地理鎖定目標準確度;國家;州;城市;郵遞區號;dma;行動電信業者;城市碼;區域碼;都市碼;設定檔指令碼;地理鎖定目標設定檔指令碼;地理鎖定目標行動
description: 了解如何在 [!DNL Adobe Target] 依據使用者的地理位置來鎖定使用者。
title: 我可以根據位置定位訪客嗎？
feature: Audiences
solution: Target,Analytics
exl-id: e4a71a4d-e8f3-4f94-a1a7-fd250f4d5095
source-git-commit: 195028613dec0294c816703b9145e720e3209d74
workflow-type: tm+mt
source-wordcount: '1041'
ht-degree: 41%

---

# 地理

在中使用對象 [!DNL Adobe Target] 依據使用者的地理位置來鎖定使用者。

地理位置參數可讓您根據訪客的地理位置來定位活動和體驗。 您可以根據國家、州/省、城市、郵遞區號、緯度、經度、DMA 或行動電信業者來包含或排除訪客。此資料會與每個 [!DNL Target] 請求，且會根據訪客的IP位址。 選取這些參數就像任何定位值一樣。

## 使用地理定位建立對象 {#section_49CBFFAAC8694C4AAD3DE4B2DB7B05DE}

1. 在 [!DNL Target] 介面中，按一下&#x200B;**[!UICONTROL 「對象」]**>**[!UICONTROL 「建立對象」]**。
1. 為對象命名並新增選用說明。
1. 拖放 **[!UICONTROL 地理]** 進入audience builder窗格。

1. 按一下&#x200B;**[!UICONTROL 「選取」]**，然後選取下列其中一個選項:

   * [!UICONTROL 國家/地區]
   * [!UICONTROL 狀態]
   * [!UICONTROL 城市]
   * [!UICONTROL 郵遞區號]
   * [!UICONTROL 經度]
   * [!UICONTROL 緯度]
   * [!UICONTROL DMA]
   * [!UICONTROL 行動電信業者]

   訪客的地理資訊由 [!DNL Target] 位置要求（mbox要求）。 新工作階段的首次呼叫會完成IP對地理的解析。 這表示，如果訪客的IP位址在造訪的工作階段中途變更，地理資訊仍會以第一次呼叫的IP位址為基礎。

   針對 [!UICONTROL 行動電信業者], [!DNL Target] 使用IP位址註冊資料（擁有IP位址區塊）來判斷適當的行動電信業者，使用 [行動裝置國碼(MCC)和行動網路碼(MNC)](https://www.mcc-mnc.com).

1. 指定運算子和適當的值。
1. （選用）為對象設定其他規則。
1. 按一下&#x200B;**[!UICONTROL 「完成」]**。

下圖顯示的受眾鎖定從緯度大於44°且經度小於22°存取活動的使用者。

![target_geo影像](assets/target_geo.png)

## 準確度 {#section_D63D5FFCB49C42F9933AFD0BD7C79DF1}

地理鎖定目標的準確度取決於幾項因素。WiFi 連線比行動電話通訊網路更準確。當訪客使用行動資料連線時，地理查閱的準確度會受位置、提供者與 [DeviceAtlas](https://deviceatlas.com/device-data/user-agent-tester)，以及其他因素。 行動通訊基地台網路連線可能比有線或 WiFi 連線更不準確。此外，訪客的IP位址可能對應至訪客的ISP位置，而這可能與訪客的實際位置不同。 某些行動地理位置問題可使用 [地理位置API](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation_API).

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

## 使用地理定位值做為Token {#section_E7F7FDF62C3B4934A6565D04B24655F6}

您可以使用 `profile.geolocation` 值會直接做為選件、外掛程式等中的Token。

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

下列是關於地理定位的常見問題：

### 如何指定緯度和經度?

+++查看詳細資訊
* 經緯度的值應為數值（以度為單位）。
* 經緯度的值最多可以有五位小數的精確度。
* 緯度的值應該介於 -90 和 90 之間。
* 經度的值應該介於 -180 和 180 之間。

+++

### 行動裝置的地理定位如何運作？

+++請參閱詳細資訊大部分行動裝置使用者透過WiFi存取內容，這表示 [!DNL Target]的IP型地理定位與案頭一樣準確。 透過行動通訊基地台的連線可能較不準確，因為訪客的 IP 位址是以接收訊號的基地台為準。某些行動地理位置問題可使用 [地理位置API](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation_API).

+++

### 地理功能如何處理來自 AOL 的訪客?

+++請參閱詳細資訊由於AOL代理其流量的方式， [!DNL Target] 只能在國家/地區層級定位。 例如，目標為法國的促銷活動成功鎖定了法國的AOL使用者。 但鎖定在巴黎的促銷活動並未成功鎖定巴黎的AOL使用者。 如果您希望特別定位 AOL 使用者，則您可以將區域欄位設定為「aol」。事實上，您可以指定兩個定位條件來定位美國的 AOL 使用者國家完全符合「美國」，而地區完全符合「aol」。

+++

### 地理定位提供的位置精細度為何？

+++查看詳細資訊
* 國家/地區 - 全球
* 州/省/區域 - 全球
* 城市 - 全球
* 郵遞區號 - 美國、德國、加拿大
* DMA/ITV (英國) - 美國、英國
* 行動電信業者 - 全球

+++

### 如何以來自不同位置的使用者身分來測試我的活動?

+++查看詳細資訊
* **at.js 1.*x***:您可以使用不同位置的IP位址來覆寫您的IP位址，並使用 `mboxOverride.browserIp url` 參數。 例如，如果貴公司位於英國，但您的全域促銷活動目標訪客位在紐西蘭的奧克蘭，則請使用此URL，假設 `60.234.0.39` 是奧克蘭境內的IP位址：

   `https://www.mycompany.com?mboxOverride.browserIp=60.234.0.39`

   先清除Cookie再測試活動。

   >[!NOTE]
   >
   >`mboxOverride.browserIp` at.js 1支援。*x* 版。at.js 2不支援此功能。*x*。

* **at.js 2.*x***:使用at.js 2覆寫您的IP位址。*x*，安裝瀏覽器擴充功能/外掛程式（例如Chrome或Firefox專用的X-Forwarded-For Header）。 此擴充功能可讓您在頁面要求中傳遞x-forwarded-for標題。

+++

### 波多黎各和香港等地區要如何對應至地理鎖定目標結構?

+++請參閱詳細資訊，波多黎各、香港和其他地區會被視為個別的「國家/地區」值。

+++

### 是 [!DNL Target] 使用地理位置定位功能定位活動時擷取（並儲存）郵遞區號等資訊？

+++詳情請參閱否、 [!DNL Target] 僅在工作階段期間使用地理資料，則會捨棄資料。

+++

## 訓練影片：建立對象 ![教學課程徽章](/help/main/assets/tutorial.png)

此影片包括關於使用對象類別的資訊。

* 建立對象
* 定義對象類別

>[!VIDEO](https://video.tv.adobe.com/v/17392)
