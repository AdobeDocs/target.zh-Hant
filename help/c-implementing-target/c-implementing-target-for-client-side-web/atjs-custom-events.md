---
keywords: 自訂事件;at.js;要求失敗;要求成功;內容呈現失敗;內容呈現成功;資料庫已載入;要求開始;內容呈現開始;內容呈現無選件;內容呈現重新導向
description: 使用Adobe Target at.js JavaScript程式庫的自訂事件，在mbox請求或選件失敗或成功時收到通知。
title: 如何使用at.js自訂事件？
feature: at.js
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '619'
ht-degree: 92%

---


# at.js 自訂事件

關於 `at.js custom events` 的資訊，可讓您知道 mbox 要求或選件失敗或成功的時間。

在過去，mbox.js 不會讓頁面上執行的其他 JavaScript 程式碼知道背景中進行的動作。利用提升的 at.js，我們有一個獨特的機會可修正此問題。

根據我們的客戶，客戶想要收到數個案例的通知，其中包括:

* mbox 要求由於逾時、錯誤的狀態代碼、JSON 剖析錯誤等等失敗。
* mbox 要求成功。
* 由於遺漏包裝 mbox 元素、找不到選取器等等，選件呈現失敗。
* 選件呈現成功。DOM 變更已套用。

預先定義的事件具有可讓您根據事件類型，擷取需要資料的結構。

為了確定事件可以用在不同的案例，自訂事件具有已指派給事件物件 (傳遞至處理常式) 之承載物件的詳細資料屬性。同時為了避免以事件名稱的形式傳遞字串，事件會使用 `adobe.target.event` 名稱空間以常數形式公開。

## 結構 {#section_0E5C9A13DE234A5DAECBCBF9F23F94FE}

| 機碼 | 類型 | 說明 |
|--- |--- |--- |
| type | 字串 | 有數個案例通知能夠協助您追蹤、偵錯和自訂與 at.js 的互動。<br>以下所列的每個自訂事件有兩個格式:「常數」和「字串值」。<ul><li>**常數:** 在前端加上 `adobe.target.event.`，以全大寫呈現，並包含底線字元。若要在 at.js 載入&#x200B;*之後*&#x200B;但在收到 mbox 回應&#x200B;*之前*&#x200B;訂閱自訂事件，請使用常數。</li><li>**字串值:** 小寫並包含破折號。若要在 at.js 載入&#x200B;*之前*&#x200B;訂閱自訂事件，請使用字串值。</li></ul>**要求失敗**<br>&#x200B;常數：`adobe.target.event.REQUEST_FAILED`<br>字串值：`at-request-failed`<br>說明：由於逾時、錯誤狀態碼、JSON剖析錯誤等原因，mbox請求失敗。<br>**要求成功**<br>&#x200B;常數: `adobe.target.event.REQUEST_SUCCEEDED`<br>字串值: `at-request-succeeded`<br>說明: mbox 要求成功。<br>**內容呈現失敗**<br>&#x200B;常數: `adobe.target.event.CONTENT_RENDERING_FAILED`<br>字串值: `at-content-rendering-failed`<br>說明: 由於遺漏包裝 mbox 元素、找不到選取器等原因，選件呈現失敗。<br>**內容呈現成功**<br>&#x200B;常數: `adobe.target.event.CONTENT_RENDERING_SUCCEEDED`<br>字串值: `at-content-rendering-succeeded`<br>說明: 選件呈現成功。DOM 變更已套用。<br>**資料庫已載入**<br>&#x200B;常數: `adobe.target.event.LIBRARY_LOADED`<br>字串值: `at-library-loaded`<br>說明: 此事件非常適合追蹤 at.js 已完整載入的時間。您可以使用此事件來自訂全域 mbox 執行。您也可以使用此事件來停用全域 mbox，然後稍後接聽此事件來觸發全域 mbox。<br>**要求開始**<br>&#x200B;常數: `adobe.target.event.REQUEST_START`<br>字串值: `at-request-start`<br>說明: 此事件是在 HTTP 要求執行之前觸發。您可以對使用資源計時 API 進行的效能測量使用此事件。<br>**內容呈現開始**<br>&#x200B;常數: `adobe.target.event.CONTENT_RENDERING_START`<br>字串值: `at-content-rendering-start`<br>說明: 此事件是在選取器輪詢開始和內容呈現至頁面之前觸發。您可以使用此事件來追蹤內容呈現進度。<br>**內容呈現無選件**<br>&#x200B;常數: `adobe.target.event.CONTENT_RENDERING_NO_OFFERS`<br>字串值: `at-content-rendering-no-offers`<br>說明: 此事件是在沒有傳回任何選件時觸發。<br>**內容呈現重新導向**<br>&#x200B;常數: `adobe.target.event.CONTENT_RENDERING_REDIRECT`<br>字串值: `at-content-rendering-redirect`<br>說明: 當選件為重新導向，且 Target 將重新導向至不同 URL 時，會觸發此事件。 |
| mbox | 字串 | mBox 名稱 |
| 訊息 | 字串 | 包含人類可讀說明，例如發生了什麼、錯誤訊息等等。 |
| 追蹤 | 物件 | 包含 `sessionId` 和 `deviceId`。在部分情況下，可以遺漏 `deviceId`，因為 [!DNL Target] 無法從 Edge 伺服器擷取它。 |

## 使用狀況 {#section_0500FF09D3A04450B5DC8F85C6F793E0}

```javascript
document.addEventListener(adobe.target.event.REQUEST_SUCCEEDED, function(event) { 
  console.log('Event', event); 
});
```

## 訓練影片: 回應 Token 和 at.js 自訂事件 ![教學課程徽章](/help/assets/tutorial.png) {#section_ED304A7137DC42A4BDCD6D57C989F1FA}

觀看以下影片，瞭解如何使用回應 Token 和 at.js 自訂事件，共用從 Target 到協力廠商系統的設定檔資訊。

>[!VIDEO](https://video.tv.adobe.com/v/23253/)