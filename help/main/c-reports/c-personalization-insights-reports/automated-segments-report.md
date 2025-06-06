---
keywords: 鎖定目標;AP 報表;自動個人化報表;自動鎖定目標;自動鎖定目標報表;個人化;前瞻分析;自動化區段;faq;常見問題集
description: 瞭解Adobe [!DNL Target] 個人化模型所定義的不同區段，如何檢視「自動化區段」報表，以回應活動中的選件/體驗。
title: 什麼是自動化區段報表？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=zh-Hant#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Reports
exl-id: d21517b7-770b-4618-9899-7ac4948c2a8b
source-git-commit: c1a71d1fb6fa9b5c14e22fa3199358a4594bb4a1
workflow-type: tm+mt
source-wordcount: '2066'
ht-degree: 59%

---

# [!UICONTROL Automated Segments]報告

有關[!UICONTROL Automated Segments]報告的資訊，這是[!UICONTROL Automated Personalization] (AP)和[!UICONTROL Auto-Target] (AT)活動使用者可用的兩種專用報告之一。

>[!NOTE]
>
>使用[!UICONTROL Personalization Insights]報表時，請考量下列事項：
>
>* AP 和 AT 活動是 [!DNL Target Premium] 解決方案內建的功能。若沒有 [!DNL Target Standard] 授權，[!DNL Target Premium] 便未隨附這些解決方案。
>
>* [!UICONTROL Personalization Insights]報告僅適用於使用轉換最佳化目標的AP和AT活動。 也不支援最佳化目標在活動上線後已從收入變更為轉換的活動。
>
>* 必須從[!UICONTROL Report Metric]下拉式清單中選取[!UICONTROL Primary Goal]，才能使用[!UICONTROL Personalization Insights]報告。
>
>* 僅[預設環境](/help/main/administrating-target/hosts.md)支援[!UICONTROL Personalization Insights]報告。
>
>* [!UICONTROL Personalization Insights]報告只會針對處於[!UICONTROL Live]狀態且已啟用且接收流量至少15天的活動產生。

不同訪客對您的 AP/AT 活動中的產品建議/體驗有不同的反應。此報表顯示 Target 的個人化模型定義之不同自動化區段如何回應活動中的產品建議/體驗。

## 存取「自動化區段」報表 {#section_8E8F997AAAF44A1B9EE06EB6FB652801}

1. 按一下&#x200B;**[!UICONTROL Activities]**，然後從清單中按一下所需的[Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9)或[自動鎖定目標](/help/main/c-activities/auto-target/auto-target-to-optimize.md)活動。

   如果您有許多活動，請按一下篩選器（ ![篩選器圖示](/help/main/assets/icons/Filter.svg) ）圖示，以從[!UICONTROL Type]、[!UICONTROL Status]、[!UICONTROL Reporting Source]、[!UICONTROL Experience Composer]、[!UICONTROL Metrics Type]和[!UICONTROL Activity Source]下拉式清單中選取選項來篩選清單。

1. 按一下 **[!UICONTROL Reports]**。

   顯示[Automated Personalization摘要](/help/main/c-reports/personalization-reports/reports-ap.md)或[自動鎖定目標摘要](/help/main/c-reports/personalization-reports/auto-target-summary-report.md)報告，其中會提供關於活動效能的資訊，並以第一個畫面圖示表示。 兩個額外的圖示代表兩個[!UICONTROL Personalization Insights]報告： **[!UICONTROL Automated Segments]** （ ![自動化區段報告](/help/main/assets/icons/AutomatedSegment.svg) ）和&#x200B;**[!UICONTROL Important Attributes]** （ ![重要屬性圖示](/help/main/assets/icons/ViewList.svg) ）。 自動鎖定目標有一個額外的圖表圖示，用於[!UICONTROL Summary]報表的圖形檢視。

   >[!IMPORTANT]
   >
   >您啟動活動後的至少15天內，將無法使用[!UICONTROL Automated Segments]報表。 在此初始期間，您將無法存取此報表或按一下[!UICONTROL Automated Segments]圖示。 15天過後，假設您的活動中有足夠的個人化流量，即可使用[!UICONTROL Automated Segments]報表。

1. 啟動活動15天後，即可按一下「**[!UICONTROL Automated Segments]**」圖示。

1. 選取所需的日期範圍。

   不同於[!UICONTROL Summary]報表（績效報表），[!UICONTROL Personalization Insights] （包括[!UICONTROL Automated Segments]）僅適用於固定日期範圍： 15天、30天和60天。 這些固定日期範圍允許[!UICONTROL Personalization Insights]使用足夠大的資料範圍，以降低您從活動中的短期模式衍生深入分析的可能性。 您可以為日期範圍做出兩個決定，「結束日期」和「持續時間」。您會注意到「開始」顯示為灰色。 開始日期會根據您對結束日期和持續時間的選擇自動變更。

   您可以從[!UICONTROL Preset Date Range]下拉式清單中存取可用的固定日期範圍。

1. 檢閱[!UICONTROL Automated Segments]報表資料。

