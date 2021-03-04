---
keywords: 部分資料;A4T;差異;analytics for target;孤立;虛擬報表套裝;虛設項目;疑難排解;未拼接;膨脹;未指定
description: 瞭解如何在使用Analytics for Target(A4t)時，將誇大的「瀏覽」和「訪客」計數的影響降到最低。 瞭解「部分資料」是什麼，以及如何減少資料。
title: 如何將A4T中誇大的瀏覽次數和訪客計數降至最低？
feature: 目標分析 (A4T)
translation-type: tm+mt
source-git-commit: 4abf975095c5e29eea42d67119a426a3922d8d79
workflow-type: tm+mt
source-wordcount: '1363'
ht-degree: 48%

---


# 在 A4T 中將膨脹的造訪和訪客計數減到最少{#minimizing-inflated-visit-and-visitor-counts-in-a-t}

使用[!DNL Adobe Analytics]作為[!DNL Adobe Target](A4T)的報表來源時，可協助您將誇大的「瀏覽」和「訪客」計數的影響降到最低。

>[!IMPORTANT]
>在 2016 年 11 月 14 日，Adobe Analytics 已針對 Target 使用 Analytics 報表 (A4T) 的客戶變更部分資料的處理方式。這些變更讓 Adobe Target 資料更能與 Adobe Analytics 的資料模型對應。這些變更已對使用 A4T 的所有客戶展開。這些變更特別能解決在執行 Target 活動時，有些客戶所注意到膨脹的訪客計數的問題。
>
>此變更不溯及既往。如果您的歷史報表顯示膨脹的計數，而您想要將它們從報表中排除，您可以建立虛擬報表套裝，如下所示。
>
>此外，已更新數個JavaScript程式庫，以協助將誇大的計數降至最低。 Adobe建議您升級至下列程式庫版本（或更新版本）:
>
>* Experience Cloud 訪客 ID 服務: visitorAPI.js 版本 2.3.0 或更新版本。
>* Adobe Analytics: appMeasurement.js 版本 2.1。
>* Adobe Target: at.js 0.9.6 版或更新版本 (若 A4T 使用重新導向選件，則不包括 1.1.0 版)。

>
>  
mbox.js 資料庫不支援使用 A4T 重新導向選件。您的實作必須使用 at.js。

## 哪些部分有所變更? {#section_9CCF45F5D66D48EBA88F3A178B27D986}

當[!DNL Adobe Analytics]用於測量[!DNL Target]活動（稱為A4T）時，[!DNL Analytics]會收集頁面上沒有[!DNL Target]活動時無法使用的額外資料。 [!DNL Target]活動會在頁面頂端觸發呼叫，但[!DNL Analytics]通常會在頁面底部觸發其資料收集呼叫。 在A4T至今的實作中，當[!DNL Target]活動處於活動狀態時，Adobe會包含此附加資料。 今後，Adobe僅在[!DNL Target]和[!DNL Analytics]標籤都已引發時，才會包含此額外資料。

## Adobe 為何做出此變更? {#section_92380A4BD69E4B8886692DD27540C92A}

Adobe 對於自己的資料準確性和品質感到自豪。當[!DNL Target]標籤觸發，但[!DNL Analytics]標籤未觸發時，Analytics會記錄「部分資料」（有時稱為「未連結點擊」）。 如果沒有[!DNL Target]活動，則[!DNL Analytics]不會擷取這些未連結的點擊。 雖然在[!DNL Analytics]報告中包含此部分資料可提供其他資訊，但它也會在沒有執行[!DNL Target]活動的期間產生與歷史資料不一致的情況。 這種情況可能會對分析一段時間趨勢的[!DNL Analytics]使用者造成問題。 為確保[!DNL Analytics]中的資料一致性，Adobe會排除所有部分資料。

## 是什麼造成了部分資料? {#section_C9C906BEAA7D44DAB9D3C03932A2FEB8}

Adobe遇到了[!DNL Analytics]中部分資料速率較高的客戶。 部分資料的高比率可能來自不當實施，但也有合法的原因。

部分資料經確認的原因包括下列:

