---
keywords: 鎖定目標；視覺化體驗撰寫器； VEC；疑難排解視覺化體驗撰寫器；疑難排解； TLS； TLS 1.2
description: 瞭解如何疑難排解[!UICONTROL 視覺化體驗撰寫器] (VEC)中的問題。
title: 如何疑難排解[!UICONTROL 視覺化體驗撰寫器]的相關問題？
feature: Visual Experience Composer (VEC)
exl-id: ca251025-25e8-4e56-9b59-81310fc763c1
TQID: 'https://experienceleague.adobe.com/VNkydzzU-WRRAL0pqQPOs-sKrY8a6DS5Go764UGh0Hs'
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
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '1150'
ht-degree: 4%
---
# 疑難排解[!UICONTROL 視覺化體驗撰寫器]的相關問題 {#vec-issues}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解如何解決只影響&#x200B;**[!UICONTROL 視覺化體驗撰寫器]** (VEC)的問題。

>[!ENDSHADEBOX]

顯示在某些情況下，有時候會在[!DNL Adobe Target] **[!UICONTROL 視覺化體驗撰寫器]** (VEC)中發生問題。 以下專案說明僅影響VEC的問題以及如何解決這些問題。

+++ 在VEC中開啟網站時未載入[!DNL Target]資料庫

在&#x200B;**[!UICONTROL 視覺化體驗撰寫器]**&#x200B;中開啟網站時，[!DNL Target]會將引數`mboxEdit=1`和`mboxDisable=1`新增至URL。

在不重新載入頁面的情況下，從一個頁面導覽至另一個頁面時，修剪或移除這些引數的網站（尤其是單頁應用程式）會中斷[!DNL Target]功能，且[!DNL Target]資料庫不會載入。 若要避免此問題，請將這兩個引數都保留在URL中。

+++

+++ 頁面無法在EEC中開啟或載入緩慢，或活動和體驗在VEC中載入緩慢

數個問題可能會影響[!DNL Target]體驗撰寫器中的頁面效能。 最常見的如下：

* 頁面沒有mbox。
* 網站使用Proxy封鎖，可防止頁面在任一體驗撰寫器中開啟。
* 網站不允許本身在iFrame中開啟。

當&#x200B;**[!UICONTROL 增強體驗撰寫器]**&#x200B;發生問題時，請關閉該工具，並改用&#x200B;**[!UICONTROL 視覺化體驗撰寫器]**。 若要這麼做，請前往&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 視覺化體驗撰寫器]**，並關閉&#x200B;**[!UICONTROL 啟用增強體驗撰寫器]**&#x200B;選項。

控制檯中會顯示下列錯誤訊息：

![瀏覽器主控台錯誤訊息，指出由於X-Frame-Options設為SAMEORIGIN，頁面已拒絕顯示在框架中](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/console_error_message.jpg)

