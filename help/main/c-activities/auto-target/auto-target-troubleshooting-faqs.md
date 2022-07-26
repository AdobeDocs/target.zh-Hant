---
keywords: 自動鎖定目標;鎖定目標;流量分配;常見問答;faq;疑難排解;疑難排解;流量
description: 查看有關 Adobe Target 自動鎖定目標活動的疑難排解主題和常見問答。
title: 如何疑難排解自動鎖定目標活動？
feature: Auto-Target
exl-id: 934f738e-560a-4847-9608-432ecfa2afe7
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: ht
source-wordcount: '1919'
ht-degree: 100%

---

# ![PREMIUM](/help/main/assets/premium.png) 自動鎖定目標疑難排解和常見問答 (FAQ)

查看有關 [!DNL Adobe Target] [!UICONTROL 自動鎖定目標] 的疑難排解和常見問答 (FAQ)。

## 自動鎖定目標常見問答 {#section_5C120A2B11D14D9BAF767BBAB50FED23}

在使用 [!UICONTROL 自動鎖定目標] 活動時查詢下列的常見問答：

### 設定 [!UICONTROL 自動鎖定目標] 活動有何最佳作法？

* 決定「每次造訪帶來的收入 (RPV)」成功量度的商業價值是否有額外流量需求的價值。與轉換相比，RPV 通常需要每個體驗至少有 1,000 次轉換，如此活動才會運作。
* 開始展開活動之前，請根據目標決定控制與個人化體驗之間的分配。
* 判斷將執行[!UICONTROL 自動鎖定目標]活動的頁面是否有足夠流量，而能夠在合理的時間內建立個人化模型。
   * 如果您在測試個人化演算法，請勿於活動上線期間變更體驗，或新增/移除設定檔屬性。

* 請考慮針對您打算於[!UICONTROL 自動鎖定目標]活動中使用的不同選件和位置進行 A/B 活動，以確定位置和選項件對最佳化目標具影響力。如果 A/B 活動未展現明顯的差異，則[!UICONTROL 自動鎖定目標]很可能也無法帶來提升度。

   * 如果 A/B 測試顯示體驗之間沒有統計顯著差異，可能是您考慮的選件彼此的差異不夠、您選取的位置不會影響成功量度，或最佳化目標在轉換漏斗中太遠，以致於不受您選擇的選件所影響。

* 請勿於活動期間對體驗做出重大變更。

### 你建議我們在使用[!UICONTROL 自動鎖定目標]時採取 90 (控制項)/10 (目標鎖定) 的分割比例，直到建立模型為止嗎？

您的最佳流量配置分割取決於您想要達成的目的。

如果您的目標是盡可能使最多的流量個人化，對於期限和活動可以維持 90% (目標鎖定) 和 10% (控制項) 的分割比例。如果您的目標是執行比較個人化演算法與控制項的實驗，則 50/50 的分割比例最適合活動期限。

最佳實務是維持活動期限的流量配置分割，讓訪客不必在目標鎖定和控制項體驗之間切換。

<!-- 
### Do the check marks indicating a model is built for that experience update if the report date range changes?

No, check marks for model generation show only the models built to date. There's no way to go back and see when a model was completed.
-->

### 如果訪客沒有看到 [!UICONTROL 自動鎖定目標] 活動就轉換，該轉換會計入我的活動中嗎？

不會，只有合格並檢視 [!UICONTROL 自動鎖定目標] 活動的訪客才會計入報告中。

### 我的 [!UICONTROL 自動鎖定目標] 活動似乎沒有帶來任何提升度。這是為什麼？ 

[!UICONTROL 自動鎖定目標]活動帶來提升度需要四個要素:

* 選件需要夠不同才能影響訪客。
* 選件需要位於對最佳化目標而言具有差異化的位置。
* 測試中必須具有充分的流量和統計「檢定力」才能偵測提升度。
* 個人化演算法必須正常運作。

動作的最佳措施是先使用簡易、非個人化的 A/B 測試來確定組成活動體驗的內容和位置對整體回應率確實產生影響。務必提早計算樣本大小，以確保有足夠檢定力可看見合理的提升度，並在固定期間執行 A/B 測試而不停止它或進行任何變更。