* **不相符的報表套裝 ID (實作):** 在活動設定指定的報表套裝不符合傳送測試所在頁面上的報表套裝。資料無法在[!DNL Analytics]伺服器上協調，因此看起來像是部分資料。
* **慢速頁面：** [!DNL Target] 呼叫位於頁面頂端， [!DNL Analytics] 呼叫通常位於頁面底部。如果頁面載入緩慢，則會增加訪客在[!DNL Target]呼叫引發後，但在[!DNL Analytics]呼叫前離開頁面的可能性。 在連線速度通常較慢的行動網站上，頁面速度緩慢尤其有問題。
* **頁面錯誤：** 如果有JavaScript錯誤或其他觸點未觸發的案例(Experience CloudID服務、Target和Analytics)，則會產生部分資料結果。
* **活動中的重 [!DNL Target] 新導向選** 件：若要使用A4T重新導向活動中的選件，您的實作必須符合某些最低要求。此外，您必須瞭解重要資訊。 如需詳細資訊，請參閱[重新導向選件 - A4T 常見問題集](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#section_FA9384C2AA9D41EDBCE263FFFD1D9B58)。
* **舊版程式庫：在過去** 一年中，Adobe對JavaScript程式庫( [!DNL appMeasurement.js]、 `at.js/mbox.js`和 `visitorAPI.js`)做了幾項改進，以確保資料傳送的效率盡可能高。若要進一步瞭解實作需求，請參閱[實作之前](/help/c-integrating-target-with-mac/a4t/before-implement.md#concept_046BC89C03044417A30B63CE34C22543)。

## 減少部分資料的最佳做法為何? {#section_065C38501527451C8058278054A1818D}

檢閱下列步驟，以減少部分資料收集：

| 步驟 | 任務 |
| --- | --- |
| ![步驟 1](assets/step1_icon.png) | 請確定[!DNL Target]中選取的報表套裝與顯示活動之頁面上的報表套裝相同。 |
| ![步驟 2](assets/step2_icon.png) | 請確定visitorAPI.js、appMeasurement.js、at.js / mbox.js程式庫是A4T相容版本。 若要進一步瞭解實作需求，請參閱[實作之前](/help/c-integrating-target-with-mac/a4t/before-implement.md)。 |
| ![步驟 3](assets/step3_icon.png) | 請確定SDID已設定在離開頁面的所有[!DNL Target]和[!DNL Analytics]呼叫上，且符合。<br/>使用網路分析器或除錯工具，確保呼 `mboxMCSDID` 叫上的 [!DNL Target] 參數符合呼叫中的SDID [!DNL Analytics] 參數。 |
| ![步驟 4](assets/step4_icon.png) | 確認實作資料庫在您的網站上以正確的順序載入網站。如需詳細資訊，請參閱 [Analytics 用於 Target 的實作](/help/c-integrating-target-with-mac/a4t/a4timplementation.md)。 |

## 我如何知道我有多少部分資料? {#section_89B663E2824A4805AB934153508A0F4B}

雖然此資訊無法直接在 [!DNL Analytics] 中取得，您可以聯絡 Adobe 客戶服務來擷取「部分資料」報表。此報表用意在協助偵錯。

## 我如何檢視沒有部分資料的歷史趨勢? {#section_4C9DED560FAD4428B362DDA2064897C3}

此處理變更僅影響發行日期（2016年11月14日）後的資料。 如果您想要調整歷史量度以符合，Adobe建議您建立區段以排除部分資料。

與此變更相關的下列資訊包含的指示可幫助您定義區段和將區段套用至虛擬報表套裝，使得此區段一律會套用至您的 [!DNL Analytics] 檢視。

在多數情況下，一個 [!DNL Target] 點擊會與每個網頁上的一個 [!DNL Analytics] 點擊拼接。如果 [!DNL Target] 和 [!DNL Analytics] 呼叫中同時有一個一致的 SDID，且相同頁面上的 [!DNL Experience Cloud ID] 呼叫中有一個 [!DNL Analytics] (MCID)，便會發生此拼接。[!DNL Target] 通常也有MCID，但如果呼叫發生在訪客ID傳 [!DNL Target] 回之前，則點擊仍會因為SDID而縫合。同時，使用者必須維持在頁面上夠長的時間，才能在觸發 [!DNL Target] 呼叫之後觸發 [!DNL Analytics] 呼叫。這種情況是理想的。

**部分資料點擊:** 使用者有時不會維持在頁面上夠長的時間，因而無法傳送 [!DNL Analytics] 呼叫，但是 [!DNL Target] 會有正確的 MCID。此藍本會產生部分資料點擊（沒有[!DNL Analytics]頁面檢視的點擊）。 如果這些使用者返回您的網站並檢視包含[!DNL Analytics]程式碼的頁面，則會正確地計為舊訪客。 如果頁面上只有[!DNL Analytics]程式碼，這些點擊會遺失。 有些用戶端不想要這些點擊的資料，因為它們會讓某些度量 (造訪) 膨脹和讓其他度量 (每次造訪的頁面檢視、每次造訪時間等) 壓縮。您也會看到沒有任何頁面檢視的瀏覽。 不過，保留此資料仍有有效的原因。

為了將部分資料點擊最小化，您可以讓您的頁面載入更快，更新為最新版本的資料庫，或建立排除這些點擊的[虛擬報表套裝](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-workflow/vrs-create.html)。如需逐步指示，請參閱&#x200B;*Analytics元件指南*&#x200B;中的[建立虛擬報表套裝](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-workflow/vrs-create.html)。

下圖顯示虛擬報表套裝的區段定義:

![](assets/ts_a4t.png)

建立虛擬報表套裝時，指定區段定義的下列組態 (如上圖所示):

* **顯示點擊:**
* Analytics for Target: 已存在
* 和
* 頁面檢視: 不存在
* 和
* 自訂連結例項: 不存在
* 和
* 下載連結例項: 不存在
* 和
* 結束連結例項: 不存在

**孤立點擊:** 少數情況下，使用者未持在頁面上夠長的時間，使得 Analytics 呼叫和 Target 未取得正確的 MCID。這些點擊是Adobe定義為「孤立」點擊的點擊。 這些點擊代表的是客戶很少回來，以及他們不當地膨脹了造訪和訪客計數。

若要將這些「孤立」點擊最小化，您可以建立可排除這些點擊的[虛擬報表套裝](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-workflow/vrs-create.html)，如以上所述。

## 這對我的 [!DNL Target] 報表有何意義? {#section_AAD354C722BE46D4875507F0FCBA5E36}

發生此變更後，您可能會看到即時測試的新訪客和瀏覽次數減少，因為[!DNL Adobe]不會處理傳入的部分資料。 對其他 [!DNL Analytics] 量度的轉換和點擊將不會變更。
