---
keywords: 偵錯 mbox;疑難排解 mbox;mbox 問題;閃現;mboxDebug;mboxTrace;權杖;偵錯工具;優先順序;活動優先順序;Adobe Experience Cloud 偵錯工具;orderConfirmPage mbox;SiteCatalyst 購買 mbox;熱賣;最暢銷商品
description: 尋找建議來幫助解決如果頁面未顯示預期內容的問題。學習如何在 Adobe Target 中偵錯內容傳送。
title: 如何疑難排解內容傳送問題？
feature: 活動
exl-id: 887b7956-1d61-439a-8339-c150deb9a378
translation-type: tm+mt
source-git-commit: cb42be6b0791711d3a9ddf5680cf6d6e32045579
workflow-type: tm+mt
source-wordcount: '1415'
ht-degree: 99%

---

# 疑難排解內容傳送

如果頁面未顯示預期的內容，您應執行一些步驟來除錯內容傳送。

* 請仔細檢查您的活動或促銷活動程式碼。錯字或其他錯誤都可能導致預期的內容無法顯示。
* 使用 mboxTrace 或 mboxDebug 來針對 [!DNL Target] 請求進行疑難排解。
* 使用 Adobe Experience Cloud Debugger，與 mboxDebug 提供的資訊大多相同的易用工具，來針對 [!DNL Target] 請求進行疑難排解。

如果您在頁面上設定 [!DNL Target] 以確保引發 [!DNL Target] 以及設定 Cookie，mboxDebug 會很有用。但是，這不會深入到偵錯內容傳送時很有用的詳細程度。如果您的活動未顯示在頁面上，或是顯示不想要的內容，請使用 mboxTrace 來詳細檢查和偵錯頁面。

## 擷取授權權杖以與偵錯工具一起使用 {#section_BED130298E794D1FA229DB7C3358BA54}

由於 mboxTrace 和 mboxDebug 會公開促銷活動資料和描述檔資料給外部對象，因此需要授權權仗。在[!DNL Target]UI 中可以擷取授權 Token。權杖的有效期限為六小時。

您必須具備下列其中一個使用者權限才能產生驗證權杖：

* 至少有 [!UICONTROL 編輯者]權限 (或[!UICONTROL 核准者]權限)

   如需有關 [!DNL Target Standard] 客戶的詳細資訊，請參閱&#x200B;*使用者*&#x200B;中的[指定角色與權限](/help/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions)。如需有關 [!DNL Target Premium] 客戶的詳細資訊，請參閱[設定企業權限](/help/administrating-target/c-user-management/property-channel/properties-overview.md)。

* 工作區/產品設定檔層級的管理員角色

   工作區僅適用於 [!DNL Target Premium] 客戶。如需詳細資訊，請參閱[企業使用者權限](/help/administrating-target/c-user-management/property-channel/properties-overview.md)。

* [!DNL Adobe Target] 產品層級的管理員權限 (Sysadmin 權限)

擷取授權權杖：

1. 按一下「**[!UICONTROL 管理]** > 「**[!UICONTROL 實施]**」。
1. 在「偵錯工具」區段中，按一下「**[!UICONTROL 產生新驗證權杖]**」。

   ![產生新驗證權杖](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/assets/debugger-auth-token.png)

1. 將產生的 Token 當作參數新增至 URL，以啟用其中一個進階偵錯工具。

   ![授權 Token](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/assets/auth-token.png)

## mboxTrace {#section_256FCF7C14BB435BA2C68049EF0BA99E}

mboxTrace 可讓您接收附加至 [!DNL Target] 回應的追蹤資訊。追蹤資訊可反映 [!DNL Target] 呼叫的結果 (例如，轉換或印象) 以及可協助判斷為何發生此特定結果的任何其他資料，例如在行銷活動中所進行選擇內的一組可用分支。請使用此資訊來對內容傳送除錯。

以下是可用的參數:

| mboxTrace 選項 | 結果 |
|--- |--- |
| `?mboxTrace=console` | 列印至控制台記錄做為物件。<br>針對 at.js，不使用彈出新瀏覽器視窗或輸出至控制台的 mbox.js 中，您需檢查網路請求並查看「預覽」(Chrome) 或「回應」(Firefox)。 |
| `?mboxTrace=json` | 列印至控制台記錄做為常值 JSON 字串 |
| `?mboxTrace=window` | 列印至彈出式視窗做為 JSON 字串 |
| `?mboxTrace=disable` | 關閉追蹤工作階段模式 |

**mboxTrace 呼叫範例**

`https://www.mysite.com/page.html?mboxTrace=window&authorization=f543abf-0111-4061-9619-d41d665c59a6`

輸出會顯示與內容相關的極詳細資訊。mboxTrace 會顯示與您促銷活動或活動以及描述檔相關的詳細資訊，也會提供執行前的描述檔快照，以及執行後的變更項目快照。同時顯示每個位置評估了哪些促銷活動或活動。

有些資訊包括相符和不相符的群體與目標 ID:

* **SegmentId**：群體的 ID，來自可重複使用的群體庫或為特定促銷活動建立的匿名群體。
* **TargetId**：目標的 ID，來自目標運算式庫或來自促銷活動的匿名目標。
* **不相符**：請求在此呼叫中不符合那些群體或目標的資格。
* **相符**：請求符合指定的群體或目標的資格。

**在 Recommendations 頁面上使用 mboxTrace**：使用 mboxTrace 詳細資料視窗，新增 mboxTrace 做為具有推薦之頁面上的查詢參數，以取代該頁面的 Recommendations 設計，此可顯示關於您建議的深入資訊，包括下列項目：

* 傳回的建議以較請求的建議
* 使用的索引鍵，以及是否產生建議
* 條件產生的建議比較備份建議
* 條件組態
* 套用的排除和包含
* 收集規則

您不需要在查詢參數中加入`=console`、`=json` 或 `=window`。使用完 mboxTrace 詳細資料後，請新增 `=disable`，然後按下 **[!UICONTROL Enter]** 鍵，即可返回正常顯示模式。

mboxTrace 不會影響您網站的正常功能和外觀。訪客看到的是您的正常 Recommendations 設計。

## mboxDebug {#mboxdebug}

若要使用 mboxDebug，請附加 mboxDebug 參數至 URL 結尾。下列表格含有與 [!DNL Target] 回應相關的 URL 參數的相關資訊。

>[!NOTE]
>
>有些 mboxDebug 參數可以不使用驗證。

| URL 參數 | 用途 |
|--- |--- |
| `mboxDebug=1` | 偵錯程式<br>將此參數新增至任何已定義 Target 請求的 URL 會開啟快顯視窗，其中含有重要的偵錯詳細資訊。Cookie 資訊、PCid 及工作階段 ID 值會出現，而且所有的 URL 都會顯示。按一下 Target 請求 URL 可顯示該 [!DNL Target] 請求的回應。如需詳細資訊，請參閱 [mbox_debug.pdf](/help/assets/mbox_debug.pdf)。 |
| `mboxDebug=x-cookie` | 修改 Cookie |
| `mboxDisable=1` | 停用頁面上的 mbox |
| `mboxDebug=x-profile` | 檢視描述檔集合。 |
| `mboxDebug=x-time` | 顯示每個 [!DNL Target] 請求的回應時間。 |
| `mboxOverride.browserIp=<Insert IP address>` | 測試地理定位<br>使用這個 URL 參數測試地理定位。輸入 IP 位址作為這個屬性的值，Test&amp;Target 的地理定位功能會評估該 IP 位址，以比對促銷活動中設定的任何定位與群體劃分。 |

>[!NOTE]
>
>確保 URL 片段位於查詢字串參數之後。第一個 `#` 之後的任何項目都是片段識別碼，導致偵錯程式參數無法正常運作。

## Adobe Experience Cloud Debugger {#section_A2798ED3A431409690A4BE08A1BFCF17}

Adobe Experience Cloud Debugger 方便您快速且輕鬆地瞭解 Target 實作。您可以快速查看資料庫組態、檢查要求以確定您的自訂參數傳遞正確、開啟主控台記錄功能，以及停用所有 Target 要求。只要驗證進入 Experience Cloud，您就可以利用功能強大的 MboxTrace 工具來檢查活動、對象資格以及訪客設定檔。

