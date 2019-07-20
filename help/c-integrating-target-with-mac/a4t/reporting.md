---
description: 使用 Analytics 做為您的 Target (A4T) 報表來源，可讓您存取 Target 活動的 Analytics 報表。
keywords: Analytics for Target;A4T;使用 Analytics 作為報表來源
seo-description: 使用 Analytics 做為您的 Target (A4T) 報表來源，可讓您存取 Target 活動的 Analytics 報表。
seo-title: A4T 報表
solution: Target
subtopic: 多變數測試
title: A4T 報表
topic: Standard
uuid: bd3a7fa4-ba45-4ea3-81b6-fc2584831ce4
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# A4T 報表{#a-t-reporting}

使用 Analytics 做為您的 Target (A4T) 報表來源，可讓您存取 Target 活動的 Analytics 報表。

在 Analytics 和 Target Standard/Premium 中，您都可以檢視活動的報表。

如需使用 Analytics for Target 的報表最佳實務，[請瀏覽此 Adobe Spark Page](https://spark.adobe.com/page/Lo3Spm4oBOvwF/)。

## 概述 {#section_035A62D65608423285D8A5A54731E2C5}

Analytics 和 Target 報表都會測量加入者 (加入測試的人)，而不是來到網站的訪客。

每次有訪客在頁面上看到活動內容時，Target 就會對 Analytics 發出直接的伺服器對伺服器呼叫，包括訪客看過什麼活動和體驗。每當進行轉換時，Target 也會呼叫 Analytics。Analytics 會將轉換新增為特定的 Analytics 新事件，名稱為「活動轉換」，將會連同 Analytics 收集的其他資料一起追蹤此事件。

使用「選取」操作並排序&#x200B;*加入者*&#x200B;時，只有在所選時段接收到加入者的體驗才會出現在報表中。

>[!NOTE]
>
>Target 支援的報表會延遲四分鐘。對於 A4T 支援的活動，在 Target 和 Analytics 報表中，活動初次儲存之後最多需要 24 小時，才能依體驗來分析報表資料。在這最初 24 小時收集的資料仍然正確，且會指派給正確的體驗。

## Analytics 中的報表 {#section_F6884872DC864AE7913587FAED4CD11C}

在 Analytics 中，按一下左側功能表中的&#x200B;**[!UICONTROL 「Target]** &gt; **[!UICONTROL Target 活動」]**。在 Target 中，活動的報表會自動顯示 Analytics 資料、量度和區段。從網站收集資料後，大約一小時後資料就會出現在這些報表中。報表中的所有量度、對象和值，來自於您設定活動時所選取的報表套裝。

在 Analytics 中，使用「Target 活動」報表來檢視 Target 活動的結果。Test&amp;Target (舊版) 報表提供舊版 Test&amp;Target 外掛程式樣式頁面整合的相關資訊，不含 Analytics for Target 資料。在「活動」報表中，檢視 Target 體驗的相關資訊。按一下&#x200B;**[!UICONTROL 「量度」]**，然後選取 **Target]量度類型。[!UICONTROL **&#x200B;有兩個量度可用於報表:

* **活動項目:**&#x200B;會在 Target 報表中比對「加入者」數目。
* **活動轉換:**&#x200B;會在 Target 報表中比對「自訂轉換」次數。

>[!NOTE]
>
>Analytics 中也提供 Target 提升度和信賴度詳細資料。如需詳細資訊，請參閱 Adobe Analytics 產品說明文件中的 [Target 提升度和信賴度報表類型](https://marketing.adobe.com/resources/help/en_US/reference/report_target_lift_confidence.html)。

>[!IMPORTANT]
>
>如果 Analytics 中的「Target 活動」報表列出「未指定」，而非列出您的活動，則需要更新您的佈建帳戶。請聯絡客戶服務以解決此問題。

## Target 中的報表 {#section_C0D1F17F88374B6690BF904D7B83B42E}

使用 Analytics 作為報表來源時，Target Standard 中的報表會顯示從 Analytics 收集的資料。此報表與其他 Target Standard 報表稍微不同:

* 「對象」清單會顯示可用於 Analytics 報表套裝的對象。
* 「量度」清單會顯示可透過 Analytics 使用的每個量度。

   每個量度都可用，包括 Analytics 內建的任何自訂量度或計算量度。

   請注意，任何增加的數字在報表中都顯示為正數，即使您其實不希望增加也一樣。例如，即便您想要較低的跳出率仍顯示了較高的跳出率，因為獲勝者會具有最高的提升度。根據報表進行決策時，請注意這些和類似的量度，以及是否您偏好減少或增加這些數字。

在 Target 中，您可以在測試開始後，甚至在測試完成後，將量度或對象套用至報表。您事先完全不需要知道要測量什麼。

從活動報表頁面直接按一下，即可檢視完整的 Analytics 報表。

## Analysis Workspace 中的報表 {#reports-in-analysis-workspace}

您可以使用 [!DNL Adobe Analysis Workspace] 更進一步深入瞭解並以視覺化方式呈現資料，或發掘隱藏於表面下的分析。

For detailed information and examples, open the [Analytics &amp; Target: Best Practices for Analysis tutorial](https://spark.adobe.com/page/Lo3Spm4oBOvwF/), provided by Adobe Experience League.

## 活動建立 {#section_311586E3FF5541E7A91D1A3CE5F9ACE3}

在建立活動期間，您必須在[!UICONTROL 「設定」]頁面上指定活動的目標。此目標會成為報表的預設量度，且一律列為量度選取器的第一個選項。您無法像一般 Target 活動一樣選取要報告的區段。利用 Analytics 來測試會使用 Adobe Analytics 區段，而不是 Target Standard 對象。

## 執行 Analytics for Target (A4T) 的離線計算{#section_33A97A691F3A45D497DAF57A844388F0}

您可以為 A4T 執行離線計算，但是它需要在 [!DNL Analytics] 中進行資料匯出的步驟。

如需詳細資訊，請參閱[對 Analytics for Target (A4T) 執行離線計算](../../c-reports/conversion-rate.md#concept_0D0002A1EBDF420E9C50E2A46F36629B)。