如果 A/B 測試的結果指出一或多個體驗有統計顯著的提升度，即表示個人化活動可能會運作。當然，即便在體驗的整體回應率沒有產生影響時，個人化也能運作。一般來說，問題源自選件/位置對要使用統計精確度偵測的最佳化目標沒有夠大的影響。

### 我何時應該停止 [!UICONTROL 自動鎖定目標] 活動？

[!UICONTROL 自動鎖定目標] 可用作「隨時待命」且將持續最佳化的個人化。尤其對於歷久不衰的內容，沒有必要停止 [!UICONTROL 自動鎖定目標] 活動。

如果您想對 [!UICONTROL 自動鎖定目標] 活動中的內容進行重大改變，最佳實務是啟動新的活動，使其他檢閱報告的使用者不會將過去的結果與不同內容混淆或聯繫起來。

### 模型建置需要等候多久？ {#how-long}

在 [!UICONTROL 自動鎖定目標] 活動中建立模型所需的時間，通常取決於流向您所選活動位置的流量，以及與您的活動成功量度關聯的轉換率。

[!UICONTROL 自動鎖定目標] 不會嘗試為特定的體驗建立個人化模型，直到該體驗至少有 50 個轉換為止。此外，如果建立的模型品質不佳 (使用[稱為 AUC 的量度](https://en.wikipedia.org/wiki/Receiver_operating_characteristic#Area_under_the_curve)以截留「測試」資料進行離線評估來決定)，則該模型不會用於個人化的流量。

關於 [!UICONTROL 自動鎖定目標] 模型建立的其他應牢記的要點：

* 一旦活動開始，[!UICONTROL 自動鎖定目標] 在嘗試建立模型時會考慮過去至多 45 天隨機提供的資料 (亦即控制流量，再加上一些由我們的演算法截留的額外隨機提供資料)。
* 當[!UICONTROL 每次造訪收入]是成功量度時，由於通常存在於造訪-收入中的資料差異程度比存在於轉換率中更高，這些活動通常需要更多資料才能建立模型。
* 由於模型是以每次體驗為基礎而建立，用一次體驗來取代另一次體驗意味著在重新建立個人化模型之前，必須就新體驗收集足夠的流量 (至少 50 次轉換)。

### 我的活動中已建立一個模型。對該體驗的的造訪是否經過個人化？ 

否，您的活動內必須建立至少兩個模型，個人化才能開始。

### 何時可以開始查看 [!UICONTROL 自動鎖定目標] 活動的結果？

當您至少有兩個體驗已建立模型 (綠色勾號)，針對已建立模型的體驗，您可以開始查看 [!UICONTROL 自動鎖定目標] 測試的結果。

### 是否可以指定要用來作為控制的特定體驗？

建立 [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) 或[自動鎖定目標](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (AT) 活動時，您可以選取要用來作為控制的體驗。

此功能可讓您根據活動中設定的流量配置百分比，將整個控制流量傳送至特定體驗。接著，您可以根據該體驗之控制流量，評估個人化流量的效能報表。

如需詳細資訊，請參閱[使用特定體驗作為控制](/help/main/c-activities/t-automated-personalization/experience-as-control.md)。

### 我可以透過自動鎖定目標活動半途變更目標量度嗎？  {#change-metric}

我們不建議您透在活動中途變更目標量度。雖然在活動期間有可能使用 [!DNL Target] UI 變更目標量度，您應該總是開始一個新的活動。我們不保證您在活動開始執行後變更目標量度會發生什麼事。

此推薦適用於 [!UICONTROL 自動分配]、[!UICONTROL 自動鎖定目標]，以及 [!UICONTROL Automated Personalization] 活動 (使用 [!DNL Target] 或 [!DNL Analytics] (A4T) 成作為報告來源。)

### 我在執行自動鎖定目標活動時可以使用「重設報告資料」選項嗎？

不建議在對 [!UICONTROL 自動鎖定目標] 活動使用 [!UICONTROL 重設報告資料] 選項。雖然此選項會移除可見的報告資料，它不會移除 [!UICONTROL 自動鎖定目標] 模型中所有的訓練記錄。建議不要對 [!UICONTROL 自動鎖定目標] 活動使用 [!UICONTROL 重設報告資料] 選項，您可以建立新的活動和停用原始活動。(附註：此指引也適用於[!UICONTROL 自動分配]和 [!UICONTROL Automated Personalization] 活動。)

### 如果我從自動鎖定目標活動移除單一體驗會發生什麼情況？

[!DNL Target] 會為每一個體驗建立一個模型，因此移除一個體驗意味著 [!DNL Target] 會少建立一個模型，對為其他體驗建立的模型不會造成影響。

例如，假設您有一個具有八個體驗的 [!UICONTROL 自動鎖定目標] 活動，而您不喜歡其中一個體驗的效能。您可以移除該體驗，這並不會對其餘七個體驗的模型造成影響。

## 疑難排解[!UICONTROL 自動鎖定目標] {#section_23995AB813F24525AF294D20A20875C8}

有時活動不會如預期般進行。以下是使用[!UICONTROL 自動鎖定目標]可能面臨的一些挑戰，以及一些建議的解決方案。

### [!UICONTROL 自動鎖定目標] 活動花太久時間來建立模型。

有幾項活動設定變更可以縮短建立模型的預期時間，包括[!UICONTROL 自動鎖定目標]活動中的體驗數量、流向網站的流量，以及您選取的成功量度。

**解決方案:** 請檢閱您的活動設定並查看是否有您想要進行的任何變更，以改善建置模型的速度。

* 如果您的成功量度是設為 RPV，您可以變更為轉換嗎？ 轉換活動傾向需要較少流量來建置模型。如果將成功量度從 RPV 變更為轉換，您不會失去活動資料。
* 您的成功量度是否遠低於您的活動體驗的銷售漏斗？ 較低的活動轉換率將增加建置模型所需的流量，因為需要最低的轉換數量。
* 是否有您可以從活動中捨棄的一些體驗？ 減少活動中的體驗數量可縮短建立模型所需的時間。
* 是否有更高流量的頁面可讓此活動更成功？ 若活動位置中有愈多流量和轉換，則建置模型的速度愈快。

### 我的 [!UICONTROL 自動鎖定目標] 活動未帶來任何提升度。

AP 活動產生提升度需要四個係數:

* 選件需要夠不同才能影響訪客。
* 選件需要位於對最佳化目標而言具有差異化的位置。
* 測試中必須具有充分的流量和統計「檢定力」才能偵測提升度。
* 個人化演算法必須正常運作。

**解決方案:**&#x200B;首先，請確定活動已將流量個人化。如果沒有為所有體驗建立模型，[!UICONTROL 自動鎖定目標]活動仍會隨機處理很大一部分的造訪，以試著盡快建立所有模型。如果沒有建立模型，[!UICONTROL 自動鎖定目標]就不會將流量個人化。

接下來，請使用簡單且非個人化的 A/B 測試，以確保選件和活動位置確實對整體回應率造成改變。務必提早計算樣本大小，以確保有足夠檢定力可看見合理的提升度，並在固定期間執行 A/B 測試而不停止它或進行任何變更。如果 A/B 測試結果對一或多個體驗顯示統計顯著的提升度，則個人化活動可能將正常運作。當然，即便在體驗的整體回應率沒有產生影響時，個人化也能運作。一般來說，問題源自選件/位置對要使用統計精確度偵測的最佳化目標沒有夠大的影響。

### 相依於轉換量度的任何量度永遠不會轉換。

這是預期中的情形。

在[!UICONTROL 自動鎖定目標]活動中，轉換量度 (無論是最佳化目標或事後目標) 一旦轉換，即會從體驗中釋放使用者，而活動也會重新開始。

例如，有一個活動具有轉換量度 (C1) 和另一個量度 (A1)。A1 相依於 C1。當訪客第一次進入活動，而轉換 A1 和 C1 的條件未轉換，由於成功量度相依性，此時不會轉換量度 A1。如果訪客轉換 C1 然後轉換 A1，此時仍不會轉換 A1，因為 C1 一旦進行轉換即會釋出訪客。
