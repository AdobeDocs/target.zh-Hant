---
keywords: 自動鎖定目標;鎖定目標;流量分配;常見問答;faq;疑難排解;疑難排解;流量
description: 探索有關[!UICONTROL Auto-Target]活動的疑難排解主題和常見問題。
title: 如何疑難排解[!UICONTROL Auto-Target]活動？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=zh-Hant#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Auto-Target
exl-id: 934f738e-560a-4847-9608-432ecfa2afe7
source-git-commit: 3e8c2d77f300bf0e2ca83a53d30e7b9eee48894e
workflow-type: tm+mt
source-wordcount: '1850'
ht-degree: 29%

---

# [!UICONTROL Auto-Target]常見問題集和疑難排解

有關[!DNL Adobe Target]中[!UICONTROL Auto-Target]個活動的疑難排解和常見問答(FAQ)。

## [!UICONTROL Auto-Target]常見問題 {#section_5C120A2B11D14D9BAF767BBAB50FED23}

在使用[!UICONTROL Auto-Target]活動時查詢下列的常見問答集：

### 設定[!UICONTROL Auto-Target]活動的最佳實務是什麼？

+++回答
* 決定[!UICONTROL Revenue per Visit] (RPV)成功量度的商業值是否值得額外的流量需求。 與轉換相比，RPV 通常需要每個體驗至少有 1,000 次轉換，如此活動才會運作。
* 開始展開活動之前，請根據目標決定控制與個人化體驗之間的分配。
* 判斷執行[!UICONTROL Auto-Target]活動之頁面的流量是否足夠，而能夠在合理的時間內建立個人化模型。
* 如果您在測試個人化演演算法，請勿在活動上線期間變更體驗，或新增或移除設定檔屬性。
* 請考慮針對您打算在[!UICONTROL Auto-Target]活動中使用的不同選件和位置進行A/B活動，以確定位置和選項件對最佳化目標具影響力。 如果A/B活動未展現明顯的差異，[!UICONTROL Auto-Target]很可能也無法產生提升度。

  如果 A/B 測試顯示體驗之間沒有統計顯著差異，可能是您考慮的選件彼此的差異不夠、您選取的位置不會影響成功量度，或最佳化目標在轉換漏斗中太遠，以致於不受您選擇的選件所影響。

* 在活動期間儘量不要對體驗進行重大變更。

+++

### 是否建議[!UICONTROL Adobe]以90 （控制項）/10 （目標鎖定）的分割使用[!UICONTROL Auto Target]直到建立模型為止？

+++回答
您的最佳流量分配分割取決於您想要達成的目的。

如果您的目標是儘可能使最多的流量個人化，在活動期限內，您可以維持90%目標配置和10%控制。 如果您的目標是執行比較個人化演演算法與控制項的實驗，則50/50的分割比例最適合活動期限。

最佳實務是維持活動期限的流量配置分割，讓訪客不必在目標鎖定和控制項體驗之間切換。

<!-- 
### Do the check marks indicating a model is built for that experience update if the report date range changes?

No, check marks for model generation show only the models built to date. There's no way to go back and see when a model was completed.
-->

+++

### 如果訪客&#x200B;**沒有**&#x200B;看到[!UICONTROL Auto-Target]活動並轉換，該轉換會計入我的活動中嗎？

+++回答
不會，只有合格並檢視[!UICONTROL Auto-Target]活動的訪客才會計入報告中。

+++

### 為什麼我的[!UICONTROL Auto-Target]活動似乎沒有帶來任何提升度。

+++回答
[!UICONTROL Auto-Target]活動需要四個因素才能產生提升度：

* 選件差異必須足以影響訪客。
* 選件必須位於對最佳化目標有所影響的位置。
* 測試中必須有足夠的流量和統計「能力」，才能偵測提升度。
* 個人化演算法必須正常運作。

動作的最佳措施是先使用簡易、非個人化的 A/B 測試來確定組成活動體驗的內容和位置對整體回應率確實產生影響。務必提早計算樣本大小，以確保有足夠檢定力可看見合理的提升度，並在固定期間執行 A/B 測試而不停止它或進行任何變更。

