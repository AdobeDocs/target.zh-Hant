---
keywords: Targeting;visual experience composer;whitelist;white list;allowlist;allow list;enhanced visual experience composer;vec;troubleshoot visual experience composer;troubleshooting;eec;enhanced experience composer;tls;tls 1.2
description: 在某些情況下，Adobe Target Visual Experience Composer(VEC)和「增強體驗撰寫器」(EEC)有時會發生顯示問題。
title: 疑難排解可視化體驗撰寫器和增強體驗撰寫器的相關問題
feature: Visual Experience Composer (VEC)
translation-type: tm+mt
source-git-commit: 8110807a73e4d6d9848a52224db04faba033c98c
workflow-type: tm+mt
source-wordcount: '1370'
ht-degree: 67%

---


# 疑難排解可視化體驗撰寫器和增強體驗撰寫器的相關問題

在某些情況下，在[!DNL Adobe Target] Visual Experience Composer(VEC)和Enhanced Experience Composer(EEC)中有時會出現顯示問題和其他問題。

## 最近宣佈的Google Chrome SameSite Cookie實施政策對VEC和EEC有何影響？{#samesite}

透過最新變更（2020年8月），所有使用Chrome 80+瀏覽器版本的使用者：

* *not*&#x200B;是否能在其網站受密碼保護的頁面中使用VEC（安裝或未啟用VEC Helper擴充功能）。 這是因為其網站登入Cookie將被視為第三方Cookie，不會隨登入請求傳送。 唯一的例外是當客戶網站登入Cookie已將SameSite參數設為「無」時。
* *not*&#x200B;是否能在編輯活動時（當活動不在網站上時）下載[!DNL Target]程式庫。 這是因為下載呼叫是從客戶網域向安全的Adobe網域進行，並會被拒絕為未驗證。
* EEC將&#x200B;*not*&#x200B;函式用於所有用戶，因為它無法在`adobemc.com domain`上為Cookie設定SameSite屬性。 若沒有此屬性，瀏覽器將拒絕這些Cookie，導致EEC失敗。

Adobe已將更新的VEC Helper擴充功能提交至Google Chrome商店。 此擴充功能會覆寫Cookie屬性，以視需要設定`SameSite="none"`屬性。 [更新的擴充功能可在此處找到](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak?hl=en)。 如需有關安裝和使用VEC Helper Extension的詳細資訊，請參閱[Visual Experience Composer helper extension](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)。

對於您自己的網站Cookie，您必須依名稱指定Cookie。 將[!UICONTROL Cookie]滑桿切換至開啟位置，然後依名稱和Cookie網域指定Cookie。 Cookie名稱是「mbox」，而Cookie網域是您從中提供mbox之網域的第二層和最上層。 因為是使用公司所提供的網域，所以這些會是第一方 Cookie。範例: `mycompany.com`. 如需詳細資訊，請參閱&#x200B;*Experience Cloud介面使用指南*&#x200B;中的[Adobe Target Cookies](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-target.html)。

![Cookie在VEC協助工具擴充功能中切換](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/cookies-vec-helper.png)

### 替代方案與解決方法

使用下列其中一個選項來確保VEC和EEC繼續如預期般運作：

* 下載並使用更新的[VEC Helper擴充功能](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak?hl=en)。
* 使用Mozilla Firefox瀏覽器。 Firefox尚未執行此政策。
* 繼續使用Chrome，但將`chrome://flags/#same-site-by-default-cookies`標幟設為「已停用」。

   >[!NOTE]
   >
   >如果Cookie的SameSite屬性已設定為「Lax」或「Strict」，則&#x200B;*not*&#x200B;就足夠了。

## Target 是否支援多重層級 iframe?

Target 不支援多重層級 iframe。如果網站載入具有子項 iframe 的 iframe，Target 資料庫 (at.js and mbox.js) 只會與父項 iframe 互動。Target 資料庫不會與子項 iframe 互動。

作為因應措施，您可以使用子項 iframe 的 URL 在體驗中新增頁面。

## 當我嘗試編輯頁面時，我只看到了進度環而非我的頁面。(VEC 和 EEC) {#section_313001039F79446DB28C70D932AF5F58}

如果 URL 包含 # 字元，則可能發生此問題。若要修正問題，請在可視化體驗撰寫器中切換至「瀏覽」模式，然後切換回「撰寫」模式。進度環應該會消失，並且頁面應該會載入。

## 內容安全性原則 (CSP) 標頭在我的網站上封鎖 Target 資料庫。(VEC 和 EEC) {#section_89A30C7A213D43BFA0822E66B482B803}

如果您的網站的 CSP 標頭封鎖 Target 資料庫，然後載入網站但防止編輯，請確保 Target 資料庫未遭到封鎖。

>[!NOTE]
>
>除了下列資訊外，您還可以使用適用於 Google Chrome 的 [Adobe Target VEC Helper 瀏覽器擴充功能](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)。

![](assets/cps_headers.png)

作為解決方案，您可以設定 Requestly 規則來移除 CSP 標頭，如下所示:

![](assets/cps_headers_2.png)

您可以為造成資源無法在 VEC 內載入的任何標頭設定類似的 Requestly 規則。

