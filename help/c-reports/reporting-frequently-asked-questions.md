---
keywords: troubleshooting;metric discrepancies;FAQ;reports;new visitor;new visitors;returning visitor;returning visitors;return visit;new visit
description: 關於 Adobe Target 中報表常見問題集的清單。
title: Adobe Target 的報表常見問題集
topic: Standard
uuid: 0be40d3f-3274-493d-899b-cb7bb3612baf
translation-type: tm+mt
source-git-commit: 9229a2b6e17d7a340e7c8fb5f2c144cff1804e9e
workflow-type: tm+mt
source-wordcount: '983'
ht-degree: 35%

---


# 報表常見問題集{#reporting-faq}

關於 [!DNL Target] 中報表常見問題的清單。

## 「新訪客」和「舊訪客」量度的計數方式為何？

考慮以下事項:

**新訪客**: 如果符合下列條件之一，則「新訪客」區段會包含訪客：

* 這是訪客首次造訪網站。
* 這是訪客自清除Cookie後第一次造訪網站。
* 這是訪客自訪客描述檔存留期過期以來，首次 [造訪網站](/help/c-target/c-visitor-profile/visitor-profile-lifetime.md) 。

**舊訪客**: 如果使用者先前瀏覽網站，離開至少30分鐘，並使用相同的Cookie再次返回網站，則該訪客會納入「舊訪客」區段。 只要訪客在設定檔存留期之內回來，就是再度訪問的訪客。

如果這兩個區段套用至活動，「新訪客」區段和「舊訪客」區段不一定總會加總訪客數。

考慮到上述新訪客和舊訪客的條件，請考慮下列範例：

* 訪客首次瀏覽網站，並計為新訪客。
* 在符合舊訪客的條件並計為舊訪客後，訪客會返回網站。

即使此訪客同時計入「新訪客」和「舊訪客」區段，在活動的整體訪客計數中仍會被計為單一訪客。

「新訪客」和「舊訪客」計數的差異，也取決於您如何設定活動的成 [功度量](/help/c-activities/r-success-metrics/success-metrics.md):

考量下列範例:

許多新訪客瀏覽您的網站並符合活動資格。 這些新訪客會計入「新訪客」區段。 所有這些訪客也記錄了該活動的瀏覽。

有些訪客點擊轉換量度，此量度已設定為「增量計數、釋放使用者並允許再入」。 假設其中有些使用者多次點擊轉換度量，轉換度量不會增加。 不過，若有設定，有些使用者可能會點擊轉換度量，然後返回首頁，再次符合活動資格以記錄新的瀏覽。

## 我的 [!UICONTROL 體驗鎖定目標] (XT) 報表為何包含控制體驗的量度?

XT 活動應一律都有控制體驗。如果您以類似 [!UICONTROL A/B 測試]活動 (這是相當常見的案例) 的方式使用 XT 活動，控制體驗資料會很實用。如果您發現控制體驗資料在您的報表中並不實用，您可以將其忽略。

## [!DNL Target] 中的造訪次數為何比其他 [!DNL Adobe Experience Cloud] 解決方案中還要低? {#section_7E626FDB417E41B8B58BBF30FB207409}

由於下列原因，[!DNL Target] 所報告的量度數字 (例如造訪) 一律低於其他 [!DNL Experience Cloud] 解決方案中所報告的數字:

* [!DNL Target] 只會計算活動合格訪客的造訪次數。其他解決方案會針對顯示頁面的訪客來計算造訪次數，而不在乎將他們帶到頁面的活動。
* 不同的活動有時會爭奪相同的位置 (互斥)。因此，訪客在網頁上會看到不同內容，因而影響 [!DNL Target] 所報告的量度數字。

## 活動的報表為何沒有資料可用? {#section_E4722F6445884130951DF79981C8289B}

如果活動的內容成功傳送給使用者，但其報表不含任何資料，請確定您已在報表的設定中選取正確環境 ([主機群組](/help/administrating-target/hosts.md))。

如果您已選取開發環境，可能會看到下列錯誤訊息:「沒有可用於所選報表設定的資料」。

若要變更活動報表的環境:

1. 按一下&#x200B;**[!UICONTROL 「活動」]**，從清單中按一下所需的活動，然後按一下&#x200B;**[!UICONTROL 「報表」]**&#x200B;標籤。
1. 按一下齒輪圖示進行報表設定。

   ![A/B 設定對話方塊](/help/c-reports/c-report-settings/assets/ab_settings_dialog.png)

   >[!NOTE]
   >
   >[!UICONTROL 自動個人化] (AP) 報表沒有齒輪圖示可用。

1. 從&#x200B;**[!UICONTROL 「環境」]**&#x200B;下拉式清單中，選取&#x200B;**[!UICONTROL 「生產」]**。

   如果您選取了開發環境，則可能沒有報表資料可用。

1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

如需環境的詳細資訊，請參閱[主機](../administrating-target/hosts.md#concept_516BB01EBFBD4449AB03940D31AEB66E)。

## 為什麼我的A/B或MVT活動中體驗之間的流量分割不均？ {#uneven}

例如，我將流量分割設為50/50或25/25/25/25，但我發現報告中體驗之間的分佈大不相同。 報告中有許多可說明的訪客計數不一的 [!DNL Target] 原因：

* 首次啟 [!DNL Target] 動活動時，由於使用邊緣節點架構來最佳化體驗傳遞，流量分 [!DNL Target] 布可能不均勻。 最佳實務是讓活動有時間收集其他資料，然後散發就會標準化。 如需有關架構和 [!DNL Adobe Target] Edge節點的詳細資訊，請參 [閱Adobe Target的運作方式](/help/c-intro/how-target-works.md)。
* 如果您在或 [!DNL Target][!DNL Analytics] 且使用「瀏覽」度量，請記住，這 ****[!DNL Target] 是以訪客為基礎的系統，A/B或MVT測試的流量分佈會指派給訪客層級。 因此，如果您使用「瀏覽」度量檢查活 **[!UICONTROL 動結果]** ，則流量分佈可能會不均勻，因為某些訪客可能有多次瀏覽。 訪客是評估活動效能時的標準標準化度量。
* A/B和MVT測試的最佳實務是讓流量分割保持均勻。 在測試期間變更體驗之間的流量分佈（例如從90/10變更為50/50），可能會導致不同體驗的訪客不均衡。 較低的流量體驗可能永遠無法「趕上」。
* 如果您遵循上述最佳實務，且流量分割不會隨著時間而標準化，您應檢查下列項目：

   * 您使用最新的at.js程式庫嗎？ 如需目前版本和相關發行說明的詳細資訊，請參 [閱at.js版本詳細資訊](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)。

   * 是重新導向測試嗎？ 頁面上觸發標籤的時間不正確可能導致不均勻的流量分割，尤其是當使 [!DNL Analytics] 用作活動的資料來源時 [!DNL Target] 。 如需使用Analytics for Target(A4T)修正重新導向活動上不均衡流量分配的詳細資訊，請參閱重新導向選 [件- A4T常見問答](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md)。
