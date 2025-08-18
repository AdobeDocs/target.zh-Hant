---
keywords: Analytics 追蹤伺服器;A4T;analytics 區段;報表套裝;不正確資料;孤立;sdid;VisitorAPI.js;mboxMCSDID;虛設;未指定
description: 探索客戶將 Analytics 用於 [!DNL Target] (A4T) 時經常遇到的問題。
title: 如何針對 Analytics 和 [!DNL Target] 整合 (A4T) 進行疑難排解
feature: Analytics for Target (A4T)
exl-id: 7d155cbe-e799-43b5-afc2-1aea43f432ba
source-git-commit: 0be54d82e25eb919102f6098c1b1db76ab291675
workflow-type: tm+mt
source-wordcount: '926'
ht-degree: 88%

---

# 針對 Analytics 和 [!DNL Target] 整合 (A4T) 進行疑難排解

此主題涵蓋使用 [!DNL Adobe Analytics] 當作 [!DNL Adobe Target] (A4T) 的報告來源時經常遇到的一些問題。

## 活動在 Analytics 中未顯示資料，而是列為「未指定」。 {#unspecified}

可能發生資料顯示為「未指定」的原因有幾個：

* [!DNL Target] 中的分類尚未完全處理。

  若要在第一次儲存後分類報表，通常需要 24 到 72 小時。

* 報表套裝不含任何資料，但 [!DNL Target] 已嘗試將點閱分類。[!DNL Target] 要直到第一次點閱發生時才能夠分類。

  確保報表套裝已至少有一次點閱。

* 從 [!DNL Target] 至 [!DNL Analytics] 的分類呼叫失敗。

  [請聯絡客戶服務](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)以取得協助。

如果您依據「Analytics for Target」維度劃分「未指定」列，而且它未包含任何活動 ID，則表示所有一切都已適當分類。 如果該處有列出活動 ID，則表示有分類問題。

>[!NOTE]
>
>資料有時在報表中正確顯示，但接著回復成「未指定」，因為增加的新活動尚未完成分類。請記住，若要在第一次儲存後分類報表，通常需要 24 到 72 小時。
>
>列為「未指定」時不會遺失任何資料。分類執行之後，資料會適當地指派給適當的活動或體驗。

## A4T 活動報告包含的一列有許多「未指定」事件。 {#added_unspecified_events}

根據顯示您的資料所使用的量度，報告中可能會顯示&quot;[!UICONTROL Unspecified]&quot;事件列。

一般來說，如果您在報表中選擇的常用量度不是[!DNL Target]所特有（例如，[!UICONTROL Page Views]、[!UICONTROL Visits]、[!UICONTROL Unique Visitors]等），就會顯示此列。 在此案例中，[!UICONTROL "Unspecified"]列包含未與[!UICONTROL Page Views]活動相關聯的所有[!UICONTROL Visits]、[!UICONTROL Unique Visitors]和[!DNL Target]。

該列不會有任何 [!DNL Target] 相關資訊 (例如，沒有訪客、造訪次數或曝光率)。如需詳細資訊，請參閱 *Analytics 技術備忘稿*&#x200B;中[報表中的「未指定」、「無」、「其他」和「未知」](https://experienceleague.adobe.com/docs/analytics/technotes/unspecified.html?lang=zh-Hant)。

如果您在報表中選擇特定於[!DNL Target]的量度，該[!UICONTROL "Unspecified"]列就不會顯示。 避免報表中出現此情況的唯一方式就是在從該頁面傳送的每個要求上設定 [!DNL Target] 呼叫，這既不常見，也非必要。

## 預估收入成長量度未顯示正確資料。 {#section_35D766E5E4D347C39E15D08AA883FBB0}

Analytics 中沒有提升度和可信度詳細資料。不過，在 Target 中有這些詳細資料。

## 活動未出現在 Analytics 報表中。 {#section_F7001EB4670F4B3497CC7DA60BBDA6D5}

