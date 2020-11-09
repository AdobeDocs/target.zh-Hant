---
keywords: debug mbox;troubleshoot mbox;mbox issues;flicker;mboxDebug;mboxTrace;token;debugger;priority;activity priority;Adobe Experience Cloud Debugger;orderConfirmPage mbox;SiteCatalyst  purchase mbox;top selling;top seller
description: 如果您的頁面未顯示預期的內容，您可以執行一些步驟，以在Adobe Target中除錯內容傳送。
title: 疑難排解Adobe Target中的內容傳送
feature: activities
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '1386'
ht-degree: 60%

---


# 疑難排解內容傳送{#troubleshoot-content-delivery}

如果頁面未顯示預期的內容，您應執行一些步驟來除錯內容傳送。

* 請仔細檢查您的活動或促銷活動程式碼。錯字或其他錯誤都可能導致預期的內容無法顯示。
* Use mboxTrace or mboxDebug to troubleshoot the [!DNL Target] request.
* Use the Adobe Experience Cloud Debugger, an easy-to-use tool that provides much of the same information as mboxDebug, to troubleshoot the [!DNL Target] request.

mboxDebug is especially useful when you are setting up [!DNL Target] on your page to make sure the [!DNL Target] request is firing and the cookie is being set. 但是，這不會深入到偵錯內容傳送時很有用的詳細程度。如果您的活動未顯示在頁面上，或是顯示不想要的內容，請使用 mboxTrace 來詳細檢查和偵錯頁面。

## Retrieve the authorization token to use with debugging tools {#section_BED130298E794D1FA229DB7C3358BA54}

由於 mboxTrace 和 mboxDebug 會公開促銷活動資料和描述檔資料給外部對象，因此需要授權權仗。在[!DNL Target]UI 中可以擷取授權 Token。授權 Token 的有效期限為六小時。

您必須具備下列其中一個使用者權限才能產生驗證Token:

* 至少 [!UICONTROL 是Editor] (或 [!UICONTROL Approver])權限

   如需客戶的詳細資 [!DNL Target Standard] 訊，請參 [閱「指定使用者中的角色和](/help/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions) 權限」 **。 如需客戶的詳細資 [!DNL Target Premium] 訊，請參 [閱設定企業權限](/help/administrating-target/c-user-management/property-channel/properties-overview.md)。

* 工作區／產品設定檔層級上的管理員角色

   工作區僅供客 [!DNL Target Premium] 戶使用。 For more information, see [Configure enterprise permissions](/help/administrating-target/c-user-management/property-channel/properties-overview.md).

* 產品層級的管理權限(Sysadmin權 [!DNL Adobe Target] 限)

擷取授權 Token:

1. 按一 **[!UICONTROL 下「管理]** >實 **[!UICONTROL 施」]**。
1. 在「除錯工具」區段中，按一下「 **[!UICONTROL 產生新驗證Token]**」。

   ![產生新的驗證Token](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/assets/debugger-auth-token.png)

1. 將產生的 Token 當作參數新增至 URL，以啟用其中一個進階偵錯工具。

   ![授權 Token](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/assets/auth-token.png)

## mboxTrace {#section_256FCF7C14BB435BA2C68049EF0BA99E}

mboxTrace enables you to receive trace information attached to [!DNL Target] responses. Trace information reflects the outcome of a [!DNL Target] call (for example, a conversion or an impression) and any additional data that may help in determining why this particular outcome happened, such as a set of available branches among which the selection was made in a campaign. 請使用此資訊來對內容傳送除錯。

以下是可用的參數:

| mboxTrace 選項 | 結果 |
|--- |--- |
| `?mboxTrace=console` | 列印至控制台記錄做為物件。<br>針對 at.js，不使用彈出新瀏覽器視窗或輸出至控制台的 mbox.js 中，您需檢查網路請求並查看「預覽」(Chrome) 或「回應」(Firefox)。 |
| `?mboxTrace=json` | 列印至控制台記錄做為常值 JSON 字串 |
| `?mboxTrace=window` | 列印至彈出式視窗做為 JSON 字串 |
| `?mboxTrace=disable` | 關閉追蹤作業模式 |

