---
keywords: Analytics 追蹤伺服器;A4T;analytics 區段;報表套裝;不正確資料;孤立;sdid;VisitorAPI.js;mboxMCSDID;虛設;未指定
description: 探索客戶在使用Analytics for [!DNL Target] (A4T)時遇到的常見問題。
title: 如何疑難排解Analytics和 [!DNL Target] 整合(A4T)
feature: Analytics for Target (A4T)
exl-id: 7d155cbe-e799-43b5-afc2-1aea43f432ba
source-git-commit: 3c79b2ce70e456275ddf6774a35ae5c36f0ae99d
workflow-type: tm+mt
source-wordcount: '992'
ht-degree: 39%

---

# 疑難排解Analytics和[!DNL Target]整合(A4T)

本主題涵蓋使用[!DNL Adobe Analytics]做為[!DNL Adobe Target](A4T)的報表來源時遇到的一些常見問題。

## 活動在 Analytics 中未顯示資料，而是列為「未指定」。 {#unspecified}

資料顯示為「未指定」的可能原因有幾個：

* [!DNL Target] 中的分類尚未完全處理。

   分類通常需要24到72小時，才能在首次儲存後分類報表。

* 報表套裝不含任何資料，但 [!DNL Target] 已嘗試將點閱分類。[!DNL Target] 要直到第一次點閱發生時才能夠分類。

   確保報表套裝已至少有一次點閱。

* 從 [!DNL Target] 至 [!DNL Analytics] 的分類呼叫失敗。

   [請聯絡客戶服務](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)以取得協助。

如果您以「Analytics for Target」維度來劃分「未指定」列，且其中不包含活動ID，表示所有項目皆已正確分類。 如果活動ID列於此處，則會表示分類問題。

>[!NOTE]
>
>資料有時在報表中正確顯示，但接著回復為「未指定」，因為新增的活動尚未完成分類。 請記住，在首次儲存後分類報表通常需要24到72小時。
>
>列為「未指定」時不會遺失任何資料。分類執行之後，資料會適當地指派給適當的活動。

## A4T活動報表包含一列，內含許多「未指定」事件。 {#added_unspecified_events}

報表中可能會顯示「[!UICONTROL 未指定]」事件列，具體取決於您用來顯示資料的量度。

如果您在報表中選擇非特定[!DNL Target]的通用量度（例如[!UICONTROL 頁面檢視]、[!UICONTROL 造訪]、[!UICONTROL 獨特訪客]等），通常會顯示此列。 在此案例中，[!UICONTROL &quot;Unspecified&quot;]列包含所有未與[!DNL Target]活動相關聯的[!UICONTROL 頁面檢視]、[!UICONTROL 造訪]和[!UICONTROL 獨特訪客]。

該列不會有任何與[!DNL Target]相關的資訊（例如沒有訪客、造訪或曝光數）。 如需詳細資訊，請參閱&#x200B;*Analytics技術說明*&#x200B;中報表](https://experienceleague.adobe.com/docs/analytics/technotes/unspecified.html?lang=en)中的[「未指定」、「無」、「其他」和「未知」。

若您在報表中選擇[!DNL Target]特定量度，則不會顯示[!UICONTROL &quot;未指定&quot;]列。 要完全避免在報表中包含呼叫，唯一的方法是對從該頁面傳送的每個請求設定[!DNL Target]呼叫，這是不常見或必要的。

## 我的 Analytics資料顯示自啟動 A4T 以來抬高的造訪或訪客計數。 {#section_4BE374E573D44FB7918611699B74F58E}

如需詳細資訊，請參閱[在 A4T 中將膨脹後造訪和訪客計數最小化](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235)。

## 預估收入成長量度未顯示正確資料。 {#section_35D766E5E4D347C39E15D08AA883FBB0}

Analytics 中沒有提升度和可信度詳細資料。不過，在 Target 中有這些詳細資料。