1. （選擇性）按一下&#x200B;**[!UICONTROL Download]** （![下載圖示](/help/main/assets/icons/Download.svg) ）圖示以[下載CSV格式的報告](/help/main/c-reports/c-report-settings/report-settings.md#section_77E65C50BAAF4AB79242DB3A8778ADEF)，以便在Excel和其他工具中進行分析。

   >[!NOTE]
   >
   >「個人化前瞻分析 UI」報表包含指定資訊。「自動化區段」報表的 CSV 下載包含其他詳細資訊。「自動化區段」報表會下載包括 UI 中包含之常用區段以外的其他「自動化區段」，以及這些區段對產品建議或體驗的執行方式。

## 解譯「自動化區段」報表

下表說明如何解譯報表並描述其元素:

| 元素 | 詳細資料 |
|--- |--- |
| 左側面板 | 左側面板列出根據此活動之 Target 個人化模型找出的 20 個最大的「自動化區段」。「自動化區段」就像對象，但它是由 Target 的個人化模型 (而非行銷人員) 定義。每個自動化區段是由特定屬性的特定值 (或值範圍) 所組成。<br>自動化區段可以重疊。 自動化區段可以由一、二、三或四個屬性定義。如需詳細資訊，請參閱下列範例。<br>若要深入瞭解 Target 的個人化模型，請參閱[隨機森林演算法](/help/main/c-activities/t-automated-personalization/algo-random-forest.md)。若要深入瞭解用於建立自動化區段之屬性 Target 的個人化模型，請參閱 [Target 個人化演算法的資料收集](/help/main/c-activities/t-automated-personalization/ap-data.md)。 |
| 中心圖 | 中心圖表顯示活動內容在反白顯示自動化區段中的執行方式。 當您按一下左側面板上的不同區段時，中心圖將隨之更新。 |
| 圓形圖 | 中心面板頂端的圓餅圖顯示自動化區段的大小，以及活動中的個人化造訪總數 (例如，個人化模型提供的活動流量。其不包括整體成功案例模型所提供的控制流量或流量)。區段的大小僅根據個人化造訪而定。<br>![圓形圖](/help/main/c-reports/assets/pie.png) |
| 雙軸長條圖 | 雙軸長條圖包括根據該特定自動化區段之產品建議或體驗的造訪和轉換資訊。 |
| 粉紅色長條 | 粉紅色長條代表轉換率，並使用圖表的底部軸。您可以將游標移至長條上以獲取更多資訊 |
| 藍色長條 | 藍色長條代表造訪次數，並使用圖表的頂部軸。您可以將游標移至長條上以獲取更多資訊。 |
| 灰色虛線 | 灰色虛線代表活動中所有個人化造訪的轉換率，涵蓋所有產品建議/體驗和自動化區段。 |

**自動化區段範例 1**

此自動化區段僅根據一個屬性定義。此自動化區段中包含的訪客看到此 AP 活動在正常工作時間或週末以外的平日。

![自動化區段報告範例1](/help/main/c-reports/assets/automated_segment_example_1.png)

**自動化區段範例 2**

此自動化區段僅根據兩個屬性定義。此自動化區段中包括的訪客看到此 AP 活動在目前造訪中的頁面瀏覽次數少於三次，而且地理位置位於緯度 42.57 和 47.29 之間 (大約在新罕布夏州/奧勒崗州和華盛頓州/緬因州之間，是一家美國公司)。

![自動化區段報告範例2](/help/main/c-reports/assets/automated_segment_example_2.png)

## 「自動化區段」常見問答集 {#section_740910A52FA646B4AC9452F98C2F5719}

**「個人化前瞻分析」報表尚不適用於我的活動。是什麼原因?**

[!UICONTROL Personalization Insights]報表尚未提供給您的活動使用有幾個原因：

* 自您啟動活動以來，15天未曾過去。 「自動化區段」和「重要屬性」報表在開始活動後至少 15 天內無法使用。在初始期間，您將無法存取這些報表，或點擊「自動化區段」和「重要屬性」圖示。
* 您的活動在指定的時間範圍內沒有足夠的流量。15 天過後，假設您的活動中有足夠的個人化流量以建立個人化模型，即可使用自動化區段和重要屬性報表。
* 您的活動有收入最佳化目標。目前，[!UICONTROL Personalization Insights]僅適用於轉換最佳化目標活動。 Adobe將在未來版本中新增對收入最佳化目標活動的支援。

**屬性是什麼?**

屬性是關於訪客或他/她的個人化演算法所使用的特定造訪資訊，以學習如何個人化流量。例如，屬性可能是瀏覽器類型、位置、造訪時間等。

如需 [!DNL Target] 在其個人化模型中使用之屬性的詳細資訊，請參閱 [Target 個人化演算法的資料收集](/help/main/c-activities/t-automated-personalization/ap-data.md)。如需如何將新屬性上傳到Target，以在Target的個人化模型中使用的詳細資訊，請參閱[將資料傳入Target的方法](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=zh-Hant){target=_blank}。

**何謂自動化區段?**

「自動化區段」就像對象，但它是由 Target 的個人化模型 (而非行銷人員) 定義。

