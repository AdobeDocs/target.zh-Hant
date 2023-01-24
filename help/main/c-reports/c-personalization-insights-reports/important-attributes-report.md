---
keywords: 鎖定目標;AP 報表;自動個人化報表;自動鎖定目標;自動鎖定目標報表;個人化;前瞻分析;faq;常見問題集; 重要屬性
description: 了解如何使用 [!UICONTROL 重要屬性] 顯示影響個人化模型的排名最前屬性及其相對重要性的報表。
title: 什麼是「重要屬性」報表？
feature: Reports
exl-id: c1069ca7-e221-4865-a82e-6cff5b4c0055
source-git-commit: 33d85fcbfc971c188f4154cca5b4d21103b4dbb7
workflow-type: tm+mt
source-wordcount: '1724'
ht-degree: 79%

---

# ![PREMIUM](/help/main/assets/premium.png) 「重要屬性」報表

關於 [!UICONTROL 重要屬性] 報告，供 [!UICONTROL Automated Personalization] （美聯社）和 [!UICONTROL 自動鎖定目標] (AT)活動。

>[!NOTE]
>
>使用 [!UICONTROL 個人化前瞻分析] 報表：
>
>* AP 和 AT 活動是 [!DNL Target Premium] 解決方案內建的功能。若沒有 [!DNL Target Standard] 授權，[!DNL Target Premium] 便未隨附這些解決方案。
>
>* [!UICONTROL 「個人化前瞻分析」報表僅適用於使用轉換最佳化目標的 AP 與 AT 活動。]也不支援最佳化目標在活動上線後已從收入變更為轉換的活動。
>
>* [!UICONTROL 個人化前瞻分析] 只有在 [!UICONTROL 主要目標] 從 [!UICONTROL 報表量度] 下拉式清單。
>
>* 「個人化前瞻分析」報表僅支援於[預設環境](/help/main/administrating-target/hosts.md)中使用。
>
>* [!UICONTROL 個人化前瞻分析] 報表只會針對 [!UICONTROL 即時] 狀態和已啟用且已接收至少15天的流量。


在不同的活動中，不同屬性對於模型決定個人化的方式或多或少都有不同的重要性。此報表顯示影響模型及其相對重要性的常見屬性。

## 存取 [!UICONTROL 重要屬性] 報告 {#section_8E8F997AAAF44A1B9EE06EB6FB652801}

1. 按一下 **[!UICONTROL 活動]**，然後按一下所需的 [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9) 或 [自動鎖定目標](/help/main/c-activities/auto-target/auto-target-to-optimize.md) 活動。

   如果您有許多活動，您可以利用從[!UICONTROL 「類型」]、[!UICONTROL 「狀態」]、[!UICONTROL 「報表來源」]、[!UICONTROL 「體驗撰寫器」]、[!UICONTROL 「量度類型」]和[!UICONTROL 「活動來源」]下拉式清單選取選項來篩選清單。

1. 按一下&#x200B;**[!UICONTROL 「報表」]**。

   此 [Automated Personalization摘要](/help/main/c-reports/personalization-reports/reports-ap.md) 或 [自動鎖定目標摘要](/help/main/c-reports/personalization-reports/auto-target-summary-report.md) 報表隨即顯示，其中提供活動效能的相關資訊，由第一個螢幕圖示表示。 另外兩個圖示代表這兩個 [!UICONTROL 個人化前瞻分析] 報表： [!UICONTROL 自動化區段] 和 [!UICONTROL 重要屬性].

   ![Automated Personalization活動的摘要報表](/help/main/c-reports/assets/summary-report-ap.png)

   請注意 [!UICONTROL 自動鎖定目標] 有另一個圖表圖示，用於 [!UICONTROL 摘要] 報表。

   ![自動鎖定目標活動的摘要報表](/help/main/c-reports/assets/personalization_insights.png)

   >[!IMPORTANT]
   >
   >[!UICONTROL 您啟動活動後的至少 15 天內，將無法使用「重要屬性」]報表。在初始期間，您將無法存取此報表，或點擊[!UICONTROL 「重要屬性」]圖示。15天過後，假設您的活動中有足夠的個人化流量，則 [!UICONTROL 重要屬性] 報表可供使用。

1. 啟動活動15天後，按一下 **[!UICONTROL 重要屬性]** 表徵圖。

   ![Adobe Target報表中的「重要屬性」圖示](/help/main/c-reports/assets/model_attribute_ranking.png)

