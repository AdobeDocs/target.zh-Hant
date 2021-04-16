---
keywords: 實施；javascript library;js;atjs；裝置上決策；裝置上決策；支援的功能
description: 瞭解裝置上決策支援哪些功能。
title: 裝置上決策支援哪些功能
feature: at.js
role: Developer
exl-id: 3531ff55-c3db-44c1-8d0a-d7ec2ccb6505
translation-type: tm+mt
source-git-commit: 62a3b387445977a1bdcd2cf45306c8ff032fca50
workflow-type: tm+mt
source-wordcount: '461'
ht-degree: 11%

---

# 支援的裝置上決策功能

[!DNL Adobe Target] JS SDK讓客戶可以靈活選擇決策資料的效能與新鮮度。 換言之，如果透過機器學習提供最相關、最吸引人的個人化內容對您而言最為重要，則應進行即時伺服器呼叫。 但是，當效能更為關鍵時，應該做出設備內和記憶體內決策。 如需裝置上決策的運作，請參閱下列列出支援功能的章節。

## 支援的活動類型

下表指出裝置上決策支援或不支援哪些[活動類型](/help/c-activities/target-activities-guide.md)由[表單型Experience Composer](/help/c-experiences/form-experience-composer.md)或[ Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md)(VEC)建立的活動類型。

| 活動類型 | 支援? |
| --- | --- |
| [A/B 測試](/help/c-activities/t-test-ab/test-ab.md) | 是 |
| [自動分配](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | 無 |
| [自動鎖定目標](/help/c-activities/auto-target/auto-target-to-optimize.md) ![Premium](/help/assets/premium.png) | 無 |
| [多變數測試](/help/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) | 無 |
| [](/help/c-activities/t-experience-target/experience-target.md)體驗鎖定目標 (XT) | 是 |
| [Automated ](/help/c-activities/t-automated-personalization/automated-personalization.md) ![PersonalizationPremium](/help/assets/premium.png) | 無 |
| [](/help/c-recommendations/recommendations.md) ![RecommendationsPremium](/help/assets/premium.png) | 無 |
| [使用Analytics for Target](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T)的活動 | 是 |

## 目標受眾

下表指出裝置上決策支援或不支援哪些觀眾規則。

| 對象規則 | 支援? |
| --- | --- |
| [地理](/help/c-target/c-audiences/c-target-rules/geo.md) | 是 |
| [網路](/help/c-target/c-audiences/c-target-rules/network.md) | 無 |
| [行動](/help/c-target/c-audiences/c-target-rules/mobile.md) | 無 |
| [自訂參數](/help/c-target/c-audiences/c-target-rules/custom-parameters.md) | 是 |
| [作業系統 ](/help/c-target/c-audiences/c-target-rules/operating-system.md) | 是 |
| [網頁](/help/c-target/c-audiences/c-target-rules/site-pages.md) | 是 |
| [瀏覽器](/help/c-target/c-audiences/c-target-rules/browser.md) | 是 |
| [訪客資料](/help/c-target/c-audiences/c-target-rules/visitor-profile.md) | 無 |
| [流量來源](/help/c-target/c-audiences/c-target-rules/traffic-sources.md) | 無 |
| [時間範圍](/help/c-target/c-audiences/c-target-rules/time-frame.md) | 是 |
| Adobe Experience Cloud觀眾<br>([!DNL Adobe Analytics]、[!DNL Adobe Audience Manager]和[!DNL Adobe Experience Manager]的觀眾 | 無 |

### 裝置上決策的地理定位

為維持裝置上決策活動與地理對象之間的最低延遲，Adobe建議您在呼叫[getOffers](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md)時自行提供地理值。 在請求的「內容」中設定Geo物件。 這表示從瀏覽器，可判斷每個訪客的位置。 例如，您可以使用您設定的服務，執行IP對地理的查閱。 有些代管提供者（例如Google Cloud）會透過每個`HttpServletRequest`中的自訂標題提供此功能。

```javascript
window.adobe.target.getOffers({ 
	decisioningMethod: "on-device", 
	request: { 
		context: { 
			geo: { 
				city: "SAN FRANCISCO", 
				countryCode: "US", 
				stateCode: "CA", 
				latitude: 37.75, 
				longitude: -122.4 
			} 
		}, 
		execute: { 
			pageLoad: {} 
		} 
	} 
})
```

不過，如果您無法在伺服器上執行IP對地理位置的查詢，但您仍想對包含地理對象的[getOffers](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md)請求執行裝置上決策，則也支援此功能。 此方法的缺點是使用遠端IP到地理查閱，這會增加每個`getOffers`呼叫的延遲。 此延遲應低於伺服器端決策的`getOffers`呼叫，因為它會點擊靠近您伺服器的CDN。 請求SDK擷取訪客IP位址的地理位置時，請僅提供Geo物件中的「ipAddress」欄位。 如果除了「ipAddress」外，還有其他欄位，[!DNL Target] SDK將不會擷取地理位置中繼資料以進行解析。

```javascript
window.adobe.target.getOffers({ 
	decisioningMethod: "on-device", 
	request: { 
		context: { 
			geo: { 
				ipAddress: "127.0.0.1" 
			} 
		}, 
		execute: { 
			pageLoad: {} 
		} 
	} 
})
```

### 分配方法

下表指出裝置上決策支援或不支援哪些配置方法。

| 分配方法 | 支援? |
| --- | --- |
| 手動 | 是 |
| [自動分配以獲得最佳體驗](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | 無 |
| [自動鎖定個人化體驗](/help/c-activities/auto-target/auto-target-to-optimize.md) | 無 |