自動化區段是由特定屬性的特定值 (或值範圍) 所組成。如需自動化區段的範例，請參閱上面的步驟 5。區段可以重疊。

若要深入瞭解隨機森林個人化演演算法（Target個人化模型的基礎），請參閱[隨機森林演演算法](/help/main/c-activities/t-automated-personalization/algo-random-forest.md)。

**決定自動化區段順序的因素為何？**

根據每個區段的大小，及其對您活動內容執行方法的差異，計算每個區段的分數。這些輸入的組合決定自動化區段的順序，針對不同內容的回應方式，具有較大差異的大型區段會顯示在更接近區段清單的頂端。

**為什麼我的「自動化區段」報表中只顯示部分產品建議/體驗?**

AP 和 AT 活動為每個產品建議建置一個模型 (在 AP 的情況下)，並且為每個體驗建置一個模型 (在 AT 的情況下)。這些活動會開始提供個人化流量，並建立您的[!UICONTROL Personalization Insights]，只需建立兩個模型。 如果您在[!UICONTROL Personalization Insights]中未看到您的所有選件/體驗，表示您可能尚未針對這些特定選件/體驗建立模型。 您可以檢查活動的[!UICONTROL Summary]報告，並檢視該選件/體驗旁邊是否有時鐘圖示。 此圖示表示尚未針對該選件/體驗建立模型。

**與某些自動化區段的其他產品建議/體驗相比，為什麼某些具有較低轉換率的產品建議/體驗接收到較大量的流量?**

有多種可能原因會讓您在自動化區段中看到更多造訪較低轉換產品建議或體驗，包括：

* 針對某些自動化區段之部分或全部產品建議/體驗的少量檢視。
* 較少量的活動，其中某些產品建議/體驗未建置模型，或者某些產品建議/體驗比其他產品建議/體驗更快建立。
* 鎖定特定產品建議的規則目標，限制哪些訪客可以查看哪些產品建議/體驗。

**[!UICONTROL Automated Segments]和[!UICONTROL Important Attributes]報表中的資訊是否與CSV下載中的資訊相同？**

否，UI 報表包含選取資訊。CSV 下載包含其他詳細資料。「自動化區段前瞻分析報表」下載包括 UI 中包含之常用區段以外的其他「自動化區段」，以及這些區段對產品建議或體驗的執行方式。「重要屬性」報表包括 100 個常見的訪客屬性及其相對重要性，而 UI 僅包括 10 個常見的訪客屬性。

**我可以看到自訂日期範圍的[!UICONTROL Personalization Insights]嗎？**

Personalization前瞻分析報告（[!UICONTROL Automated Segments]和[!UICONTROL Important Attributes]）僅適用於固定日期範圍： 15天、30天和60天。 這些固定日期範圍允許[!UICONTROL Personalization Insights]使用足夠大的資料範圍，以降低您從活動中的短期模式衍生深入分析的可能性。 您可以為任何結束日期選取這些持續時間 (其中這些活動中的資料足以滿足持續時間)。

**如何建立[!UICONTROL Personalization Insights]？**

[!UICONTROL Personalization Insights]是使用名為MAGIX (Model Agnostic Globally Interpretable Explanations)的Adobe專利擱置技術所建立。 您可以在Adobe研究團隊於[arXiv.org網站](https://arxiv.org/abs/1706.07160)上發表的檔案中，瞭解有關MAGIX的更多資訊。

**為什麼[!UICONTROL Automated Segments]報表中的訪客流量資料總計與我的AP或AT摘要/效能報表不符？**

[!UICONTROL Personalization Insights]報表僅包含看見Target個人化模型所選取內容片段的訪客（亦即不會將整體成功者模型提供的控制流量或流量納入考量）。 此流量型別稱為「個人化」流量。 AP/AT中的摘要效能報表包含控制與「目標」流量。 鎖定目標流量包括個人化流量、使用整體成功案例模型提供的流量，以及用於持續學習的一些隨機提供流量。

**自動化區段是否互相排斥?**

否，自動化區段之間存在重疊。

**是否有[!UICONTROL Personalization Insights]可用於收入型模組化目標/主要目標？**

目前，[!UICONTROL Personalization Insights]僅適用於轉換最佳化目標活動。 Adobe將在未來版本中新增對收入最佳化目標活動的支援。

**有哪些不同的方法可以利用「個人化前瞻分析」中的資訊?**

* 探索要鎖定的新受眾：如果看到特定自動化區段成效良好，您可考慮建立受眾，以便在其他報表中重複使用該區段。
* 測試您對於哪類訪客會回應哪類體驗的假設。
* 深入瞭解哪些內容適用於何種類型的訪客: 哪些產品建議負責提升訪客造訪次數。
* 識別表現不佳的內容。
* 瞭解哪些屬性對模型的學習方式最重要。
* 看看個人化模型中使用的屬性及其重要性。
* 找出您可以傳遞給 Target 之其他資料點的商機，以進一步告知您的個人化。

**屬性在區段卡片中的顯示順序是否有任何邏輯?**

否，卡片的順序僅根據上述排名。卡片內的屬性順序並未根據任何邏輯。
