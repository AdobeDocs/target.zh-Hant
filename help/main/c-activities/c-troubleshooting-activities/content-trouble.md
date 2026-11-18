---
keywords: 偵錯 mbox;疑難排解 mbox;mbox 問題;閃現;mboxDebug;mboxTrace;權杖;偵錯工具;優先順序;活動優先順序;Adobe Experience Cloud 偵錯工具;orderConfirmPage mbox;SiteCatalyst 購買 mbox;熱賣;最暢銷商品
description: 尋找建議來幫助解決如果頁面未顯示預期內容的問題。 學習如何在 Adobe Target 中偵錯內容傳送。
title: 如何疑難排解內容傳送問題？
feature: Activities
exl-id: 887b7956-1d61-439a-8339-c150deb9a378
TQID: 'https://experienceleague.adobe.com/nkaoqcuoqMm67AnEjSg6dCnFDy-jvlwvD1a6YeXTkwk'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: 6efa6b7a-8062-5c41-aef4-b4853cc306ae
    internal-label: Activities
subfeature_v2:
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
    internal-label: at.js
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 22dff18ca8369805557788d62c4eaf09f9764494
workflow-type: tm+mt
source-wordcount: '1677'
ht-degree: 55%
---
# 疑難排解內容傳送 {#content-trouble}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解當您的頁面未顯示預期內容時，如何在[!DNL Adobe Target]中偵錯內容傳送。

>[!ENDSHADEBOX]

當頁面未顯示預期的內容時，原因可能是活動代碼中的錯誤、[!DNL Target]請求遺失或放置錯誤，或與另一個活動衝突。 請仔細檢查您的活動或行銷活動代碼，因為拼寫錯誤或其他錯誤可能會阻止顯示預期的內容。 然後使用mboxTrace、mboxDebug或Adobe Experience Cloud Debugger來檢查[!DNL Target]請求。

當您在頁面上設定[!DNL Target]時，**mboxDebug**&#x200B;特別有用，以確保引發[!DNL Target]要求並設定Cookie。 但是，它不會進入在偵錯內容傳送時有用的詳細資訊。 如果您的活動未顯示在頁面上，或是顯示不想要的內容，請使用 mboxTrace 來詳細檢查和偵錯頁面。

## 偵錯工具 {#debugging-tools}

### 擷取授權Token {#section_BED130298E794D1FA229DB7C3358BA54}

mboxTrace和mboxDebug會公開促銷活動資料和設定檔資料給外部對象，因此需要授權權杖。 在[!DNL Target]UI 中可以擷取授權 Token。 權杖的有效期限為六小時。

您必須具備下列其中一個使用者權限才能產生驗證權杖：

* 至少&#x200B;**[!UICONTROL 編輯者]**&#x200B;許可權（或&#x200B;**[!UICONTROL 核准者]**）

  如需有關 [!DNL Target Standard] 客戶的詳細資訊，請參閱&#x200B;*使用者*&#x200B;中的[指定角色與權限](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions)。 如需有關 [!DNL Target Premium] 客戶的詳細資訊，請參閱[設定企業權限](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md)。

* 工作區/產品設定檔層級的管理員角色

  工作區僅適用於 [!DNL Target Premium] 客戶。 如需詳細資訊，請參閱[企業使用者權限](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md)。

* [!DNL Adobe Target] 產品層級的管理員權限 (Sysadmin 權限)

擷取授權權杖：

1. 存取&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 實作]**。
1. 在[偵錯工具]區段中，按一下[產生]新驗證Token **。**

   ![產生新驗證權杖](/help/main/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/assets/debugger-auth-token.png)

1. 將產生的 Token 當作參數新增至 URL，以啟用其中一個進階偵錯工具。

   ![授權 Token](/help/main/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/assets/auth-token.png)

### mboxTrace {#section_256FCF7C14BB435BA2C68049EF0BA99E}

mboxTrace 可讓您接收附加至 [!DNL Target] 回應的追蹤資訊。 追蹤資訊可反映 [!DNL Target] 呼叫的結果 (例如，轉換或印象) 以及可協助判斷為何發生此特定結果的任何其他資料，例如在行銷活動中所進行選擇內的一組可用分支。 請使用此資訊來對內容傳送除錯。

以下是可用的參數:

| mboxTrace 選項 | 結果 |
|--- |--- |
| `?mboxTrace=console` | 列印至控制台記錄做為物件。<br>對於 at.js，您必須檢查網路請求並查看「預覽」(Chrome) 或「回應」(Firefox)，而不是像 mbox.js (現已被取代) 一樣彈出新瀏覽器視窗或輸出至主控台。 |
| `?mboxTrace=json` | 列印至控制台記錄做為常值 JSON 字串 |
| `?mboxTrace=window` | 列印至彈出式視窗做為 JSON 字串 |
| `?mboxTrace=disable` | 關閉追蹤工作階段模式 |

