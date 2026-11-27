---
keywords: 鎖定目標；視覺化體驗撰寫器；白名單；允許清單；允許清單；增強視覺化體驗撰寫器； VEC；疑難排解視覺化體驗撰寫器；疑難排解； EEC；增強體驗撰寫器； TLS； TLS 1.2
description: 瞭解如何疑難排解[!DNL Target] [!UICONTROL 視覺化體驗撰寫器] (VEC)和[!UICONTROL 增強體驗撰寫器] (EEC)在某些情況下有時會發生的問題。
title: 如何疑難排解[!UICONTROL 視覺化體驗撰寫器]和[!UICONTROL 增強體驗撰寫器]的相關問題？
feature: Visual Experience Composer (VEC)
exl-id: d829cd63-950f-4bb4-aa58-0247f85de383
TQID: 'https://experienceleague.adobe.com/4v7Qe-Yzjke-GceUSRDO2SMZGkxvrkdsSXQt8TR-bic'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
subfeature_v2:
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
    internal-label: at.js
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '1218'
ht-degree: 13%
---
# 疑難排解[!DNL Adobe Target] [!UICONTROL 視覺化體驗撰寫器]和[!UICONTROL 增強體驗撰寫器]的相關問題 {#vec-eec-issues}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解如何解決同時影響&#x200B;**[!UICONTROL 視覺化體驗撰寫器]** (VEC)和&#x200B;**[!UICONTROL 增強體驗撰寫器]** (EEC)的問題。

>[!ENDSHADEBOX]

在某些情況下，[!DNL Target] **[!UICONTROL 視覺化體驗撰寫器]** (VEC)和&#x200B;**[!UICONTROL 增強體驗撰寫器]** (EEC)有時會發生顯示問題和其他問題。 以下專案說明影響這兩種撰寫器的問題以及解決方法。

## 瀏覽器和安全性

### Google Chrome SameSite Cookie 原則 {#samesite}

[!DNL Google Chrome]的SameSite Cookie執行原則會影響下列發行版本的VEC和EEC。

>[!NOTE]
>
>以下變更適用於所有三個版本。 除非已安裝並啟用[VEC Helper擴充功能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md)，否則無法在網站受密碼保護的頁面上使用VEC。 網站的登入Cookie會視為第三方Cookie，因此不會在&#x200B;**[!UICONTROL 瀏覽]**&#x200B;模式的VEC編輯器中連同登入要求一起傳送。 唯一的例外是登入Cookie已設定`SameSite=None`和`Secure`屬性。

* **Chrome 94 （2021年9月21日）：**&#x200B;針對具有Chrome 94和更新版本的所有使用者，已移除命令列旗標`--disable-features=SameSiteByDefaultCookies,CookiesWithoutSameSiteMustBeSecure`。
* **Chrome 91 （2021年5月25日）：**&#x200B;對於具有Chrome 91和更新版本的所有使用者，旗標`#same-site-by-default-cookies`和`#cookies-without-same-site-must-be-secure`已從`chrome://flags`中移除。 此行為現在預設為啟用。
* **Chrome 80 （2020年8月）：**&#x200B;針對所有具有Chrome 80和更新版本的使用者：

  * 編輯活動時無法下載[!DNL Target]資料庫（如果它們尚未在網站上）。 下載呼叫是從客戶網域傳送到安全的[!DNL Adobe]網域，且未經過驗證即遭到拒絕。
  * EEC無法運作，因為它無法在`adobemc.com`網域上設定Cookie的SameSite屬性。 若沒有此屬性，瀏覽器會拒絕這些Cookie，導致EEC失敗。

+++ 判斷封鎖哪些Cookie

若要判斷哪些Cookie被SameSite Cookie強制原則封鎖，請在[!DNL Chrome]中使用[!DNL Developer Tools]。

1. 在[!DNL Chrome]中檢視VEC時，請按一下Chrome > **[!UICONTROL 更多工具]** > **[!UICONTROL 開發人員工具]**&#x200B;右上角的&#x200B;**[!UICONTROL 省略符號]**&#x200B;圖示。
1. 按一下&#x200B;**[!UICONTROL 網路]**&#x200B;標籤，然後尋找封鎖的Cookie。

   >[!NOTE]
   >
   >使用&#x200B;**[!UICONTROL Has blocked cookie]**&#x200B;核取方塊，讓封鎖的cookie更容易找到。

+++

+++ 內容安全性原則(CSP)標頭會封鎖網站上的[!DNL Target]資料庫

如果網站的CSP標頭封鎖[!DNL Target]資料庫，則網站會載入但無法編輯。 請確定未封鎖[!DNL Target]資料庫。

>[!NOTE]
>
>除了下列資訊外，還可以使用[!DNL Google Chrome]的[Adobe Target VEC Helper瀏覽器擴充功能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)。

![瀏覽器主控台顯示封鎖的target.js要求，且訊息違反內容安全性原則指示詞](assets/cps_headers.png)

解決方法是設定[!DNL Requestly]規則以移除CSP標頭，如下圖所示。