如果 A/B 測試的結果指出一或多個體驗有統計顯著的提升度，即表示個人化活動可能會運作。當然，即便在體驗的整體回應率沒有產生影響時，個人化也能運作。通常，問題源自選件和位置對最佳化目標的影響不足以用統計顯著性偵測到。

+++

### 何時應該停止[!UICONTROL Auto-Target]活動？

+++回答
[!UICONTROL Auto-Target]可用作「隨時待命」且持續最佳化的個人化。 尤其對於歷久不衰的內容，不需要停止[!UICONTROL Auto-Target]活動。

如果您想要對[!UICONTROL Auto-Target]活動中的內容進行重大改變，最佳實務是啟動新的活動，使其他檢閱報告的使用者不會將過去的結果與不同內容混淆或聯絡起來。

+++

### 模型建置需要等候多久？ {#how-long}

+++回答
在[!UICONTROL Auto-Target]活動中建立模型所需的時間，通常取決於流向您所選活動位置的流量，以及與您的活動成功量度關聯的轉換率。

[!UICONTROL Auto-Target]不會嘗試為指定的體驗建立個人化模型，直到該體驗至少有50個轉換為止。 此外，如果建立的模型品質不佳（使用稱為AUC[&#128279;](https://en.wikipedia.org/wiki/Receiver_operating_characteristic#Area_under_the_curve)的量度對保留「測試」資料進行離線評估所決定），則模型不會用於個人化的流量。

關於[!UICONTROL Auto-Target]的模型建立要記住的其他要點：

* 活動上線後，[!UICONTROL Auto-Target]在嘗試建立模型時會考慮過去至多45天隨機提供的資料。 例如，控制流量，加上一些由演演算法截留的額外隨機提供資料。
* 當[!UICONTROL Revenue per Visit]是成功量度時，由於通常存在於造訪 — 收入中的資料差異程度比存在於轉換率中更高，這些活動通常需要更多資料才能建立模型。
* 由於模型是以每次體驗為基礎而建立，用一次體驗來取代另一次體驗意味著在重建個人化模型之前，必須為新體驗收集足夠的流量（至少50次轉換）。

+++

### 我的活動中已建立一個模型。對該體驗的的造訪是否經過個人化？ 

+++回答
否，您的活動內必須建立至少兩個模型，個人化才能開始。

+++

### 何時可以開始檢視[!UICONTROL Auto-Target]活動的結果？

+++回答
當您至少有兩個體驗已建立模型（綠色勾號），針對已建立模型的體驗，您可以開始檢視[!UICONTROL Auto-Target]測試的結果。

+++

### 是否可以指定要用來作為控制的特定體驗？

+++回答
建立[Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP)或[自動鎖定目標](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (AT)活動時，您可以選取要用來作為控制的體驗。

此功能可讓您根據活動中設定的流量分配百分比，將整個控制流量傳送至特定體驗。 接著，您可以根據該體驗之控制流量，評估個人化流量的效能報表。

如需詳細資訊，請參閱[使用特定體驗作為控制](/help/main/c-activities/t-automated-personalization/experience-as-control.md)。

+++

### 我可以透過[!UICONTROL Auto-Target]活動半途變更目標量度嗎？ {#change-metric}

+++回答
Adobe不建議您在活動中途變更目標量度。 雖然在活動期間有可能使用 [!DNL Target] UI 變更目標量度，您應該總是開始一個新的活動。如果您在活動執行後變更目標量度，Adobe無法保證會發生什麼事。

此建議適用於使用[!DNL Target]或[!DNL Analytics] (A4T)作為報告來源的[!UICONTROL Auto-Allocate]、[!UICONTROL Auto-Target]和[!UICONTROL Automated Personalization]活動。

+++

### 我在執行[!UICONTROL Auto-Target]活動時可以使用[!UICONTROL Reset Report Data]選項嗎？

+++回答
不建議對[!UICONTROL Auto-Target]活動使用[!UICONTROL Reset Report Data]選項。 雖然此選項會移除可見的報告資料，但不會移除[!UICONTROL Auto-Target]模型中的所有訓練記錄。 不要對[!UICONTROL Auto-Target]個活動使用[!UICONTROL Reset Report Data]選項，請建立新活動並停用原始活動。

此指引也適用於[!UICONTROL Auto-Allocate]和[!UICONTROL Automated Personalization]活動。

+++

### 如果我從[!UICONTROL Auto-Target]活動中移除單一體驗，會發生什麼情況？

+++回答
[!DNL Target]會為每個體驗建立一個模型，因此移除一個體驗意味著[!DNL Target]會少建立一個模型，不會影響其他體驗的模型。

例如，假設您有一個包含八個體驗的[!UICONTROL Auto-Target]活動，而您不喜歡其中一個體驗的效能。 您可以移除該體驗，這不會影響其餘七個體驗的模型。

+++

## 疑難排解 [!UICONTROL Auto-Target] {#section_23995AB813F24525AF294D20A20875C8}

有時活動不會如預期般進行。以下是您在使用[!UICONTROL Auto-Target]時可能會遇到的一些潛在挑戰，以及一些建議的解決方案。

### 我的[!UICONTROL Auto-Target]活動花費太多時間來建置模型。

+++疑難排解建議
有幾項活動設定變更可以縮短建立模型的預期時間，包括[!UICONTROL Auto-Target]活動中的體驗數量、流向網站的流量，以及您選取的成功量度。

**解決方案：**&#x200B;檢閱您的活動設定，看看是否有任何您願意進行的變更，以提高建立模型的速度。

* 如果您的成功量度設為[!UICONTROL RPV]，可以變更為轉換嗎？ 轉換活動傾向需要較少流量來建置模型。如果將成功量度從 RPV 變更為轉換，您不會失去活動資料。
* 您的成功量度是否遠低於您的活動體驗的銷售漏斗？ 較低的活動轉換率會增加建立模型所需的流量需求，因為需要的最低轉換次數。
* 是否有您可以從活動中捨棄的一些體驗？ 減少活動中的體驗數量會減少建立模型的時間。
* 是否有更高流量的頁面可讓此活動更成功？ 活動位置的流量和轉換次數越多，建立的模型就越快。

+++

### 我的[!UICONTROL Auto-Target]活動未帶來任何提升度。

+++疑難排解建議
[!UICONTROL Auto-Target]活動需要四個因素才能產生提升度：

* 選件差異必須足以影響訪客。
* 選件必須位於對最佳化目標有所影響的位置。
* 測試中必須有足夠的流量和統計「能力」，才能偵測提升度。
* 個人化演算法必須正常運作。

**解決方案:**&#x200B;首先，請確定活動已將流量個人化。如果沒有為所有體驗建立模型，您的[!UICONTROL Auto-Target]活動仍會隨機處理很大一部分的造訪，以儘快建立所有模型。 如果未建立模型，[!UICONTROL Auto-Target]就不會將流量個人化。

接下來，使用簡易、非個人化的A/B測試，確定優惠方案和活動位置對整體回應率真的有產生影響。 務必提早計算樣本大小，以確保有足夠檢定力可看見合理的提升度，並在固定期間執行 A/B 測試而不停止它或進行任何變更。如果A/B測試結果顯示一或多個體驗在統計上顯著提升，則個人化活動可能會正常運作。 即使體驗的整體回應率沒有差異，Personalization仍可運作。 通常，問題源自選件和位置對最佳化目標的影響不足以用統計顯著性偵測到。

+++

### 相依於轉換量度的任何量度永遠不會轉換。

+++疑難排解建議
這是預期中的情形。

在[!UICONTROL Auto-Target]活動中，轉換量度（無論是最佳化目標或事後目標）一旦轉換，即會從體驗中釋放使用者，而活動也會重新開始。

例如，有一個活動具有轉換量度 (C1) 和另一個量度 (A1)。A1相依於C1。 當訪客第一次進入活動，而轉換 A1 和 C1 的條件未轉換，由於成功量度相依性，此時不會轉換量度 A1。如果訪客轉換C1然後轉換A1，A1仍不會轉換，因為轉換C1時，訪客會釋放。

+++
