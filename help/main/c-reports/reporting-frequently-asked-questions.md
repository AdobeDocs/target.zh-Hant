---
keywords: 疑難排解；量度差異；FAQ；報表；新訪客；新訪客；舊訪客；舊訪客；回訪；新造訪
description: 探索有關Adobe [!DNL Target] 報告的常見問答清單。
title: 哪裡可以找到有關 [!DNL Target] 報告的問題的解答？
feature: Reports
exl-id: 1a345a67-5050-4bd3-858d-99731d2c1dd3
source-git-commit: fe1e97710e7692ba7724103853ed7438c3f361b1
workflow-type: tm+mt
source-wordcount: '1367'
ht-degree: 20%

---

# 報表常見問題集

關於 [!DNL Adobe Target] 中報表常見問題的清單。

## 新訪客與回訪訪客量度如何計算？ {#methodology}

只要訪客在網站上處於作用中狀態，新訪客的首次造訪就會持續。
如果使用者閒置30分鐘或更長時間，工作階段會重設。 重設工作階段表示該訪客在下次造訪時成為回訪訪客，或在閒置30分鐘後再次變為使用中。
如果訪客在網站中一整天每29分鐘瀏覽一次，則此訪客即會計為當天的新訪客。 工作階段從未重設，因為訪客從未超過30分鐘的臨界值。

下列資訊將更詳細地說明新訪客和回訪訪客的計數方式。 同時也會舉例說明為何這兩個區段的總和並不一定等於訪客總數。

### 新訪客

如果符合下列條件之一，則訪客會包含在「新訪客」區段：

* 這是訪客第一次造訪網站。
* 這是訪客自 Cookie 清除後第一次造訪網站。
* 這是訪客自[訪客設定檔存留期](/help/main/c-target/c-visitor-profile/visitor-profile-lifetime.md)過期後第一次造訪網站。

### 再度訪問的訪客

如果使用者先前造訪網站，離開至少 30 分鐘，並使用相同的 Cookie 再次返回網站，則該訪客會納入「回訪訪客」區段。只要訪客在設定檔期限之內回來，就是回訪訪客。

假設您的設定檔存留期設定為14天（預設值）。 如果符合下列條件，則訪客會納入「回訪訪客」區段：

* 訪客首次造訪網站，系統會將其記錄為「新訪客」。
* 訪客離開網站，但六天後回訪。

由於設定檔存留期設為14天，因此此訪客會包含在「回頭客」區段中。 如果該訪客在六天內刪除了Cookie，則該訪客會包含在「新訪客」區段中。

### 說明量度計數之間差異的範例

**範例1**：如果將這兩個區段套用至活動，則「新訪客」區段和「再度訪問的訪客」區段並非總和訪客總數。

考量以下範例，接受上述新訪客和回訪訪客的條件：

* 訪客首次造訪網站，即計為新訪客。
* 當回訪訪客符合條件時，訪客即會返回網站，並計為回訪訪客。

在活動的整體訪客計數中，即使此訪客同時計入新訪客和回訪訪客區段，仍會計為單一訪客。

**範例2**：新訪客和回訪訪客計數之間的差異也取決於您設定活動[成功量度](/help/main/c-activities/r-success-metrics/success-metrics.md)的方式。

例如：

數個新訪客造訪您的網站，並符合活動的資格。 這些新訪客會計入「新訪客」區段。 所有這些訪客也記錄了該活動的造訪。

有些訪客點選轉換量度，該量度已設定為「增加計數以及讓使用者留在活動中」。 假設其中某些使用者多次點選轉換量度，轉換量度不會增加。 但是，進行此設定後，有些使用者可能會點選轉換量度，然後導覽回首頁，再次符合活動資格以記錄新的造訪。

## 我的[!UICONTROL Experience Targeting] (XT)報表為何包含控制體驗的量度？

XT 活動應一律都有控制體驗。如果您以類似[!UICONTROL A/B Test]活動（這是相當常見的案例）的方式使用XT活動，控制體驗資料會很實用。 如果您發現控制體驗資料在您的報表中並不實用，您可以將其忽略。

## [!DNL Target]中的造訪次數為何比其他[!DNL Adobe Experience Cloud]解決方案中的造訪次數低？ {#section_7E626FDB417E41B8B58BBF30FB207409}

由於下列原因，[!DNL Target]所報告的量度數字（例如造訪）一律低於其他[!DNL Experience Cloud]解決方案中所報告的數字：

* [!DNL Target] 只會計算活動合格訪客的造訪次數。其他解決方案會針對顯示頁面的訪客來計算造訪次數，而不在乎將他們帶到頁面的活動。
* 不同的活動有時會爭奪相同的位置 (互斥)。因此，訪客在網頁上會看到不同內容，因而影響 [!DNL Target] 所報告的量度數字。