**範例mboxTrace呼叫**

`https://www.mysite.com/page.html?mboxTrace=window&authorization=f543abf-0111-4061-9619-d41d665c59a6`

輸出會顯示與內容相關的極詳細資訊。mboxTrace 會顯示與您促銷活動或活動以及描述檔相關的詳細資訊，也會提供執行前的描述檔快照，以及執行後的變更項目快照。同時顯示每個位置評估了哪些促銷活動或活動。

有些資訊包括相符和不相符的群體與目標 ID:

* **SegmentId**: 群體的 ID，來自可重複使用的群體庫或為特定促銷活動建立的匿名群體。
* **TargetId**: 目標的 ID，來自目標運算式庫或來自促銷活動的匿名目標。
* **不相符**: 請求在此呼叫中不符合那些群體或目標的資格。
* **相符**: 請求符合指定的群體或目標的資格。

**在建議頁面上使用mboxTrace**:將mboxTrace新增為含建議之頁面上的查詢參數，會以mboxTrace詳細資料視窗取代頁面上的Recommendations設計，此視窗會顯示建議的深入資訊，包括：

* 傳回的建議以較請求的建議
* 使用的索引鍵，以及是否產生建議
* 條件產生的建議比較備份建議
* 條件組態
* 套用的排除和包含
* 收集規則

您不需要在查詢參數中加入`=console`、`=json` 或 `=window`。使用完 mboxTrace 詳細資料後，請新增 `=disable`，然後按下 **[!UICONTROL Enter]** 鍵，即可返回正常顯示模式。

mboxTrace 不會影響您網站的正常功能和外觀。訪客看到的是您的正常 Recommendations 設計。

## mboxDebug {#mboxdebug}

若要使用 mboxDebug，請附加 mboxDebug 參數至 URL 結尾。The following table contains information about [!DNL Target] response-related URL parameters.

>[!NOTE]
>
>有些 mboxDebug 參數可以不使用驗證。

| URL 參數 | 用途 |
|--- |--- |
| `mboxDebug=1` | Debugger<br>Adding this parameter to any URL with Target requests defined opens a pop-up window with valuable debugging details. Cookie 資訊、PCid 及作業 ID 值會出現，而且所有的 URL 都會顯示。Click on a Target request URL to show the response for that [!DNL Target] request. 如需詳細資訊，請參閱 [mbox_debug.pdf](/help/assets/mbox_debug.pdf)。 |
| `mboxDebug=x-cookie` | 修改 Cookie |
| `mboxDisable=1` | 停用頁面上的 mbox |
| `mboxDebug=x-profile` | 檢視描述檔集合。 |
| `mboxDebug=x-time` | Show response time for each [!DNL Target] request |
| `mboxOverride.browserIp=<Insert IP address>` | 測試地理定位<br>使用這個 URL 參數測試地理定位。輸入 IP 位址作為這個屬性的值，Test&amp;Target 的地理定位功能會評估該 IP 位址，以比對促銷活動中設定的任何定位與群體劃分。 |

>[!NOTE]
>
>請確定URL片段位於查詢字串參數之後。 第一個後面的任 `#` 何項目都是片段識別碼，導致除錯參數無法正常運作。

## Adobe Experience Cloud Debugger {#section_A2798ED3A431409690A4BE08A1BFCF17}

Adobe Experience Cloud Debugger 方便您快速且輕鬆地瞭解 Target 實作。您可以快速查看資料庫組態、檢查要求以確定您的自訂參數傳遞正確、開啟主控台記錄功能，以及停用所有 Target 要求。驗證至Experience Cloud，您可以使用功能強大的MboxTrace工具來檢查您的活動、受眾資格以及訪客資料。

如需詳細資訊，請觀看下方的訓練影片:

如需詳細資訊，請 [參閱使用Adobe Experience Cloud除錯程式除錯at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-debugging-atjs/target-debugging-atjs.md)。

## 如果在傳送期間 target.js 無法載入 {#section_ABBA5EFDFFB749D8BEE172DB1F973058}

如果在傳送期間 target.js 無法載入，mbox.js 會將 Cookie「em-disabled」傳送給訪客。此 Cookie 可避免使用 Visual Experience Composer 建立的選件在網站上轉譯。具有此 Cookie 的訪客看不到測試內容，也不會算入那些活動報表中。所有其他選件內容 (例如來自 Target Classic 的促銷活動) 會繼續載入。Cookie 從載入失敗起的存留期為 30 分鐘。

## 最暢銷商品未出現在建議中 {#section_3920C857270A406C80BE6CBAC8221ECD}

The *`SiteCatalyst: purchase`* call can&#39;t be used for Purchase algorithm traffic data. 請改用 *`orderConfirmPage`* 呼叫。

## Check activity priority {#section_3D0DD07240F0465BAF655D0804100AED}

Form-based activities created with [!DNL Target Standard/Premium] might collide with activities created in the [!DNL Target Classic] UI that have the same priority and use the same [!DNL Target] request.

## 自訂程式碼在 Internet Explorer 8 中未產生預期結果。{#section_FAC3651F19144D12A37A3E4F14C06945}

Target 不再支援 IE 8。

## JavaScript content delivered by the global [!DNL Target] request doesn&#39;t load when using mbox.js. {#section_03EC9B9C410B4F52A7FCD81840311709}

升級至 [!DNL mbox.js] 版本 58 或更新版。

mbox.js version 58 and later executes non-JavaScript content for the global [!DNL Target] request immediately after the HTML `BODY` tag is present. JavaScript content inside `<script>` tags for the global [!DNL Target] request executes after the `DOMContentLoaded` event is fired. This order of content delivery ensures that JavaScript content for the global [!DNL Target] request is delivered and rendered properly.

## Target cookie does not get set {#section_77AFEB541C0B495EB67E29A4475DF960}

如果您的網站有子網域，例如 [!DNL us.domain.com]，但您需要將 Target Cookie 設定在 [!DNL domain.com] (而不是 [!DNL us.domain.com])，則必須覆寫 `cookieDomain` 設定。如需詳細資訊，請參閱 [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md)。

## 如果元素也是 AEM 個人化的一部分，Target 內容會忽隱勿現或未出現。{#section_9E1DABEB75AB431FB9F09887E6DD07D3}

如果 DOM 元素 Adobe Experience Manager (AEM) 個人化目標鎖定和 Target 活動的一部分，Target 內容可能會忽隱忽現或沒有出現。

若要補救這種情況，您可以在執行 Target 的頁面上停用 AEM 個人化。

## 無效 URL 導致重新導向與遠端選件無法傳送。 {#section_7D09043B687F43B39DAEDF17D00375AC}

如果重新導向與遠端選件使用無效的 URL，可能會無法傳送。

For redirect offers, the [!DNL Target] response can contain `/* invalid redirect offer URL */`

或

For remote offers, the [!DNL Target] response can contain `/* invalid remote offer URL */`

You can check the [!DNL Target] response in the browser or using mboxTrace. 請參閱 [https://tools.ietf.org/html/std66](https://tools.ietf.org/html/std66) 以取得有效 URL 的詳細資訊。

## 我的網站上未觸發目標請求。

如果您使用無效的doctype,at.js不會觸發Target請求。 at.js 需要 HTML 5 doctype。

## 訓練影片

以下影片含有本文章探討之概念的詳細資訊。

### 新增擴充功能 ![教學課程徽章](/help/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/23114t2/)

### 基本目標除錯教 ![學課程徽章](/help/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/23115t2/)

### Mbox追蹤教 ![學課程徽章](/help/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/23113t2/)