A4T 活動需要您指定 Analytics 追蹤伺服器。請參閱[使用Analytics追蹤伺服器](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823)，以確定您的Analytics追蹤伺服器設定正確。

>[!NOTE]
>
>如果您使用 at.js 0.9.1 版 (或更新版本)，您在活動建立期間就不需要指定追蹤伺服器。 at.js 程式庫會自動傳送追蹤伺服器值給 [!DNL Target]。 在活動建立期間，您可以將[!UICONTROL Tracking Server]頁面上的[!UICONTROL Goals & Settings]欄位保留空白。

## 我的 Analytics 區段未出現在 Target 中。 {#section_DEE87F1557834F448E99381D3D02EEEF}

開啟建立 A4T 活動之前，請確定您具備正確權限:

* 您必須屬於 Adobe Analytics 中的「Web 服務存取」群組，才能使用 Analytics 作為 Target 的報告來源
* 您必須是具有 Analytics 和 Target 存取權的一或多個 Experience Cloud 群組的成員。
* 請確認 Analytics 和 Target 出現在左導覽的「行銷應用程式」區段中。

## 跳出率、跳出和離開量度在報表中顯示為正數。 {#section_B5C3D56EF0344407AE67ABEB93037F5A}

這些在報表中顯示為正值的量度為已知問題。

雖然這些量度為負數，但提升度會在 Target 報表中顯示為正數。例如，即便您想要較低的跳出率仍顯示了較高的跳出率，因為獲勝者會具有最高的提升度。根據報表進行決策時，請注意這些和類似的量度，以及是否您偏好減少或增加這些數字。

## 我需要的報表套裝未顯示。 {#section_BD8F956E41D6475B98B7BF0C74CC387C}

在 [!DNL Target Standard/Premium] 中出現的報表套裝清單，就是已設定 [!DNL Analytics] 當作 [!DNL Target] (A4T) 的報告來源的報表套裝清單。 您可能不會看到您擁有的每個報表套裝。

如果您正在使用多個報告來源，則在 [!DNL Target] 中設定的預設報告來源中也必須有報表套裝。 如果報表套裝不在預設報告來源中，則不會顯示報表套裝。

如果您還是沒看到您要尋找的報表套裝，請聯絡[客戶服務](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)來啟用它。

## 我在報表中看到的資料量不如預期。 {#section_75002584FA63456D8D9086172925DD8D}

檢閱您的實作，尤其是在訪客有資格體驗的頁面上，並確定 [!DNL Target] 和 [!DNL Analytics] 呼叫中的補充資料 ID 相符。

* **at.js 1.x**：在 [!DNL Target] 呼叫中，補充 ID 包含在 `mboxMCSDID` 參數中。 在 [!DNL Analytics] 呼叫中，補充 ID 包含在 `sdid` 參數中。
* **at.js 2.x**：在 [!DNL Target] 呼叫中，HTTP 標頭中會傳回補充 ID 當作 `experienceCloud.analytics.supplementalDataId` 的值。 在 [!DNL Analytics] 呼叫中，補充 ID 包含在 `sdid` 參數中。

檢查補充 ID 的最簡單方法就是使用 Adobe Experience Platform Debugger。

如果您尚未安裝此偵錯工具，請參閱 [Adobe Experience Platform Debugger 簡介](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/web-sdk/introduction-to-the-experience-platform-debugger.html?lang=zh-Hant)。

![Debugger](/help/main/c-integrating-target-with-mac/a4t/assets/debugger.png)

如果 [!DNL Target] 呼叫中沒有補充資料 ID，請確認 [!DNL VisitorAPI.js] 檔案是在 [!DNL at.js] 之前載入。 如果 [!DNL Analytics] 呼叫中沒有補充 ID，請確認 [!DNL Target] 呼叫在 [!DNL Analytics] 呼叫之前執行。

如需詳細資訊，請參閱 [Analytics for Target 實作](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md#concept_CE78750AC2A4487D8ACD9369B3EAC85A)，或聯絡[客戶服務](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)。
