---
keywords: 部分資料;A4T;差異;analytics for target;孤立;虛擬報表套裝;虛設項目;疑難排解;未拼接;膨脹;未指定
description: 瞭解如何在使用Analytics for [!DNL Target] (A4t)。 瞭解「部分資料」是什麼以及如何減少它。
title: 如何在A4T中最大限度地減少虛假訪問和訪問者人數？
feature: Analytics for Target (A4T)
exl-id: 308711f7-e630-4f6b-8a6d-a1f36ed7902d
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1341'
ht-degree: 47%

---

# 在 A4T 中將膨脹的造訪和訪客計數減到最少

幫助您在使用時最大限度地減少虛假訪問和訪問者數量的影響的資訊 [!DNL Adobe Analytics] 作為 [!DNL Adobe Target] (A4T)。

>[!IMPORTANT]
>在 2016 年 11 月 14 日，Adobe Analytics 已針對 Target 使用 Analytics 報表 (A4T) 的客戶變更部分資料的處理方式。這些變更讓 Adobe Target 資料更能與 Adobe Analytics 的資料模型對應。這些變更已對使用 A4T 的所有客戶展開。這些變更特別能解決在執行 Target 活動時，有些客戶所注意到膨脹的訪客計數的問題。
>
>此變更不溯及既往。如果您的歷史報表顯示膨脹的計數，而您想要將它們從報表中排除，您可以建立虛擬報表套裝，如下所示。
>
>此外，還更新了幾個JavaScript庫，以幫助最大限度地減少虛數。 Adobe建議您升級到以下庫版本（或更新版本）:
>
>* Experience Cloud 訪客 ID 服務: visitorAPI.js 版本 2.3.0 或更新版本。
>* Adobe Analytics: appMeasurement.js 版本 2.1。
>* Adobe Target: at.js 0.9.6 版或更新版本 (若 A4T 使用重新導向選件，則不包括 1.1.0 版)。


## 哪些部分有所變更? {#section_9CCF45F5D66D48EBA88F3A178B27D986}

當 [!DNL Adobe Analytics] 用於度量 [!DNL Target] 活動（稱為A4T）, [!DNL Analytics] 收集在沒有 [!DNL Target] 的子菜單。 的 [!DNL Target] 活動在頁面頂部觸發呼叫，但 [!DNL Analytics] 通常在頁面底部觸發其資料收集調用。 在A4T至今的實施中，Adobe在 [!DNL Target] 活動處於活動狀態。 展望未來，Adobe僅在 [!DNL Target] 和 [!DNL Analytics] 標籤已觸發。

## Adobe 為何做出此變更? {#section_92380A4BD69E4B8886692DD27540C92A}

Adobe 對於自己的資料準確性和品質感到自豪。當 [!DNL Target] 標籤會觸發，但 [!DNL Analytics] 標籤不會，Analytics會記錄「部分資料」（有時稱為「未縫合命中」）。 這些未縫合的命中不會被 [!DNL Analytics] 如果沒有 [!DNL Target] 的子菜單。 儘管將此部分資料 [!DNL Analytics] 報告提供額外資料，亦與沒有歷史資料 [!DNL Target] 活動正在運行。 此情況可能導致 [!DNL Analytics] 分析隨時間推移的趨勢的用戶。 為了確保資料一致性 [!DNL Analytics],Adobe排除所有部分資料。

## 是什麼造成了部分資料? {#section_C9C906BEAA7D44DAB9D3C03932A2FEB8}

Adobe在中遇到部分資料速率較高的客戶 [!DNL Analytics]。 部分資料的高速率可能是由於實施不當造成的，但也有合理的原因。

部分資料經確認的原因包括下列:

* **不相符的報表套裝 ID (實作):** 在活動設定指定的報表套裝不符合傳送測試所在頁面上的報表套裝。無法對資料進行協調 [!DNL Analytics] 伺服器，所以它看起來是部分資料。
* **慢速頁面：** [!DNL Target] 呼叫位於頁面的頂部 [!DNL Analytics] 呼叫通常位於頁面底部。 如果頁面載入緩慢，則會增加訪問者在 [!DNL Target] 呼叫失火，但在 [!DNL Analytics] 呼叫。 在連接速度通常較慢的移動網站上，慢速頁面可能會特別成問題。
* **頁面錯誤：** 如果存在JavaScript錯誤或每個觸點都未觸發的其他情形(Experience CloudID服務、目標和分析)，則會顯示部分資料結果。
* **重定向服務 [!DNL Target] 活動：** 對於使用A4T的活動中的重定向服務，您的實施必須滿足某些最低要求。 另外，還有重要的資訊，你必須知道。 如需詳細資訊，請參閱[重新導向選件 - A4T 常見問題集](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#section_FA9384C2AA9D41EDBCE263FFFD1D9B58)。
* **舊版本的庫：** 在過去一年中，Adobe對JavaScript庫進行了幾項改進( [!DNL appMeasurement.js]。 `at.js`, `visitorAPI.js`)以確保盡可能高效地發送資料。 若要進一步瞭解實作需求，請參閱[實作之前](/help/main/c-integrating-target-with-mac/a4t/before-implement.md#concept_046BC89C03044417A30B63CE34C22543)。

## 減少部分資料的最佳做法為何? {#section_065C38501527451C8058278054A1818D}

查看以下步驟以減少部分資料收集：

| 步驟 | 任務 |
| --- | --- |
| ![步驟 1](assets/step1_icon.png) | 確保在中選擇的報告套件 [!DNL Target] 與顯示活動的頁面上的相同。 |
| ![步驟 2](assets/step2_icon.png) | 確保visitorAPI.js、appMeasurement.js和at.js庫在與A4T相容的版本上。 若要進一步瞭解實作需求，請參閱[實作之前](/help/main/c-integrating-target-with-mac/a4t/before-implement.md)。 |
| ![步驟 3](assets/step3_icon.png) | 確保SDID已全部設定 [!DNL Target] 和 [!DNL Analytics] 離開頁面的電話，並且它們匹配。<br/>使用網路分析器或調試工具確保 `mboxMCSDID` 參數 [!DNL Target] 調用與SDID參數 [!DNL Analytics] 呼叫。 |
| ![步驟 4](assets/step4_icon.png) | 確認實作資料庫在您的網站上以正確的順序載入網站。如需詳細資訊，請參閱 [Analytics 用於 Target 的實作](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md)。 |

## 我如何知道我有多少部分資料? {#section_89B663E2824A4805AB934153508A0F4B}

雖然此資訊無法直接在 [!DNL Analytics] 中取得，您可以聯絡 Adobe 客戶服務來擷取「部分資料」報表。此報表用意在協助偵錯。

## 我如何檢視沒有部分資料的歷史趨勢? {#section_4C9DED560FAD4428B362DDA2064897C3}

此處理更改僅影響發佈日期（2016年11月14日）後的資料。 如果要調整歷史度量以匹配，Adobe建議您建立一個段以排除部分資料。

與此變更相關的下列資訊包含的指示可幫助您定義區段和將區段套用至虛擬報表套裝，使得此區段一律會套用至您的 [!DNL Analytics] 檢視。

在多數情況下，一個 [!DNL Target] 點擊會與每個網頁上的一個 [!DNL Analytics] 點擊拼接。如果 [!DNL Target] 和 [!DNL Analytics] 呼叫中同時有一個一致的 SDID，且相同頁面上的 [!DNL Experience Cloud ID] 呼叫中有一個 [!DNL Analytics] (MCID)，便會發生此拼接。[!DNL Target] 通常也有MCID，但如果 [!DNL Target] 在訪問者ID返回之前，由於SDID，仍然會縫製該命令。 同時，使用者必須維持在頁面上夠長的時間，才能在觸發 [!DNL Target] 呼叫之後觸發 [!DNL Analytics] 呼叫。這種情景是理想的。

**部分資料點擊:** 使用者有時不會維持在頁面上夠長的時間，因而無法傳送 [!DNL Analytics] 呼叫，但是 [!DNL Target] 會有正確的 MCID。此方案導致部分資料命中（無命中） [!DNL Analytics] 頁面)。 如果這些用戶返回您的站點並查看包含 [!DNL Analytics] 密碼，他們被恰當地算作返程遊客。 如果你只是 [!DNL Analytics] 頁碼。 有些用戶端不想要這些點擊的資料，因為它們會讓某些度量 (造訪) 膨脹和讓其他度量 (每次造訪的頁面檢視、每次造訪時間等) 壓縮。您還可以看到沒有任何頁面視圖的訪問。 不過，保留此資料仍有有效的原因。

為了將部分資料點擊最小化，您可以讓您的頁面載入更快，更新為最新版本的資料庫，或建立排除這些點擊的[虛擬報表套裝](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-workflow/vrs-create.html)。有關逐步說明，請參見 [建立虛擬報告套件](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-workflow/vrs-create.html) 的 *分析元件指南*。

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

**孤立點擊:** 少數情況下，使用者未持在頁面上夠長的時間，使得 Analytics 呼叫和 Target 未取得正確的 MCID。這些點擊是Adobe所定義的「孤立」點擊。 這些點擊代表的是客戶很少回來，以及他們不當地膨脹了造訪和訪客計數。

若要將這些「孤立」點擊最小化，您可以建立可排除這些點擊的[虛擬報表套裝](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-workflow/vrs-create.html)，如以上所述。

## 這對我的 [!DNL Target] 報表有何意義? {#section_AAD354C722BE46D4875507F0FCBA5E36}

一旦發生這種變化，您可能會看到新訪問者和現場test訪問的減少，因為 [!DNL Adobe] 不處理傳入的部分資料。 對其他 [!DNL Analytics] 量度的轉換和點擊將不會變更。
