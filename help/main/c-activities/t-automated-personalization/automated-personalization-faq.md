---
keywords: 疑難排解；常見問題集；FAQ；FAQs；自動個人化；控制；預設體驗；最佳實務
description: 在[!UICONTROL Adobe Target]中探索關於[!UICONTROL Automated Personalization] (AP)活動的常見問題集(FAQ)和回答清單。
title: 如何尋找有關[!UICONTROL Automated Personalization]活動的常見問題集？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Automated Personalization
exl-id: 2bf62cc1-1781-4021-a400-2884e0bae893
TQID: 'https://experienceleague.adobe.com/cYdFwvkJDlfGYdcxql9iWGwNiTed4Lb2kC7JdN7xgdo'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: f0055dd2-93f3-4ac8-9abc-d69d4ed2d977
    internal-label: Automated personalization
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
    internal-label: Machine learning
source-git-commit: 44c6bdd4ab818226e76477782d7e4238b49d5cdc
workflow-type: tm+mt
source-wordcount: '2088'
ht-degree: 6%
---
# Automated Personalization常見問題集 {#ap-faq}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;尋找有關&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活動的常見問題解答。

>[!ENDSHADEBOX]

下列問題和答案包含如何在[!DNL Adobe Target]中設定&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活動、如何建立個人化模型、如何配置流量以及如何讀取結果。

## 設定活動 {#set-up-an-activity}

+++ 設定[!UICONTROL Automated Personalization]活動的最佳實務是什麼？

