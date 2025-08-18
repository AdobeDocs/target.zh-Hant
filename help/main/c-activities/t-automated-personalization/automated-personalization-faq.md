---
keywords: 疑難排解；常見問題集；FAQ；FAQs；自動個人化；控制；預設體驗；最佳實務
description: 探索[!UICONTROL Automated Personalization]中[!UICONTROL Adobe Target] (AP)活動的常見問題(FAQ)和答案清單。
title: 如何尋找有關[!UICONTROL Automated Personalization]活動的常見問題集？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=zh-Hant#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Automated Personalization
exl-id: 2bf62cc1-1781-4021-a400-2884e0bae893
source-git-commit: 336da9dd876243a0eea662b4604a8fc1e6a69b1a
workflow-type: tm+mt
source-wordcount: '1946'
ht-degree: 20%

---

# Automated Personalization常見問題集

當您在[!UICONTROL Automated Personalization]中處理[!DNL Adobe Target]活動時，請查閱下列常見問答集。

## 我可以指定特定體驗來做為[!UICONTROL Automated Personalization]活動中的控制嗎？

+++檢視詳細資料

建立[Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP)或[自動鎖定目標](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (AT)活動時，您可以選取要用來作為控制的體驗。

此功能可讓您根據活動中設定的流量配置百分比，將整個控制流量傳送至特定體驗。接著，您可以根據該體驗之控制流量，評估個人化流量的效能報表。

如需詳細資訊，請參閱[使用特定體驗作為控制](/help/main/c-activities/t-automated-personalization/experience-as-control.md)。

+++

## 如何比較[!UICONTROL Automated Personalization]與預設體驗？ {#section_46C1A620A2384C2C8392D6716DD18495}

+++檢視詳細資料

沒有將[!UICONTROL Automated Personalization]與預設體驗進行比較的按鍵選項。 不過，暫行解決方法是如果預設選件或體驗存在於整個活動中，若要瞭解其基準效能，請按一下報表中的&quot;[!UICONTROL Control]&quot;區段，然後在產生的選件層級報表中找出該特定選件。 針對此選件記錄的轉換率，可用來與整個「隨機森林」區段的交談率進行比較。 這有助於比較機器的運作與預設產品建議。

+++

## 設定[!UICONTROL Automated Personalization]活動的最佳實務是什麼？ {#section_E155B26282BE49B58EA2683413D11DE6}

+++檢視詳細資料

* 如果您想要個人化低流量頁面，或想對個人化的體驗進行結構性變更，請考慮使用[!UICONTROL Auto-Target]活動來取代[!UICONTROL Automated Personalization]。 請參閱[自動鎖定目標](/help/main/c-activities/auto-target/auto-target-to-optimize.md)。
* 請考慮針對您打算在[!UICONTROL A/B Test]活動中使用的不同選件和位置進行[!UICONTROL Automated Personalization]活動，以確定位置和選項件對最佳化目標具影響力。 如果[!UICONTROL A/B Test]活動未展現明顯的差異，[!UICONTROL Automated Personalization]可能也無法產生提升度。

   * 如果A/B...N測試顯示體驗之間沒有統計上的顯著差異，可能是因為下列一或多個情況所造成：

      * 選件間的差異可能不足。
      * 您選取的位置不會影響成功量度。
      * 最佳化目標在轉換漏斗中太遠，不受您選擇的選件影響。

* 請務必使用[流量估算程式](/help/main/c-activities/t-automated-personalization/ap-traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714)，以瞭解在[!UICONTROL Automated Personalization]活動中建立個人化模型所需的時間。
* 在開始活動之前，根據您的目標，決定控制與目標之間的配置。

  根據活動目標和您已選取的控制型別，請考慮三種情況：

   * **使用隨機體驗作為控制，且活動目標是測試個人化演演算法的有效程度**：如果您的目標是評估個人化演演算法，則您想要更準確地瞭解提升度。 如果您僅執行[!UICONTROL A/B Test] （隨機提供的控制），也很可能想要比較體驗或選件的轉換率。 在此情況下，建議對隨機提供的體驗控制執行 50% 分配。
   * **「隨機體驗」作為控制，且活動目標是最大化個人化流量**：如果您很熟悉演演算法，而且想要有最大量的個人化流量，建議對控制執行10%至30%分配。 這裡的取捨是您在提升度資訊中看到的準確度。 控制流量的信賴區間較大，因為流向它們的流量較少。
   * **使用特定體驗作為控制，具有任一目標類型**: 若要比較個人化模型的特定行銷人員導向體驗，建議對控制執行 10% 至 30% 分配。當您只選取一個體驗作為控制時，該流量不會散佈在活動中的每個選件或體驗之間。

* 鎖定目標規則應儘可能少用，因為會妨礙模型的最佳化能力。
* 報告群組可以限制您的[!UICONTROL Automated Personalization]活動的成功。 僅在特定條件下使用報表群組：

   * 只有在符合下列條件時，才使用報表群組：

      * 您打算在活動執行時取代或新增優惠方案。
      * 報表群組中的選件會吸引相同的訪客。
      * 該報表群組中的選件具有大約相同的整體回應率。

   * 報表群組中的選件之間沒有個人化專案。 個人化模型會將所有選件視為相同專案。
   * 絕不將活動中的所有產品建議全部放入單一報表群組中。這麼做會讓所有選件都隨機提供給活動中的所有訪客。

+++

## [!UICONTROL Automated Personalization]中有哪些限制？ {#section_08BA09ED51B547299963C94FE6417CFA}

+++檢視詳細資料

[!DNL Target]嚴格限製為30,000個體驗，但在建立少於10,000個體驗時運作情況最好。

即使活動已啟用[!UICONTROL Disalow Duplicates]選項，此限制也會套用。

如需會對[!DNL Target]中的活動和其他元素造成影響的字元限制和其他限制（選件大小、對象、設定檔、值、引數等）相關資訊，請參閱[限制](/help/main/r-troubleshooting-target/target-limits.md)。

+++

## 如何實作產品建議等級目標鎖定?    {#section_9D7A86EA93D74E9B8C81072A681263A4}

+++檢視詳細資料

當每個訪客抵達時，訪客可能看見的產品建議集取決於產品建議等級鎖定目標規則。接著，演演算法會從這些優惠方案中選擇模型預測有最佳預期收入或轉換機會的優惠方案。 選件鎖定目標會影響[!DNL Target]機器學習演演算法的效能，因此應儘可能謹慎使用。

+++

## 我的[!UICONTROL Automated Personalization]活動為何沒有顯示提升度？ {#section_BFA07C8C258F45318F73A461B8F32737}

+++檢視詳細資料

[!UICONTROL Automated Personalization]活動需要四個因素才能產生提升度：

* 每個位置中的選件必須足夠不同，才能影響訪客。
* 位置必須位於對最佳化目標有所影響的位置。
* 活動中必須有足夠的流量和統計檢定力，才會偵測到提升度。
* 個人化演算法必須正常運作。

動作的最佳措施是先使用簡易、非個人化的[!UICONTROL A/B Test]活動，確定組成活動體驗的內容和位置對整體回應率真的有產生影響。 務必提早計算樣本大小，以確保有足夠檢定力可看見合理的提升度，並在固定期間執行 A/B 測試而不停止它或進行任何變更。如果A/B測試結果顯示一或多個體驗在統計上顯著提升，則個人化活動可能會成功。 即使體驗的整體回應率沒有差異，Personalization仍可運作。 通常，問題源自選件或位置對最佳化目標的影響不足以偵測到具有統計顯著性的情況。

如需詳細資訊，[疑難排解Automated Personalization](/help/main/c-activities/t-automated-personalization/ap-trouble.md#reference_281954549C3E49E2B5498009BBDC62CA)。

+++

## [!UICONTROL Automated Personalization]如何配置我的活動流量？ {#section_4369364F77804E0D9B78BEE551DA5659}

+++檢視詳細資料

[!UICONTROL Automated Personalization]會根據針對每個模型建立的最新[隨機森林](/help/main/c-activities/t-automated-personalization/algo-random-forest.md)模型，將訪客路由至預測成功量度最高的體驗。 此預測是根據訪客的特定資訊和造訪情境。

例如，假設[!UICONTROL Automated Personalization]活動有兩個位置，每個位置有兩個選件。 在第一個位置，產品建議 A 對特定訪客的預測轉換率為 3%，產品建議 B 的預測轉換率為 1%。在第二個位置，產品建議 C 對相同位訪客的預測轉換率為 2%，產品建議 D 的預測轉換率為 5%。因此，[!UICONTROL Automated Personalization]會提供選件A和選件D給此訪客體驗。

+++

## 何時應該停止[!UICONTROL Automated Personalization]活動？ {#section_C51F3DAB8887463BB147373F6FE06B93}

+++檢視詳細資料

[!UICONTROL Automated Personalization]可用作「隨時待命」且持續最佳化的個人化。 尤其對於歷久不衰的內容，不需要停止[!UICONTROL Automated Personalization]活動。 如果您想要對內容進行重大變更，而這些變更與目前[!UICONTROL Automated Personalization]活動中選件不類似，最佳實務是啟動新活動。 開始新活動可協助其他檢閱報表的使用者避免將過去的結果與不同內容混淆或聯絡起來。

+++

## 模型建置需要等候多久？ {#section_6F6A5A9DB3564BE6B22FFEDFA5B29619}

+++檢視詳細資料

在活動中建立模型所需的時間，通常取決於流向您所選活動位置的流量，以及活動成功量度。 使用[流量估算程式](/help/main/c-activities/t-automated-personalization/ap-traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714)來判斷在您的活動中建立模型所需的預期時間長度。

+++

## 已在我的[!UICONTROL Automated Personalization]活動中建置一個模型。 對該體驗的的造訪是否經過個人化？  {#section_51EA953C6D1D4A3185FC9DD290D66621}

+++檢視詳細資料

否，您的活動內必須建立至少兩個模型，個人化才能開始。

+++

## 何時可以檢視[!UICONTROL Automated Personalization]活動的結果？ {#section_05DB5ACAE6AD429C9510766A7268EE2C}

+++檢視詳細資料

當您至少有兩個體驗已建立模型（綠色勾號），針對已建立模型的體驗，您可以開始檢視[!UICONTROL Automated Personalization]活動的結果。

+++

## 如何縮短在[!UICONTROL Automated Personalization]活動中建立模型所需的時間？ {#section_CCB8CEE98DAA40BA93AADCD596C48D82}

+++檢視詳細資料

檢閱活動設定，並檢視您是否有任何願意進行的變更來改善模型建立的速度。

* 您的成功量度是否遠低於您的活動體驗的銷售漏斗？ 較低的活動轉換率將增加建置模型所需的流量，因為需要最低的轉換數量。
* 如果您的成功量度是設為 RPV，您可以變更為轉換嗎？ 轉換活動傾向需要較少流量來建置模型。
* 是否有您可以從活動中捨棄的一些體驗？ 減少活動中的體驗數量會加快建立模型的時間。
* 是否有更高流量的頁面可讓此活動更成功？ 活動位置的流量和轉換次數越多，建立的模型就越快。

+++

## 訪客在[!UICONTROL Automated Personalization]活動中為何看到不應該看到的體驗？ {#section_41CECEAE0881446A8D9F3B016857914B}

+++檢視詳細資料

每個工作階段評估[!UICONTROL Automated Personalization]個活動。 如果存在符合特定體驗資格的使用中工作階段，且現在已有新選件加入其中，訪客將會看見新內容以及先前顯示的優件。 因為這些訪客先前符合這些體驗的資格，他們仍會在工作階段期間看到這些體驗。 若要在每次頁面瀏覽時評估此專案，您應該變更為[!UICONTROL Experience Targeting] (XT)活動型別。

+++

## 我可以透過[!UICONTROL Automated Personalization]活動半途變更目標量度嗎？ {#change-metric}

+++檢視詳細資料

[!DNL Adobe]不建議您在活動中途變更目標量度。 雖然在活動期間有可能使用 [!DNL Target] UI 變更目標量度，您應該總是開始一個新的活動。[!DNL Adobe]無法保證您在活動執行後變更目標量度會發生什麼事。

此建議適用於使用[!UICONTROL Auto-Allocate]或[!UICONTROL Auto-Target] (A4T)作為報告來源的[!UICONTROL Automated Personalization]、[!DNL Target]和[!DNL Analytics]活動。

+++

## 我在執行[!UICONTROL Reset Report Data]活動時可以使用[!UICONTROL Automated Personalization]選項嗎？

+++檢視詳細資料

[!DNL Adobe]不建議對[!UICONTROL Reset Report Data]活動使用[!UICONTROL Automated Personalization]選項。 雖然此選項會移除可見的報告資料，但不會移除[!UICONTROL Automated Personalization]模型中的所有訓練記錄。 不要對[!UICONTROL Reset Report Data]個活動使用[!UICONTROL Automated Personalization]選項，請建立新活動並停用原始活動。 此指引也適用於[!UICONTROL Auto-Allocate]和[!UICONTROL Auto-Target]活動。

+++

## [!UICONTROL Automated Personalization]如何建立環境相關模型？

+++檢視詳細資料

我們建立了一個模型，用來識別個人化策略相對於隨機提供流量的效能，以及將所有流量傳送至整體成功體驗的效能。 此模型僅考量預設環境中的點選和轉換。

為每個模型群組([!UICONTROL Automated Personalization])或體驗([!UICONTROL Auto-Target])建立第二組模型的流量。 對於這些模型中的每一個，都會考量所有環境的點選和轉換。

因此，無論環境為何，都會以相同的模式提供請求。 不過，多個流量應來自預設環境，以確保識別的整體成功體驗與真實世界行為一致。

+++