## 活動的報表為何沒有資料可用? {#section_E4722F6445884130951DF79981C8289B}

如果活動的內容成功傳送給訪客，但其報表不含任何資料，您可能會看到下列錯誤訊息：「沒有可用於所選報表設定的資料。」

活動報表中遺失資料的可能原因如下：

* 您沒有在報告的設定中選取正確的環境
* 您沒有任何流量分配給控制體驗

### 您沒有在報表設定中選取正確的環境：

如果活動的內容成功傳送給使用者，但其報表不含任何資料，請確定您已在報表的設定中選取正確環境 ([主機群組](/help/main/administrating-target/hosts.md))。

若要變更活動報表的環境:

1. 按一下「**[!UICONTROL Activities]**」，從清單中按一下所需的活動，然後按一下「**[!UICONTROL Reports]**」標籤。
1. 按一下齒輪圖示進行報表設定。

   ![A/B 設定對話方塊](/help/main/c-reports/c-report-settings/assets/ab_settings_dialog.png)

1. 從&#x200B;**[!UICONTROL Environment]**&#x200B;下拉式清單中，選取&#x200B;**[!UICONTROL Production]**。

   如果您選取了開發環境，則可能沒有報表資料可用。

1. 按一下 **[!UICONTROL Save]**。

如需環境的詳細資訊，請參閱[主機](/help/main/administrating-target/hosts.md#concept_516BB01EBFBD4449AB03940D31AEB66E)。

### 您沒有任何流量分配給控制體驗

如果活動的內容成功傳送給使用者，但其報表不含任何資料，請確定您使用具有流量的體驗作為控制體驗。

1. 按一下「**[!UICONTROL Activities]**」，從清單中按一下所需的活動，然後按一下「**[!UICONTROL Reports]**」標籤。
1. 按一下齒輪圖示進行報表設定。

1. 從&#x200B;**[!UICONTROL Control]**&#x200B;下拉式清單中，選取接收流量的體驗。

1. 按一下 **[!UICONTROL Save]**。

>[!NOTE]
>
>如需有關如何更新[!UICONTROL Automated Personalization] (AP)活動以及將控制體驗變更為接收流量的體驗的詳細資訊，請參閱[選取Automated Personalization或自動鎖定目標活動的控制項](/help/main/c-activities/t-automated-personalization/experience-as-control.md)。


## 為什麼我的A/B或MVT活動中的體驗之間流量分割不平均？ {#uneven}

例如，我將流量分割設為50/50或25/25/25/25/25，但在報表中看到體驗之間的分佈大相逕庭。 [!DNL Target]報表中有幾個不平均訪客計數可解釋的原因：

* 首次啟動[!DNL Target]活動時，流量分佈可能會不平均，因為[!DNL Target]用來最佳化體驗傳遞的邊緣節點架構。 最佳實務是給予活動一些時間以收集更多資料，且分配將會正常化。 如需[!DNL Adobe Target]架構和Edge節點的詳細資訊，請參閱[Adobe Target運作方式](/help/main/c-intro/how-target-works.md)。
* 如果您在[!DNL Target]或[!DNL Analytics]，而且您使用&#x200B;**[!UICONTROL Visits]**&#x200B;量度，請記住[!DNL Target]是以訪客為基礎的系統，且A/B或MVT測試的流量分配是在訪客層級指派。 因此，如果您使用&#x200B;**[!UICONTROL Visits]**&#x200B;量度來檢查活動結果，流量分佈可能會呈現不平均的狀態，因為某些訪客可能會有多次造訪。 訪客是評估活動績效時的標準標準化量度。
* A/B和MVT測試的最佳實務是保持流量分割均勻。 在測試期間變更體驗之間的流量分佈（例如從90/10到50/50）可能會導致體驗之間的訪客不平均。 較低的流量體驗可能永遠無法「趕上」。
* 如果您遵循上述最佳實務，且流量分割不會隨著時間正常化，您應檢查下列專案：

   * 您使用最新的at.js資料庫嗎？ 如需目前版本和相關發行說明的詳細資訊，請參閱[at.js版本詳細資料](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=zh-Hant){target=_blank}。

   * 這是重新導向測試嗎？ 標籤在頁面上引發的時間不正確會導致不平均的流量分割，尤其是在使用[!DNL Analytics]做為[!DNL Target]活動的資料來源時。 如需使用Analytics for Target (A4T)修正重新導向活動上不平均流量分佈的詳細資訊，請參閱[重新導向選件 — A4T常見問題集](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md)。