![Requestly對話方塊， Modify HTTP Request and Response中的標頭，其規則名稱為Content-Security-Policy，可從回應中移除Content-Security-Policy標頭](assets/cps_headers_2.png)

可以為任何導致資源無法在VEC內載入的標頭設定類似的[!DNL Requestly]規則。 當需要使用[!DNL Requestly]移除標頭時，請執行下列任一項作業：

* 為要在VEC中開啟的URL新增URL規則，以便僅移除這些URL的標題。
* 在VEC中編輯時啟用規則，並在VEC未使用時停用規則。

+++

+++ 不支援多重層級iframe

[!DNL Target]不支援多重層級iframe。 如果網站載入具有子項iframe的iframe，at.js只會與父項iframe互動。 [!DNL Target]資料庫不會與子項iframe互動。

做為因應措施，請使用子項iframe的URL在體驗中新增頁面。

+++

+++ 無法在iFrame-busting網站或沒有[!DNL Target]實作的頁面上編輯體驗

啟用&#x200B;**[!UICONTROL 增強體驗撰寫器]** (EEC)以解決此問題。 按一下&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 視覺化體驗撰寫器]**，然後選取可啟用&#x200B;**[!UICONTROL 增強體驗撰寫器]**&#x200B;的核取方塊。

EEC使用[!DNL Adobe]管理的Proxy來載入頁面以進行編輯。 此Proxy允許在iFrame-busting網站以及尚未新增[!DNL Adobe Target]程式碼的網站和頁面上編輯。 在新增程式碼之後，才會將活動傳送至網站。 有些網站可能無法透過EEC載入，在此情況下，清除此選項會透過iFrame載入頁面。

>[!NOTE]
>
>[!DNL Adobe] Proxy伺服器無法存取本機主控的頁面和無法從網路外部存取的頁面，且無法在EEC中開啟。 這些頁面可能包括測試 URL、使用者接受測試 (UAT) URL，或本機主控的頁面。

+++

## 頁面載入和顯示

+++ 編輯頁面時會顯示旋轉圖示，而非頁面

如果URL包含#個字元，就可能發生這種情況。 若要修正此問題，請在VEC或EEC中切換至&#x200B;**[!UICONTROL 瀏覽]**&#x200B;模式，然後切換回&#x200B;**[!UICONTROL 撰寫]**&#x200B;模式。 進度環應該會消失，並且頁面應該會載入。

+++

+++ 再次編輯已儲存的活動時，VEC或EEC似乎損毀或未初始化

如果定義體驗後，網站在VEC外部有所變更，則在開啟活動以重新編輯時，找不到先前執行動作的選取器。 頁面似乎損毀，並且未顯示警告。

+++

+++ 旋轉橫幅和其他包含JavaScript的內容不會顯示在VEC或EEC中

依預設，VEC會封鎖JavaScript元素。 停用JavaScript可以處理這些元素。 根據網站的設定方式，一些項目可能會繼續不正確地顯示或保持無法使用。

+++

+++ 針對Automated Personalization活動，影像交換在VEC或EEC中似乎損毀

新增影像產品建議至位置以取得 VEC 或 EEC 中原始影像空間的完整尺寸。 在傳遞時，影像不會展開並且如原樣顯示，因此對傳遞沒有影響。

+++

## 編輯結果

+++ 變更頁面上的一個元素會變更多個元素

如果您在頁面的多個元素上使用相同的 DOM 元素 ID，變更這些元素中的一個會變更具有該 ID 的所有元素。 為避免此問題，請在每個頁面上只使用一次ID。 這是標準的 HTML 最佳作法。 如需詳細資訊，請參閱[頁面修改案例](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#vec-scenarios)。

+++

+++ 套用「編輯文字」/「編輯HTML」或「變更文字」/「變更HTML」後，粗體和斜體文字樣式不會顯示或文字消失

當&#x200B;**[!UICONTROL 編輯文字]**/**[!UICONTROL 編輯HTML]**&#x200B;在VEC中用於&#x200B;**[!UICONTROL A/B測試]**、**[!UICONTROL 體驗鎖定目標]**&#x200B;活動，或&#x200B;**[!UICONTROL 變更文字]**/**[!UICONTROL 變更HTML]**&#x200B;用於&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;或&#x200B;**[!UICONTROL 多變數測試]**&#x200B;活動時，若要將文字設為粗體或斜體，樣式可能不會套用於頁面，或文字可能會從VEC的頁面中消失。 之所以發生此情況，是因為RTF編輯器套用這些樣式的方式可能會干擾網站標籤。

如果發生此問題：

1. 按一下 RTF 格式編輯器中的&#x200B;**[!UICONTROL 「HTML」]**&#x200B;按鈕來進入來源編輯模式。
1. 尋找已設定樣式的文字元素。

   * 針對粗體文字，將 `<strong>` 元素變更為 `<b>`。
   * 針對斜體文字，將 `<em>` 元素變更為 `<i>`。

+++