對於 Requestly，一旦需要移除標頭，您就應該執行下列任一動作:

* 為要在 VEC 中開啟的 URL 新增 URL 規則，如此一來，便僅有那些 URL 的標頭會移除。
* 在 VEC 中編輯時啟用規則，並在不使用 VEC 時停用規則。

## 重新編輯已儲存的活動時，VEC 或 EEC 似乎損毀或未初始化。(VEC 和 EEC) {#section_5AC3BA8F8FBB451EA814F298D0645E54}

如果在定義體驗之後，於可視化體驗撰寫器外部變更了網站，開啟活動進行重新編輯時，會找不到稍早採取動作所在的選取器。頁面似乎損毀，並且未顯示警告。

## VEC 或 EEC 未顯示我的旋轉橫幅和包含 JavaScript 的其他內容。(VEC 和 EEC) {#section_8B5BE6EB050B42D6A14A054724C41330}

依預設，可視化體驗撰寫器會封鎖 JavaScript 元素。如果您在可視化體驗撰寫器設定中停用 JavaScript，則可以使用這些元素。根據網站的設定方式，一些項目可能會繼續不正確地顯示或保持無法使用。

## 我託管的 target.js 檔案在後續的頁面重新載入中無法載入。(VEC 和 EEC) {#section_87F6418C2CD142A7B4D1E7037935F81F}

當客戶的 mbox.js 版本早於 57 (即版本 56 或更早版本) 時會發生此問題。

建議所有 VEC 使用者升級至 [mbox.js 最新版本](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mboxjs-change-log.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A)，或至少升級至版本 57。您也應考慮[移轉至 at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#concept_8AC8D169E02944B1A547A0CAD97EAC17)。

## 在頁面上變更一個元素時，變更了多個元素。(VEC 和 EEC) {#section_309188ACF34942989BE473F63C5710AF}

如果您在頁面的多個元素上使用相同的 DOM 元素 ID，變更這些元素中的一個會變更具有該 ID 的所有元素。若要防止發生此問題，一個 ID 應該僅在每個頁面上使用一次。這是標準的 HTML 最佳作法。如需詳細資訊，請參閱[頁面修改案例](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB)。

## 我無法編輯 iFrame-busting 網站的體驗。(VEC 和 EEC) {#section_9FE266B964314F2EB75604B4D7047200}

此問題可透過啟用增強體驗撰寫器來解決。按一下「**[!UICONTROL 管理]** > **[!UICONTROL 視覺體驗撰寫器]**」，然後選取啟用「增強體驗撰寫器」的核取方塊。 增強體驗撰寫器使用 Adobe 管理的 Proxy 來載入您的頁面進行編輯。這允許在 iFrame-busting 網站上進行編輯，並允許在您尚未新增 Adobe Target 程式碼的網站和頁面上進行編輯。在新增程式碼之後，才會將活動傳送至網站。有些網站可能無法透過增強體驗撰寫器載入，在此情況下，您可以取消勾選此選項，以透過 iFrame 載入可視化體驗撰寫器。[]

>[!NOTE]
>
>對於您在本機託管的頁面或無法從您的網路外部存取的頁面，Adobe Proxy 伺服器無法存取這類頁面，且無法在 EEC 中開啟。這些頁面可能包括測試 URL、使用者接受測試 (UAT) URL，或本機主控的頁面。

## 我想要在尚未完成 mbox/target 實施的頁面上設定測試。(VEC 和 EEC) {#section_DE63BCCB5B124E10A71FA579B582A80A}

請參閱以上的「我無法編輯 iFrame-busting 網站的體驗」。

## 具有「編輯文字/HTML」或「變更文字/HTML」的粗體和斜體文字樣式未在我的頁面上顯示。有時文字會在套用這些樣式變更之後消失。(VEC 和 EEC) {#section_7A71D6DF41084C58B34C18701E8774E5}

如果您對 A/B 或體驗鎖定目標活動使用可視化體驗撰寫器中的&#x200B;**[!UICONTROL 編輯文字/HTML]**，或對自動個人化或多變數測試活動使用&#x200B;**[!UICONTROL 變更文字/HTML]**，以讓文字粗體或斜體，這些樣式可能無法在頁面上套用，或文字會從可視化體驗撰寫器中的頁面消失。這是因為 RTF 格式編輯器套用這些樣式的方式可能會干擾網站標記。

如果您看見此問題:

1. 按一下 RTF 格式編輯器中的&#x200B;**[!UICONTROL 「HTML」]**&#x200B;按鈕來進入來源編輯模式。
1. 尋找樣式文字元素。

   * 針對粗體文字，將 `<strong>` 元素變更為 `<b>`。

   * 針對斜體文字，將 `<em>` 元素變更為 `<i>`。

## 針對自動個人化活動，影像交換在 VEC 或 EEC 中似乎損毀。(VEC 和 EEC) {#section_88AABFDFE6A3420299B0D508B12A3994}

新增影像選件至位置以取得 VEC 或 EEC 中原始影像空間的完整尺寸。在傳遞時，影像不會展開並且如原樣顯示，因此對傳遞沒有影響。