**mboxTrace 呼叫範例**

`https://www.mysite.com/page.html?mboxTrace=window&authorization=f543abf-0111-4061-9619-d41d665c59a6`

輸出會顯示與內容相關的詳細資訊。 mboxTrace會顯示有關促銷活動或活動與設定檔的詳細資料。 它也會提供執行前的設定檔快照，以及執行後變更內容的快照。 同時顯示每個位置評估了哪些促銷活動或活動。

有些資訊包括相符和不相符的群體與目標 ID:

* **SegmentId**：群體的 ID，來自可重複使用的群體庫或為特定促銷活動建立的匿名群體。
* **TargetId**：目標的 ID，來自目標運算式庫或來自促銷活動的匿名目標。
* **不相符**：請求在此呼叫中不符合那些群體或目標的資格。
* **相符**：請求符合指定的群體或目標的資格。

**在推薦頁面上使用 mboxTrace**：使用 mboxTrace 詳細資料視窗，新增 mboxTrace 做為具有推薦之頁面上的查詢參數，以取代該頁面的推薦設計，此可顯示關於您建議的深入資訊，包括下列項目：

* 傳回的建議以較請求的建議
* 使用的索引鍵，以及是否產生建議
* 條件產生的建議比較備份建議
* 條件組態
* 套用的排除和包含
* 收集規則

您不需要在查詢引數中包含`=console`、`=json`或`=window`。 使用完mboxTrace詳細資料後，請新增`=disable`並按&#x200B;**[!UICONTROL Enter]**&#x200B;以返回正常顯示模式。

mboxTrace 不會影響您網站的正常功能和外觀。 訪客會看到您的一般推薦設計。

### mboxDebug {#mboxdebug}

若要使用 mboxDebug，請附加 mboxDebug 參數至 URL 結尾。 下列表格含有與 [!DNL Target] 回應相關的 URL 參數的相關資訊。

請注意，有些mboxDebug引數可以不使用驗證。

| URL 參數 | 用途 |
|--- |--- |
| `mboxDebug=1` | 偵錯程式<br>將此參數新增至任何已定義 Target 請求的 URL 會開啟快顯視窗，其中含有重要的偵錯詳細資訊。 Cookie 資訊、PCid 及工作階段 ID 值會出現，而且所有的 URL 都會顯示。 按一下 Target 請求 URL 可顯示該 [!DNL Target] 請求的回應。 如需詳細資訊，請參閱 [mbox_debug.pdf](/help/main/assets/mbox_debug.pdf)。 |
| `mboxDisable=1` | 停用頁面上的 mbox |
| `mboxOverride.browserIp=<Insert IP address>` | 測試地理定位<br>使用這個 URL 參數測試地理定位。 輸入IP位址作為此屬性的值，且[!DNL Target]地理定位會評估該IP位址，以比對促銷活動中設定的任何地理定位或細分。 |

>[!NOTE]
>
>確保 URL 片段位於查詢字串參數之後。 第一個 `#` 之後的任何項目都是片段識別碼，導致偵錯程式參數無法正常運作。

### Adobe Experience Cloud Debugger {#section_A2798ED3A431409690A4BE08A1BFCF17}

Adobe Experience Cloud Debugger可協助您瞭解[!DNL Target]實作。 您可以檢視程式庫組態、確認已正確傳遞自訂引數、開啟主控台記錄，以及停用所有[!DNL Target]要求。 在Experience Cloud中驗證之後，您可以使用mboxTrace來檢查您的活動和對象資格以及訪客設定檔。