當這兩種撰寫器都無法運作時，覆寫網站X-Frame-Options標頭的瀏覽器擴充功能(例如[!DNL Requestly] （[!DNL Chrome]或[!DNL Firefox]）或Modify Response Headers ([!DNL Firefox]))會允許網站載入iFrame，進而啟用VEC。 當無法使用瀏覽器延伸時，請使用[表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md)。 除了下列程式外，也可以使用[!DNL Google Chrome]的[[!DNL Adobe Target] **[!UICONTROL Visual Editing Helper &#x200B;]**&#x200B;擴充功能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md)。

>[!NOTE]
>
>這些擴充功能僅適用於VEC編輯。
>
>透過[!DNL Requestly]，每當需要移除標頭時，請執行下列任一項作業：
>
>* 為要在VEC中開啟的URL新增URL規則，以便僅移除這些URL的標題。
>* 在VEC中編輯時啟用規則，並在VEC未使用時停用規則。
>
>**[!UICONTROL 修改回應標題]** ([!DNL Firefox])時，無法使用URL規則，因此必須在VEC中編輯時啟用規則，並在VEC未使用時停用規則。

設定擴充功能後，即使&#x200B;**[!UICONTROL 增強體驗撰寫器]**&#x200B;已停用，頁面也會載入&#x200B;**[!UICONTROL 視覺化體驗撰寫器]**。

+++

+++ 使用Requestly （Chrome或Firefox）移除X-Frame-Options標頭

1. 關閉&#x200B;**[!UICONTROL 增強體驗撰寫器]**。
1. 在[!DNL Chrome]或[!DNL Firefox]上安裝[!DNL Requestly]瀏覽器延伸模組。
1. 開啟擴充功能並選取&#x200B;**[!UICONTROL 修改標頭]**。
1. 輸入規則名稱。
1. 在修改規則中，建立移除標題的規則：

   * 將&#x200B;**[!UICONTROL 「新增」]**&#x200B;切換為&#x200B;**[!UICONTROL 「移除」]**。
   * 將&#x200B;**[!UICONTROL 「要求」]**&#x200B;切換為&#x200B;**[!UICONTROL 「回應」]**。
   * 輸入 &quot;X-Frame-Options&quot; 作為標頭名稱。

1. 重複上一步驟，並輸入「x-frame-options」作為標頭名稱。

   >[!NOTE]
   >
   >使用[!DNL Requestly]處理的標頭須區分大小寫。

1. 將&#x200B;**[!UICONTROL Equals]**&#x200B;變更為&#x200B;**[!UICONTROL Contains]**&#x200B;作為來源URL的條件，並輸入要載入VEC的活動URL。

   ![名為Bypass iframe爆裂程式碼的Requestly規則，此規則會移除包含adobe.com](assets/chrome_extension.png)之URL的X-Frame-Options回應標頭

1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

   ![移除所有URL之X-FRAME-OPTIONS和x-frame-options回應標頭的Requestly規則](assets/requestly.png)

頁面現在應該會在&#x200B;**[!UICONTROL 視覺化體驗撰寫器]**&#x200B;中快速載入。

+++

+++ 移除具有Modify Response標頭的X-Frame-Options標頭(Firefox)

1. 在[!DNL Firefox]上安裝[!DNL Modify Response Headers]擴充功能並重新啟動瀏覽器。
1. 從[!DNL Firefox]擴充功能中，選取[!DNL Modify Response Headers]擴充功能。
1. 按一下&#x200B;**[!UICONTROL 「偏好設定」]**。
1. 從&#x200B;**[!UICONTROL 動作]**&#x200B;下拉式清單中的Select **[!UICONTROL 篩選器]**。
1. 在&#x200B;**[!UICONTROL 標頭名稱]**&#x200B;欄位中，輸入&#x200B;**[!UICONTROL X-Frame-Options]**。
1. 重複前兩個步驟，使用&#x200B;**[!UICONTROL x-frame-options]**&#x200B;新增篩選器。
1. 按一下「**[!UICONTROL 新增]**」。
1. 按一下&#x200B;**[!UICONTROL 「開始」]**。

![在Firefox中修改回應標題視窗，X-Frame-Options標題上的篩選器顯示為已啟用](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox_extension.png)

+++

+++ VEC中未顯示頁面

檢查下列原因：

* **擴充功能版本：**&#x200B;最新版本的[[!DNL Adobe Experience Cloud] **[!UICONTROL Visual Editing Helper &#x200B;]**&#x200B;擴充功能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md)提供與VEC的最佳相容性。 若要驗證已安裝的版本，請移至&#x200B;**[!UICONTROL &#x200B;擴充功能&#x200B;]**>**[!UICONTROL &#x200B;管理擴充功能&#x200B;]**，然後按一下&#x200B;**[!UICONTROL &#x200B;詳細資料&#x200B;]**。
* **編寫資料庫：** VEC需要編寫資料庫才能修改網頁。 這些檔案內嵌於at.js資料庫中，無論at.js或[!DNL Adobe Experience Platform Web SDK]是否已在頁面上，每次使用VEC時，擴充功能都會從[!DNL Adobe]伺服器下載這些檔案。 檢查&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 實作]**&#x200B;中設定的at.js標頭是否不包含無效的變更。
* **已封鎖的要求：**&#x200B;當頁面內嵌於iFrame中時，頁面不可封鎖載入的必要要求。 這種封鎖包括`frame-ancestors` CSP指示、網站中的自訂JavaScript程式碼、中繼HTML標籤和`x-frame-options`標頭。
* **保留的檔案名稱：**&#x200B;頁面的JavaScript不得干擾編寫程式庫。 請勿使用或包含具有下列保留名稱的檔案：

  * `target-vec-helper.js`
  * `target-vec.js`
  * `target.js`
  * `admin.css`
  * `sizzle.js`
  * `mixContentCheck.html`

  意外覆寫這些檔案中定義的變數或事件也可能會導致VEC發生問題。

* **安全網站上的不安全頁面：**&#x200B;瀏覽器會封鎖此頁面。 按一下位址列URL左側的圖示，然後按一下&#x200B;**[!UICONTROL 停用此頁面的保護]**。
* **無效的URL：**&#x200B;輸入的URL無效。
* **Cookie：**&#x200B;如果網站無法在VEC中載入或意外運作，在[!DNL Target]中載入網站之前，先在瀏覽器中接受其Cookie，即可解決問題。

+++

+++ VEC在瀏覽模式中似乎損毀

在&#x200B;**[!UICONTROL 瀏覽]**&#x200B;模式中，當開啟的URL缺少[!DNL Target]資料庫（[at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/overview.html?lang=zh-Hant){target=_blank}或[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=zh-Hant){target=_blank}）或包含frame-buster標頭時，VEC會顯示為損毀。 基於瀏覽器安全理由，[!DNL Target]無法正確存取已導覽至的URL，或頁面載入時VEC URL未一致更新。

VEC會在`<iframe>`中載入網頁，而目前瀏覽器的安全性機制會防止[!DNL Target] UI存取相同來源原則下的框架元素。 瀏覽器會封鎖嘗試存取不同來源之框架的Script，包括`location.href`等資訊。

使用新的[Visual Editing Helper擴充功能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md)將[!DNL Target]資料庫插入頁面，以最佳方式瀏覽頁面。

+++

+++ 問題是由VEC中的CSS衝突所導致

檢查當頁面在編輯器中載入時，是否有任何CSS檔案影響可見度。 例如，頁面本文上的`overflow: hidden`屬性可能會導致捲動問題或觸發干擾編寫功能表的點選事件。

+++