## 活動未出現在 Analytics 報表中。 {#section_F7001EB4670F4B3497CC7DA60BBDA6D5}

A4T 活動需要您指定 Analytics 追蹤伺服器。請參閱  [使用Analytics追蹤](/help/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823) 伺服器，以確定您的Analytics追蹤伺服器設定正確。

>[!NOTE]
>
>如果您使用at.js版本0.9.1（或更新版本），則無需在活動建立期間指定追蹤伺服器。 at.js程式庫會自動傳送追蹤伺服器值至[!DNL Target]。 在活動建立期間，您可以將[!UICONTROL 「目標與設定」]頁面上的[!UICONTROL 「追蹤伺服器」]欄位保留空白。

## 我的 Analytics 區段未出現在 Target 中。 {#section_DEE87F1557834F448E99381D3D02EEEF}

開啟建立 A4T 活動之前，請確定您具備正確權限:

* 屬於Adobe Analytics中的「網站服務存取」群組，可以使用Analytics做為Target的報表來源
* 成為可存取Analytics和Target的一或多個Experience Cloud群組的成員。
* 請確認 Analytics 和 Target 出現在左導覽的「行銷應用程式」區段中。

## 跳出率、跳出和離開量度在報表中顯示為正數。 {#section_B5C3D56EF0344407AE67ABEB93037F5A}

這些量度在報表中顯示為正數是已知問題。

雖然這些量度為負數，但提升度會在 Target 報表中顯示為正數。例如，即便您想要較低的跳出率仍顯示了較高的跳出率，因為獲勝者會具有最高的提升度。根據報表進行決策時，請注意這些和類似的量度，以及是否您偏好減少或增加這些數字。

## 我需要的報表套裝不會顯示。 {#section_BD8F956E41D6475B98B7BF0C74CC387C}

[!DNL Target Standard/Premium]中顯示的報表套裝清單是已針對[!DNL Analytics]設定為[!DNL Target](A4T)的報表來源的報表套裝清單。 您可能看不到每個報表套裝。

如果您使用多個報表來源，報表套裝也必須位於[!DNL Target]中設定的預設報表來源中。 如果報表套裝不在預設的報表來源中，則不會顯示報表套裝。

如果您仍未看見所尋找的報表套裝，請連絡[客戶服務](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)以啟用它。

## 我在報表中看到的資料量不符預期。 {#section_75002584FA63456D8D9086172925DD8D}

檢閱您的實作，尤其是訪客有資格使用體驗的頁面，並確定 [!DNL Target] 和 [!DNL Analytics] 呼叫中的補充資料 ID 相符。

* **at.js 1.x**:在呼 [!DNL Target] 叫中，參數包含補充 `mboxMCSDID` ID。在 [!DNL Analytics] 呼叫中，`sdid` 參數包含補充 ID。
* **at.js 2.x**:在呼 [!DNL Target] 叫中，增補ID會在HTTP標題中傳回，作為的 `experienceCloud.analytics.supplementalDataId`值。在 [!DNL Analytics] 呼叫中，`sdid` 參數包含補充 ID。

要檢查補充ID，最簡單的方式是使用Adobe Experience Platform Debugger。

如果您尚未安裝除錯程式，請參閱[Adobe Experience Platform除錯程式簡介](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/web-sdk/introduction-to-the-experience-platform-debugger.html)。

![除錯程式](/help/c-integrating-target-with-mac/a4t/assets/debugger.png)

如果[!DNL Target]呼叫中沒有補充ID，請確認[!DNL VisitorAPI.js]檔案是在[!DNL at.js]之前載入。 如果 [!DNL Analytics] 呼叫中沒有補充 ID，請確認 [!DNL Target] 呼叫在 [!DNL Analytics] 呼叫之前執行。

如需詳細資訊，請參閱 [Analytics for Target 實作](/help/c-integrating-target-with-mac/a4t/a4timplementation.md#concept_CE78750AC2A4487D8ACD9369B3EAC85A)，或聯絡[客戶服務](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)。