1. 選取所需的日期範圍。

   不同於 [!UICONTROL 摘要] 報告（績效報告）, [!UICONTROL 個人化前瞻分析]，包括 [!UICONTROL 重要屬性]，僅適用於固定日期範圍：15天，30天，60天。

   這些固定日期範圍允許[!UICONTROL 「個人化前瞻分析」]使用足夠大的資料範圍來降低您從短期模式的活動中掌握情況的可能性。您可以為日期範圍做出兩個決定，「結束日期」和「持續時間」。你會注意到「開始」呈現灰色。開始日期會根據您對結束日期和持續時間的選擇自動變更。

   ![Adobe Target報表中的日曆](/help/main/c-reports/assets/personalization_insights_calendar_1.png)

   您可以從[!UICONTROL 「選擇持續時間」]下拉式清單中存取可用的固定日期範圍。

   ![在報表中選擇「持續時間」下拉式清單](/help/main/c-reports/assets/personalization_insights_calendar_2.png)

1. 檢閱[!UICONTROL 「重要屬性」]報表資料。

   ![Adobe Target中的「重要屬性」報表](/help/main/c-reports/assets/model_attribute_ranking_report.png)

1. (選用) [下載 CSV 格式的報表](/help/main/c-reports/c-report-settings/report-settings.md#section_77E65C50BAAF4AB79242DB3A8778ADEF)，以便在 Excel 和其他工具中進行分析。

   >[!NOTE]
   >
   >「個人化前瞻分析 UI」報表包含指定資訊。「重要屬性」報表的 CSV 下載包含其他詳細資訊。「重要屬性」報表下載包括 100 個常見屬性的完整清單，而 UI 報表僅包括 10 個常見屬性。如果您在報表中尋找特定屬性，但該屬性不存在，那不代表該屬性不會影響活動，它只是沒有列在 100 個常見屬性的清單中。

## 解譯「重要屬性」報表

下表說明如何解譯報表並描述其元素:

| 元素 | 詳細資料 |
|--- |--- |
| 橫條圖 | 畫面頂端的多色彩橫條圖允許您視覺化這些相對重要性分數，並對應到表格中各個屬性旁邊的點的顏色。您也可以將游標移至橫條圖中的特定顏色上，以查看其代表的屬性。100 個常見屬性的重要性分數增加到 100%。如需如何新增更多 Target 個人化模型可使用之屬性的詳細資訊，請參閱[上傳用於 Target 個人化演算法的資料](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md)。 |
| 模型屬性排名圖表 | 「模型屬性排名」包括 10 個常見的屬性，這些對於 Target 的個人化模型如何決定向每個訪客顯示內容而言是最重要的屬性。重要性分數顯示關於這 100 個常見屬性中，特定屬性對此活動中 Target 個人化模型的重要程度。 |

## 「重要屬性」常見問題集 {#section_740910A52FA646B4AC9452F98C2F5719}

**「個人化前瞻分析」報表尚不適用於我的活動。是什麼原因?**

尚未針對您的活動提供[!UICONTROL 個人化前瞻分析]報表的數個可能原因如下:

* 自您啟動活動以來，還不到 15 天。「自動化區段」和「重要屬性」報表在開始活動後至少 15 天內無法使用。在初始期間，您將無法存取這些報表，或點擊「自動化區段」和「重要屬性」圖示。
* 您的活動在指定的時間範圍內沒有足夠的流量。15 天過後，假設您的活動中有[足夠的個人化流量](/help/main/c-activities/auto-target/auto-target-to-optimize.md#section_BA4D83BE40F14A96BE7CBC7C7CF2A8FB)以建立個人化模型，即可使用自動化區段和重要屬性報表。
* 您的活動有收入最佳化目標。目前，[!UICONTROL 「個人化前瞻分析」]僅適用於轉換最佳化目標活動。我們將在未來的版本中新增對收入最佳化目標活動的支援。

**屬性是什麼?**

屬性是關於訪客或他/她的個人化演算法所使用的特定造訪資訊，以學習如何個人化流量。例如，屬性可能是瀏覽器類型、位置、造訪時間等。

如需 [!DNL Target] 在其個人化模型中使用之屬性的詳細資訊，請參閱 [Target 個人化演算法的資料收集](/help/main/c-activities/t-automated-personalization/ap-data.md)。如需如何將新屬性上傳至Target以用於Target個人化模型的詳細資訊，請參閱 [將資料傳入Target的方法](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/methods-to-get-data-into-target/){target=_blank}.

**[!UICONTROL 「自動化區段」]和[!UICONTROL 「重要屬性」]報表中的資訊，是否與 CSV 下載中的資訊相同?**

否，UI 報表包含選取資訊。CSV 下載包含其他詳細資料。「自動化區段前瞻分析報表」下載包括 UI 中包含之常用區段以外的其他「自動化區段」，以及這些區段對選件或體驗的執行方式。「重要屬性」報表包括 100 個常見的訪客屬性及其相對重要性，而 UI 僅包括 10 個常見的訪客屬性。

**我可以看到自訂日期範圍的「個人化前瞻分析」嗎?**

「個人化前瞻分析」報表 ([!UICONTROL 「自動化區段」]和[!UICONTROL 「重要屬性」]) 僅適用於固定日期範圍: 15 天、30 天、45 天、60 天和 90 天。這些固定日期範圍允許[!UICONTROL 「個人化前瞻分析」]使用足夠大的資料範圍來降低您從短期模式的活動中掌握情況的可能性。您可以為任何結束日期選取這些持續時間 (其中這些活動中的資料足以滿足持續時間)。

**「個人化前瞻分析」是如何建立的?**

[!UICONTROL 「個人化前瞻分析」是使用 Adobe 正在申請專利的技術建立而成，該技術稱為 MAGIX (Model Agnostic Globally Interpretable Explanations) 。]您可以在Adobe研究團隊於 [arXiv.org網站](https://arxiv.org/abs/1706.07160).

**「個人化前瞻分析」是否可用於收入型模組化目標/主要目標?**

目前，[!UICONTROL 「個人化前瞻分析」]僅適用於轉換最佳化目標活動。我們將在未來的版本中新增對收入最佳化目標活動的支援。

**「重要屬性」報表中的屬性重要性分數是多少?**

當演算法判斷如何將所有訪客分成它識別的區段時，報表的「屬性重要性排名」部分中的重要性分數可提供演算法用於學習之最重要的變數輸入。它為模型使用的 100 個屬性指派百分比分數。

**與某些自動化區段的其他選件/體驗相比，為什麼某些具有較低轉換率的選件/體驗接收到較大量的流量?**

有多種可能原因會讓您在自動化區段中看到更多造訪較低轉換選件/體驗，包括：

* 針對某些自動化區段之部分或全部選件/體驗的少量檢視。
* 某些選件或體驗尚未建立模型的較少量活動。
* 某些選件/體驗比其他選件/體驗更早建立模型的較少量活動。例如，假設已在第 22 天建立額外的模型，而且您要查看從第 10 至 24 天的資料。
* 鎖定特定選件的規則目標，限制哪些訪客可以查看哪些選件/體驗。
* 前瞻分析報表中沒有任何信賴區間。不過，如果轉換率足夠接近，模型可能會提供流量，以便點數量較高，但不會有「統計上不同的」數字。

瞭解提供流量的模型運作方式會有所助益。每個個人都是根據其總計設定檔提供。不過，前瞻分析報表會歸納此行為，讓人類更容易解讀。因此，區段並非互斥。這可能會導致個別區段顯示這種行為，因為同一個人可以出現在多個區段中。

**有哪些不同的方法可以利用「個人化前瞻分析」中的資訊?**

* 發現要鎖定目標的新對象: 如果您發現某個特定自動化區段執行效能特別好，則可以考慮建立對象，以便您可以在其他報表中重複使用該區段。
* 測試您的假設，瞭解哪種類型的訪客會對您的哪些體驗做出回應。
* 深入瞭解哪些內容適用於何種類型的訪客: 哪些選件負責提升訪客造訪次數。
* 識別表現不佳的內容。
* 瞭解哪些屬性對模型的學習方式最重要。
* 看看個人化模型中使用的屬性及其重要性。
* 找出您可以傳遞給 Target 之其他資料點的商機，以進一步告知您的個人化。

## 已知問題

下列問題目前正由 [!DNL Target] 工程團隊。

* [!DNL Adobe Experience Platform] 區段名稱不會顯示在 [!UICONTROL Automated Personalization] (AP) 和[!UICONTROL 自動鎖定目標] (AT) 活動的[!UICONTROL 重要屬性]報告中。(TOP-3813)