* 請密切注意&#x200B;*活動圖形* （位置數量×選件數量），不僅注意體驗總數。 位置和選件的卡式組合對製作時間效能的影響，會比原始體驗數量大。 如以下問題所述，為獲得最佳效能和管理性，請將&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;和&#x200B;**[!UICONTROL 自動鎖定目標]**&#x200B;活動限製為4-6個位置，每個位置提供4-6個選件：「Automated Personalization有哪些限制？」 在本節中。 不建議使用較大的設定，這可能會導致&#x200B;**[!UICONTROL 視覺化體驗撰寫器]**&#x200B;中的載入或編輯速度緩慢。
* 若要個人化低流量頁面，或對您個人化的體驗進行結構性變更，請考慮使用[**[!UICONTROL 自動鎖定目標&#x200B;]**&#x200B;活動](/help/main/c-activities/auto-target/auto-target-to-optimize.md)，而非&#x200B;**[!UICONTROL &#x200B; Automated Personalization &#x200B;]**。
* 請考慮在您計畫於&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活動中使用的選件和位置之間執行&#x200B;**[!UICONTROL A/B測試]**&#x200B;活動，以確認位置和選項對最佳化目標有影響。 如果&#x200B;**[!UICONTROL A/B測試]**&#x200B;活動未展現明顯的差異，**[!UICONTROL Automated Personalization]**&#x200B;很可能也無法產生提升度。

  如果A/B...N測試顯示體驗之間沒有統計上的顯著差異，可能是因為下列一或多個情況所造成：

  * 選件間的差異可能不足。
  * 您選取的位置不會影響成功量度。
  * 最佳化目標在轉換funnel中太遠，無法受您選擇的選件影響。

* 使用[流量估算程式](/help/main/c-activities/t-automated-personalization/ap-traffic-estimator.md#use-traffic-estimator)瞭解在&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活動中建立個人化模型所需的時間。
* 在開始活動之前，根據您的目標，決定控制與目標流量之間的分配。 下表根據您的活動目標和您選取的控制型別，列出要考慮的三種案例。

  | 控制與活動目標 | 建議的控制項配置 | 詳細資料 |
  | --- | --- | --- |
  | **[!UICONTROL 隨機體驗]**&#x200B;作為控制，目標是測試個人化演演算法的有效性 | 50% | 此目標需要更精確的提升圖。 您也最可能想要比較體驗或選件的轉換率，與簡單&#x200B;**[!UICONTROL A/B測試]** （隨機提供的控制）提供的轉換率。 |
  | **[!UICONTROL 隨機體驗]**&#x200B;作為控制，目標是最大化個人化流量 | 10%至30% | 如果您很熟悉演演算法，而且想要個人化最大流量，請使用此選項。 取捨在於提升度資訊的準確性：控制流量的信賴區間較大，因為流向這些區段的流量較少。 |
  | **[!UICONTROL 特定體驗]**&#x200B;作為控制，具有任一目標 | 10%至30% | 使用此選項來比較特定行銷人員導向的體驗與個人化模型。 當您只選取一個體驗作為控制時，該流量不會散佈在活動中的每個選件或體驗之間。 |

* 儘可能謹慎使用定位規則，因為它們可能會干擾模型最佳化的能力。 如需詳細資訊，請參閱[Target Automated Personalization 產品建議](/help/main/c-activities/t-automated-personalization/ap-target-offers.md)。
* 報表群組可以限制您的&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活動成功與否，因此請僅在特定條件下使用它們。 如需詳細資訊，請參閱[Automated Personalization中的選件報表群組](/help/main/c-activities/t-automated-personalization/offer-reporting-groups-in-automated-personalization.md)。

  * 只有在符合下列所有條件時，才使用報表群組：

    * 您打算在活動執行時取代或新增優惠方案。
    * 報表群組中的選件會吸引相同的訪客。
    * 報表群組中的選件具有大約相同的整體回應率。

  * 報表群組中的選件之間沒有個人化專案。 個人化模型會將所有選件視為相同。
  * 絕不將活動中的所有產品建議全部放入單一報表群組中。 這麼做會讓所有選件都隨機提供給活動中的所有訪客。

+++

+++ [!UICONTROL Automated Personalization]中有哪些限制？

[!DNL Target]嚴格限製為30,000個體驗，但在建立少於10,000個體驗時運作情況最好。 當活動啟用&#x200B;**[!UICONTROL 不允許重複專案]**&#x200B;選項時，也會套用相同的限制。

雖然&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;和&#x200B;**[!UICONTROL 自動鎖定目標]**&#x200B;活動可以支援大量體驗，但編寫效能在很大程度上取決於&#x200B;*活動圖形* （位置數量×選件數量）。 某些組態會建立大型笛卡爾組合，即使低於記錄的體驗限制，這些組合仍可大幅影響載入和編輯效能。

為獲得最佳效能和管理性，請將&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;和&#x200B;**[!UICONTROL 自動鎖定目標]**&#x200B;活動限製為4-6個位置，每個位置提供4-6個選件。 不建議使用較大的設定，且可能會在[!DNL Target] UI中加以限制。

在目前的[!DNL Target] UI中，**[!UICONTROL Automated Personalization]**&#x200B;和&#x200B;**[!UICONTROL 自動鎖定目標]**&#x200B;活動是直接在&#x200B;**[!UICONTROL 體驗]**&#x200B;步驟中設定。 當設定超過支援的臨界值時，[!DNL Target]可能會顯示內嵌警告或阻止您儲存活動，而且會在&#x200B;**[!UICONTROL 下一步]**、**[!UICONTROL 儲存]**&#x200B;和&#x200B;**[!UICONTROL 發佈]**&#x200B;上重新驗證活動圖形。

如需會對[!DNL Target]中的活動和其他元素造成影響的字元限制和其他限制（選件大小、對象、設定檔、值、引數等）相關資訊，請參閱[限制](/help/main/r-troubleshooting-target/target-limits.md)。

+++

+++ 我可以指定特定體驗來做為[!UICONTROL Automated Personalization]活動中的控制嗎？

建立[**[!UICONTROL Automated Personalization]**](/help/main/c-activities/t-automated-personalization/automated-personalization.md#automated-personalization-overview) (AP)或[**[!UICONTROL 自動鎖定目標]**](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (AT)活動時，您可以選取要用來作為控制的特定體驗。

此功能可讓您根據活動中設定的流量分配百分比，將整個控制流量傳送至該體驗。 接著，您可以根據該體驗的控制流量，評估個人化流量的效能報表。

如需詳細資訊，請參閱[選取控制體驗](/help/main/c-activities/t-automated-personalization/experience-as-control.md)。

+++

+++ 如何實作產品建議等級目標鎖定?

當每位訪客到達時，選件層級鎖定目標規則會決定訪客看得到的選件集。 演演算法接著會從這些選件中選擇模型預測有最佳預期收入或轉換機會的選件。 選件鎖定目標會影響[!DNL Target]機器學習演演算法的功效，因此請儘量謹慎使用。 如需詳細資訊，請參閱[Target Automated Personalization 產品建議](/help/main/c-activities/t-automated-personalization/ap-target-offers.md)。

+++

## 模型建立和流量分配 {#models-and-traffic}

+++ [!UICONTROL Automated Personalization]如何配置我的活動流量？

**[!UICONTROL Automated Personalization]**&#x200B;會根據最新的[隨機森林](/help/main/c-activities/t-automated-personalization/algo-random-forest.md)模型，將訪客路由到預測成功量度最高的體驗。 此預測是根據特定資訊和訪客的造訪內容而定。

例如，假設&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活動有兩個位置，每個位置有兩個選件。 在第一個位置，產品建議 A 對特定訪客的預測轉換率為 3%，產品建議 B 的預測轉換率為 1%。 在第二個位置，產品建議 C 對相同位訪客的預測轉換率為 2%，產品建議 D 的預測轉換率為 5%。 因此，**[!UICONTROL Automated Personalization]**&#x200B;會提供選件A和選件D給此訪客體驗。

+++

+++ [!UICONTROL Automated Personalization]如何建立環境相關模型？

我們建立了一個模型，用來識別個人化策略相對於隨機提供流量的效能，以及將所有流量傳送至整體成功體驗的效能。 此模型僅考量預設環境中的點選和轉換。

為每個報表群組(**[!UICONTROL Automated Personalization]**)或體驗（**[!UICONTROL 自動鎖定目標]**）建立第二組模型。 對於這些模型中的每一個，都會考量所有環境的點選和轉換。

因此，無論環境為何，都會以相同的模式提供請求。 不過，多個流量應來自預設環境，以確保識別的整體成功體驗與真實世界行為一致。

+++

+++ 模型建置需要等候多久？

在活動中建立模型所需的時間，通常取決於流向您所選活動位置的流量，以及活動成功量度。 使用[流量估算程式](/help/main/c-activities/t-automated-personalization/ap-traffic-estimator.md#use-traffic-estimator)來判斷在您的活動中建立模型所需的預期時間長度。

+++

+++ 如何縮短在[!UICONTROL Automated Personalization]活動中建立模型所需的時間？

檢閱活動設定，瞭解可改善模型建立速度的變更。 例如，將RPV成功量度變更為轉換、選擇在銷售funnel中更接近活動體驗的成功量度、從活動中捨棄部分體驗，或使用較高流量的頁面。 如需詳細資訊，請參閱[疑難排解Automated Personalization](/help/main/c-activities/t-automated-personalization/ap-trouble.md)。

+++

+++ 已在我的[!UICONTROL Automated Personalization]活動中建置一個模型。 對該體驗的的造訪是否經過個人化？

無. 您的活動內必須建立至少兩個模型，個人化才能開始。

+++

## 結果和提升度 {#results-and-lift}

+++ 何時可以檢視[!UICONTROL Automated Personalization]活動的結果？

至少有兩個體驗已建立模型（以綠色勾號表示），您就可以開始檢視&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活動的結果。

+++

+++ 我的[!UICONTROL Automated Personalization]活動為何沒有顯示提升度？

**[!UICONTROL Automated Personalization]**&#x200B;活動需要四個因子才能產生提升度：

* 每個位置中的選件必須足夠不同，才能影響訪客。
* 位置必須位於對最佳化目標有所影響的位置。
* 活動中必須有足夠的流量和統計檢定力，才會偵測到提升度。
* 個人化演算法必須正常運作。

動作的最佳措施是先使用簡單、非個人化的&#x200B;**[!UICONTROL A/B測試]**&#x200B;活動，確定組成活動體驗的內容和位置對整體回應率真的有產生影響。 如需完整程式，請參閱[疑難排解Automated Personalization](/help/main/c-activities/t-automated-personalization/ap-trouble.md)。

+++

+++ 如何比較[!UICONTROL Automated Personalization]與預設體驗？

沒有可將&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;與預設體驗進行比較的全包選項。 暫行解決方法是如果活動中有預設選件或體驗存在，請按一下報表中的&#x200B;**[!UICONTROL 控制項]**&#x200B;區段，然後在產生的選件層級報表中找出該選件。 此選件記錄的轉換率，可與整個「隨機森林」區段的轉換率比較。 此比較顯示模型相對於預設選件的執行方式。

+++

## 管理已上線的活動 {#manage-live-activity}

+++ 何時應該停止[!UICONTROL Automated Personalization]活動？

**[!UICONTROL Automated Personalization]**&#x200B;可用作「隨時待命」且持續最佳化的個人化。 尤其對於歷久不衰的內容，不需要停止您的&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活動。 如果您想要對內容進行重大變更，而這些變更與目前活動中的優惠方案不類似，最佳實務是啟動新活動。 開始新活動可協助其他檢閱報表的使用者避免將過去的結果與不同內容混淆或聯絡起來。

+++

+++ 我可以在[!UICONTROL Automated Personalization]活動中途變更目標量度嗎？

[!DNL Adobe]不建議您在活動中途變更目標量度。 雖然在活動期間有可能使用[!DNL Target] UI變更目標量度，請一律開始新的活動。 [!DNL Adobe]無法保證您在活動執行後變更目標量度會發生什麼情況。

此建議適用於使用[!DNL Target]或[!DNL Analytics] (A4T)作為報告來源的&#x200B;**[!UICONTROL 自動分配]**、**[!UICONTROL 自動鎖定目標]**&#x200B;和&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活動。

+++

+++ 我在執行[!UICONTROL Automated Personalization]活動時可以使用[!UICONTROL 重設報告資料]選項嗎？

[!DNL Adobe]不建議對&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活動使用&#x200B;**[!UICONTROL 重設報表資料]**&#x200B;選項。 雖然此選項會移除可見的報告資料，但不會移除&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;模型中的所有訓練記錄。 不要使用&#x200B;**[!UICONTROL 重設報告資料]**&#x200B;選項，請建立新活動並停用原始活動。 此指引也適用於&#x200B;**[!UICONTROL 自動分配]**&#x200B;和&#x200B;**[!UICONTROL 自動鎖定目標]**&#x200B;活動。

+++

+++ 訪客在[!UICONTROL Automated Personalization]活動中為何看到不應該看到的體驗？

每個工作階段會評估一次&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活動。 如果活動工作階段符合特定體驗的資格，且之後已新增選件，則訪客會看見新內容以及先前顯示的優惠。 這些訪客先前符合這些體驗的資格，因此他們仍可在工作階段期間看見這些體驗。 若要在每次頁面造訪時評估活動，請變更為&#x200B;**[!UICONTROL 體驗鎖定目標]** (XT)活動型別。

+++
