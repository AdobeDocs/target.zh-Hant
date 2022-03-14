---
keywords: Analytics 追蹤伺服器;A4T;analytics 區段;報表套裝;不正確資料;孤立;sdid;VisitorAPI.js;mboxMCSDID;虛設;未指定
description: 瞭解客戶在使用Analytics時遇到的常見問題 [!DNL Target] (A4T)。
title: 如何排除分析故障和 [!DNL Target] 整合(A4T)
feature: Analytics for Target (A4T)
exl-id: 7d155cbe-e799-43b5-afc2-1aea43f432ba
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '987'
ht-degree: 39%

---

# 排除分析故障並 [!DNL Target] 整合(A4T)

本主題介紹使用時遇到的一些常見問題 [!DNL Adobe Analytics] 作為 [!DNL Adobe Target] (A4T)。

## 活動在 Analytics 中未顯示資料，而是列為「未指定」。 {#unspecified}

資料顯示為「未指定」的原因有幾個：

* [!DNL Target] 中的分類尚未完全處理。

   分類通常需要24到72小時，以便在第一次保存後對報告進行分類。

* 報表套裝不含任何資料，但 [!DNL Target] 已嘗試將點閱分類。[!DNL Target] 要直到第一次點閱發生時才能夠分類。

   確保報表套裝已至少有一次點閱。

* 從 [!DNL Target] 至 [!DNL Analytics] 的分類呼叫失敗。

   [請聯絡客戶服務](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)以取得協助。

如果按「目標分析」維分解「未指定」行，並且它不包含活動ID，則意味著所有內容都被正確分類。 如果活動ID列在此處，則它將作為分類問題的指示。

>[!NOTE]
>
>有時，資料會在報告中正確顯示，但隨後會恢復為「未指定」，因為添加了一個尚未完成分類的新活動。 請記住，在第一次保存報告後，通常需要24到72個小時對報告進行分類。
>
>列為「未指定」時不會遺失任何資料。分類執行之後，資料會適當地指派給適當的活動。

## A4T活動報告包含一個包含許多「未指定」事件的行。 {#added_unspecified_events}

可能有&quot;[!UICONTROL 未指定]&quot;報告中顯示的事件行，具體取決於用於顯示資料的度量。

通常，如果在報表中選擇的公用度量不是 [!DNL Target]-specific(例如， [!UICONTROL 頁面視圖]。 [!UICONTROL 訪問]。 [!UICONTROL 獨特訪問者]等)。 在這個例子中， [!UICONTROL &quot;未指定&quot;] 行包含所有 [!UICONTROL 頁面視圖]。 [!UICONTROL 訪問], [!UICONTROL 獨特訪問者] 與 [!DNL Target] 活動。

該行將沒有任何 [!DNL Target] — 關聯資訊（例如，沒有訪問者、訪問或印象）。 有關詳細資訊，請參見 [報告中的「未指定」、「無」、「其他」和「未知」](https://experienceleague.adobe.com/docs/analytics/technotes/unspecified.html?lang=en) 的 *分析技術說明*。

如果您選擇 [!DNL Target] — 特定的指標， [!UICONTROL &quot;未指定&quot;] 不顯示行。 唯一能避免報告中出現的辦法是設定 [!DNL Target] 從該頁發送的每個請求都需要呼叫，這並不常見，也不必要。

## 我的 Analytics資料顯示自啟動 A4T 以來抬高的造訪或訪客計數。 {#section_4BE374E573D44FB7918611699B74F58E}

如需詳細資訊，請參閱[在 A4T 中將膨脹後造訪和訪客計數最小化](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235)。

## 預估收入成長量度未顯示正確資料。 {#section_35D766E5E4D347C39E15D08AA883FBB0}

Analytics 中沒有提升度和可信度詳細資料。不過，在 Target 中有這些詳細資料。

## 活動未出現在 Analytics 報表中。 {#section_F7001EB4670F4B3497CC7DA60BBDA6D5}

A4T 活動需要您指定 Analytics 追蹤伺服器。請參閱 [使用分析跟蹤伺服器](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823) 以確保正確設定分析跟蹤伺服器。

>[!NOTE]
>
>如果使用at.js版本0.9.1（或更高版本），則在建立活動期間無需指定跟蹤伺服器。 at.js庫自動將跟蹤伺服器值發送到 [!DNL Target]。 在活動建立期間，您可以將[!UICONTROL 「目標與設定」]頁面上的[!UICONTROL 「追蹤伺服器」]欄位保留空白。

## 我的 Analytics 區段未出現在 Target 中。 {#section_DEE87F1557834F448E99381D3D02EEEF}

開啟建立 A4T 活動之前，請確定您具備正確權限:

* 屬於Adobe Analytics的Web服務訪問組，以便能夠將分析用作目標的報告源
* 成為一個或多個有權訪問分析和目標的Experience Cloud組的成員。
* 請確認 Analytics 和 Target 出現在左導覽的「行銷應用程式」區段中。

## 跳出率、跳出和離開量度在報表中顯示為正數。 {#section_B5C3D56EF0344407AE67ABEB93037F5A}

這些度量在報告中顯示為正值是已知問題。

雖然這些量度為負數，但提升度會在 Target 報表中顯示為正數。例如，即便您想要較低的跳出率仍顯示了較高的跳出率，因為獲勝者會具有最高的提升度。根據報表進行決策時，請注意這些和類似的量度，以及是否您偏好減少或增加這些數字。

## 我需要的報告套件不顯示。 {#section_BD8F956E41D6475B98B7BF0C74CC387C}

顯示在 [!DNL Target Standard/Premium] 是已為配置的報告套件的清單 [!DNL Analytics] 作為 [!DNL Target] (A4T)。 你可能看不到所有的報告套件。

如果使用多個報告源，則報告套件必須位於中的預設報告源集中 [!DNL Target] 也是。 如果報告套件不在預設報告源中，則不顯示報告套件。

如果您仍未看到要查找的報告套件，請聯繫 [客戶端保護](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) 來啟用它。

## 我在報表中看到的資料量不符預期。 {#section_75002584FA63456D8D9086172925DD8D}

檢閱您的實作，尤其是訪客有資格使用體驗的頁面，並確定 [!DNL Target] 和 [!DNL Analytics] 呼叫中的補充資料 ID 相符。

* **at.js 1.x**:在 [!DNL Target] 呼叫，補充ID包含在 `mboxMCSDID` 的下界。 在 [!DNL Analytics] 呼叫中，`sdid` 參數包含補充 ID。
* **at.js 2.x**:在 [!DNL Target] 調用時，在HTTP頭中返回補充ID作為 `experienceCloud.analytics.supplementalDataId`。 在 [!DNL Analytics] 呼叫中，`sdid` 參數包含補充 ID。

檢查補充ID的最簡單方法是使用Adobe Experience Platform調試器。

如果尚未安裝調試器，請參見 [Adobe Experience Platform調試器簡介](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/web-sdk/introduction-to-the-experience-platform-debugger.html)。

![除錯程式](/help/main/c-integrating-target-with-mac/a4t/assets/debugger.png)

如果中沒有補充資料ID [!DNL Target] 打電話，確認 [!DNL VisitorAPI.js] 檔案載入之前 [!DNL at.js]。 如果 [!DNL Analytics] 呼叫中沒有補充 ID，請確認 [!DNL Target] 呼叫在 [!DNL Analytics] 呼叫之前執行。

如需詳細資訊，請參閱 [Analytics for Target 實作](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md#concept_CE78750AC2A4487D8ACD9369B3EAC85A)，或聯絡[客戶服務](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)。
