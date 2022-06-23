---
keywords: 實現；javascript library;js;atjs；設備上決策；設備上決策；支援的功能
description: 瞭解設備上決策支援哪些功能。
title: 設備上決策支援哪些功能
feature: at.js
role: Developer
exl-id: 3531ff55-c3db-44c1-8d0a-d7ec2ccb6505
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 13%

---

# 裝置上決策的支援功能

的 [!DNL Adobe Target] JS SDK使客戶能夠靈活地在效能和資料新鮮度之間進行選擇，以便做出決策。 換句話說，如果通過機器學習交付最相關和最吸引人的個性化內容對您來說最為重要，則應進行即時伺服器呼叫。 但是，當效能更為關鍵時，應該做出設備內和記憶體內決策。 要使設備上的決策工作正常，請參閱以下列出支援的功能的部分。

## 支援的活動類型

下表指明了 [活動類型](/help/main/c-activities/target-activities-guide.md) 建立者 [基於表單的體驗作曲家](/help/main/c-experiences/form-experience-composer.md) 或 [視覺體驗作曲家](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) 設備上的決策支援或不支援(VEC)。

| 活動類型 | 支援? |
| --- | --- |
| [A/B 測試](/help/main/c-activities/t-test-ab/test-ab.md) | 是 |
| [自動分配](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | 無 |
| [自動鎖定目標](/help/main/c-activities/auto-target/auto-target-to-optimize.md) ![Premium](/help/main/assets/premium.png) | 否 |
| [多變數測試](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) | 否 |
| [體驗鎖定](/help/main/c-activities/t-experience-target/experience-target.md) (XT) | 是 |
| [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) ![高級](/help/main/assets/premium.png) | 無 |
| [Recommendations](/help/main/c-recommendations/recommendations.md) ![高級](/help/main/assets/premium.png) | 否 |
| [使用目標分析的活動](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) | 是 |

## 目標受眾

下表指明了設備上決策支援或不支援哪些訪問群體規則。

| 受眾規則 | 支援? |
| --- | --- |
| [地理](/help/main/c-target/c-audiences/c-target-rules/geo.md) | 是 |
| [網路](/help/main/c-target/c-audiences/c-target-rules/network.md) | 否 |
| [行動](/help/main/c-target/c-audiences/c-target-rules/mobile.md) | 否 |
| [自訂參數](/help/main/c-target/c-audiences/c-target-rules/custom-parameters.md) | 是 |
| [作業系統 ](/help/main/c-target/c-audiences/c-target-rules/operating-system.md) | 是 |
| [網頁](/help/main/c-target/c-audiences/c-target-rules/site-pages.md) | 是 |
| [瀏覽器](/help/main/c-target/c-audiences/c-target-rules/browser.md) | 是 |
| [訪客資料](/help/main/c-target/c-audiences/c-target-rules/visitor-profile.md) | 否 |
| [流量來源](/help/main/c-target/c-audiences/c-target-rules/traffic-sources.md) | 否 |
| [時間範圍](/help/main/c-target/c-audiences/c-target-rules/time-frame.md) | 是 |
| Adobe Experience Cloud觀眾<br>(來自 [!DNL Adobe Analytics]。 [!DNL Adobe Audience Manager], [!DNL Adobe Experience Manager] | 否 |

### 用於設備上決策的地理定位

為使基於地域的受眾在設備上決策活動的延遲保持最小，Adobe建議您在呼叫中提供自己的地理值 [get優惠](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-getoffers-atjs-2/)。 在請求的上下文中設定Geo對象。 這意味著從瀏覽器中確定每個訪問者的位置。 例如，您可以使用您配置的服務執行IP到Geo查找。 某些主機提供商(如Google雲)通過每個主機中的自定義標頭提供此功能 `HttpServletRequest`。

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

但是，如果您無法在伺服器上執行IP到Geo查找，但您仍希望對 [get優惠](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-getoffers-atjs-2/) 包含基於地域的受眾的請求，也支援此功能。 此方法的缺點是它使用遠程IP到Geo查找，這會增加每個查找的延遲 `getOffers` 呼叫。 此延遲應低於 `getOffers` 通過伺服器端決策調用，因為它命中了靠近伺服器的CDN。 請求SDK檢索訪問者IP地址的地理位置時，請僅提供Geo對象中的「ipAddress」欄位。 如果除「ipAddress」之外還提供了其他欄位， [!DNL Target] SDK將不提取用於解析的地理位置元資料。

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

下表指明了設備上決策支援或不支援哪些分配方法。

| 分配方法 | 支援? |
| --- | --- |
| 手動 | 是 |
| [自動分配以獲得最佳體驗](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | 否 |
| [個性化體驗的自動目標](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | 否 |