如需詳細資訊，請參閱本頁結尾的[訓練影片](#training-videos)和使用Adobe Experience Cloud Debugger偵錯at.js [&#128279;](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/target-debugging-atjs.html){target=_blank}。

## 常見問題 {#common-problems}

+++ 最暢銷商品未出現在推薦中

*`SiteCatalyst: purchase`*&#x200B;呼叫無法用於「購買」演演算法流量資料。 改為使用 *`orderConfirmPage`* 呼叫。

+++

</br>

+++ 表單式活動與Target Classic活動發生衝突

以 [!DNL Target Standard/Premium] 建立的表單式活動，可能與 [!DNL Target Classic] UI 中建立的活動發生衝突，兩者有相同的優先順序且使用相同的 [!DNL Target] 請求。 如需詳細資訊，請參閱[活動優先順序](/help/main/c-activities/priority.md)。

+++

</br>

+++ 未設定[!DNL Target] Cookie

如果您的網站有子網域，例如[!DNL us.domain.com]，但您需要在[!DNL domain.com] （而不是[!DNL us.domain.com]）上設定[!DNL Target] Cookie，則必須覆寫`cookieDomain`設定。 如需詳細資訊，請參閱 [targetGlobalSettings()](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/targetglobalsettings.html){target=_blank}。

+++

</br>

+++ 當元素也是Adobe Experience Manager個人化的一部分時，內容會忽隱勿現或未出現

如果DOM元素是Adobe Experience Manager (AEM)個人化目標鎖定和[!DNL Target]活動的一部分，可能會忽隱忽現或未顯示[!DNL Target]內容。

若要補救這種情況，您可以在執行[!DNL Target]的頁面上停用AEM個人化。

+++

</br>

+++ 重新導向與遠端選件因為URL無效而無法傳遞

如果重新導向與遠端產品建議使用無效的 URL，可能會無法傳送。

* 若為重新導向選件，[!DNL Target]回應可包含`/* invalid redirect offer URL */`。
* 若為遠端選件，[!DNL Target]回應可包含`/* invalid remote offer URL */`。

您可以在瀏覽器中或使用mboxTrace來檢查[!DNL Target]回應。 請參閱 [https://tools.ietf.org/html/std66](https://tools.ietf.org/html/std66) 以取得有效 URL 的詳細資訊。

+++

</br>

+++ 我的網站未觸發[!DNL Target]個請求

如果您使用無效的doctype，at.js不會觸發[!DNL Target]請求。 at.js 需要 HTML 5 doctype。

+++

## 在URL中有查詢字串引數的活動 {#query-strings}

**[!UICONTROL 活動URL]**&#x200B;決定符合活動訪客資格的頁面，並向使用者呈現活動體驗。 在活動建立期間出現提示時，輸入完整 URL 並不一定能確保在該網站頁面上傳遞內容，尤其是包含查詢字串參數的 URL。

根據預設，[!UICONTROL 視覺化體驗撰寫器] (VEC)會開啟[視覺化體驗撰寫器設定](/help/main/administrating-target/visual-experience-composer-set-up.md)中指定的頁面。 您也可以在活動建立期間指定不同的頁面。

若要在VEC開啟之後顯示不同的頁面，請按一下&#x200B;**[!UICONTROL 設定齒輪圖示]** >選取&#x200B;**[!UICONTROL 頁面傳送]** >然後在&#x200B;**[!UICONTROL 活動URL]**&#x200B;欄位中指定所需URL。

![設定頁面傳送設定 UI](assets/configure-page-delivery.png)

當URL包含查詢字串引數時，頁面可能無法符合活動資格或顯示個人化內容。 無論目標對象為何，除了可定義查詢引數的基底URL之外，您還可以包含範本規則。

下列選項可用來包含其他範本規則：

* **選項1：**&#x200B;複製URL並使用「包含」選項將其保留在範本規則中

  +++ 檢視範本規則設定

  此選項可確保此 URL 符合活動的資格，但請注意，其相關邊角案例是，透過對包含基底 URL 的 URL 新增其他記錄來影響您的報告資料。

  在這個案例中，URL 為 `https://shopping.mycart.com?type=Summers%20Offers`，而其他範本規則「包含」相同的 URL (以 OR 運算子分隔)：

  ![在範本規則中複製 URL](assets/option1.png)

  +++

* **選項2：**&#x200B;限制URL「包含」只包含查詢字串的條件

  +++ 檢視範本規則設定

  上一個選項中討論的邊角案例適用於這個選項，但此處的條件設定僅限於查詢字串。

  在這個案例中，URL 為 `https://shopping.mycart.com?type=Summers%20Offers`，而其他範本規則僅「包含」查詢字串 (以 OR 運算子分隔)：

  ![範本規則僅包含查詢字串](assets/option2.png)

  +++

* **選項3：**&#x200B;不要將目標定位為完整URL，而是利用URL的特定部分

  +++ 檢視範本規則設定

  在此案例中，URL為`https://shopping.mycart.com?type=Summers%20Offers`，而其他範本規則指定具有&#x200B;**[!UICONTROL type]** > **[!UICONTROL 的**&#x200B;[!UICONTROL &#x200B;查詢&#x200B;]&#x200B;**為（區分大小寫）]** > type=Summers%20Offers，以OR運運算元分隔：

  ![範本規則利用 URL 的特定部分](assets/option3.png)

  +++

## 在設定檔屬性值中逸出雙引號 {#escape}

當您在[!DNL Target]設定檔屬性中傳送包含雙引號的值時，您必須將其雙重逸出，如下所示。

```
adobe.target.trackEvent({
    "mbox": "data-collection",
    "params":    {
        "profile.tagLine": "Escape \\\"Double Quotes\\\" like this."
    }
});
```

## 培訓影片 {#training-videos}

以下影片含有本文章探討之概念的詳細資訊。

### 新增擴充功能![教學課程徽章](/help/main/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/23114t2/)

### 基本 Adobe Target 偵錯![教學課程徽章](/help/main/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/23115t2/)

### Mbox 追蹤![教學課程徽章](/help/main/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/23113t2/)