如需詳細資訊，請觀看下方的訓練影片：

如需詳細資訊，請參閱「[使用 Adobe Experience Cloud Debugger 偵錯 at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-debugging-atjs/target-debugging-atjs.md)」。

## 如果在傳送期間 target.js 無法載入 {#section_ABBA5EFDFFB749D8BEE172DB1F973058}

如果在傳送期間 target.js 無法載入，mbox.js 會將 Cookie「em-disabled」傳送給訪客。此 Cookie 可避免使用 Visual Experience Composer 建立的選件在網站上轉譯。具有此 Cookie 的訪客看不到測試內容，也不會算入那些活動報表中。所有其他選件內容 (例如來自 Target Classic 的促銷活動) 會繼續載入。Cookie 從載入失敗起的存留期為 30 分鐘。

## 最暢銷商品未出現在建議中  {#section_3920C857270A406C80BE6CBAC8221ECD}

*`SiteCatalyst: purchase`* 呼叫無法用於「購買」演算法流量資料。改為使用 *`orderConfirmPage`* 呼叫。

## 檢查活動優先順序 {#section_3D0DD07240F0465BAF655D0804100AED}

以 [!DNL Target Standard/Premium] 建立的表單式活動，可能與 [!DNL Target Classic] UI 中建立的活動發生衝突，兩者有相同的優先順序且使用相同的 [!DNL Target] 請求。

## 自訂程式碼在 Internet Explorer 8 中未產生預期結果。{#section_FAC3651F19144D12A37A3E4F14C06945}

Target 不再支援 IE 8。

## 使用 mbox.js 時全域 [!DNL Target] 請求傳送的 JavaScript 內容未載入。{#section_03EC9B9C410B4F52A7FCD81840311709}

升級至 [!DNL mbox.js] 版本 58 或更新版本。

Mbox.js 版本 58 和更新版本會在出現 HTML `BODY` 標記之後，立即對全域 [!DNL Target] 請求執行非 JavaScript 內容。針對全域 [!DNL Target] 請求的 `<script>` 標記內的 JavaScript 內容會在觸發 `DOMContentLoaded` 事件之後執行。這個內容傳送順序可確保全域 [!DNL Target] 請求的 JavaScript 內容受到傳送並正確呈現。

## 未設定 Target cookie{#section_77AFEB541C0B495EB67E29A4475DF960}

如果您的網站有子網域，例如 [!DNL us.domain.com]，但您需要將 Target Cookie 設定在 [!DNL domain.com] (而不是 [!DNL us.domain.com])，則必須覆寫 `cookieDomain` 設定。如需詳細資訊，請參閱 [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md)。

## 如果元素也是 AEM 個人化的一部分，Target 內容會忽隱勿現或未出現。{#section_9E1DABEB75AB431FB9F09887E6DD07D3}

如果 DOM 元素 Adobe Experience Manager (AEM) 個人化目標鎖定和 Target 活動的一部分，Target 內容可能會忽隱忽現或沒有出現。

若要補救這種情況，您可以在執行 Target 的頁面上停用 AEM 個人化。

## 無效 URL 導致重新導向與遠端選件無法傳送。  {#section_7D09043B687F43B39DAEDF17D00375AC}

如果重新導向與遠端選件使用無效的 URL，可能會無法傳送。

若為重新導向選件，可包含 [!DNL Target] 回應`/* invalid redirect offer URL */`

或

若為遠端選件，可包含 [!DNL Target] 回應`/* invalid remote offer URL */`

您可在瀏覽器中或使用 mboxTrace 來檢查 [!DNL Target] 回應。請參閱 [https://tools.ietf.org/html/std66](https://tools.ietf.org/html/std66) 以取得有效 URL 的詳細資訊。

## 我的網站未觸發 Target 請求。

如果您使用無效的 doctype，at.js 不會觸發 Target 請求。at.js 需要 HTML 5 doctype。

## 訓練影片

以下影片含有本文章探討之概念的詳細資訊。

### 新增擴充功能 ![Tutorial badge](/help/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/23114t2/)

### 基本Adobe Target調試![教程徽章](/help/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/23115t2/)

### Mbox Trace ![Tutorial badge](/help/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/23113t2/)
