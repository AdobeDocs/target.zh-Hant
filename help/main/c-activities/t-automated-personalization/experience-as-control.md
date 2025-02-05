---
keywords: 體驗;控制;automated personalization;自動鎖定目標
description: 瞭解如何在 [!DNL Adobe Target]中建立[!UICONTROL Automated Personalization] (AP)或[!UICONTROL Auto-Target]活動時，選取要用來作為控制的體驗。
title: 如何在[!UICONTROL Automated Personalization]活動中使用特定體驗作為控制？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Automated Personalization, Auto-Target
solution: Target,Analytics
exl-id: a0a36ace-3cba-4d8d-9bbd-e35204ff6453
source-git-commit: 3a44c05bea24c622292dd0b774f88f0c93be1d88
workflow-type: tm+mt
source-wordcount: '768'
ht-degree: 39%

---

# 選取您[!UICONTROL Automated Personalization]或[!UICONTROL Auto-Target]活動的控制項

建立[[!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP)或[[!UICONTROL Auto-Target]](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (AT)活動時，您可以選取要用來作為控制的隨機提供的體驗或特定體驗。

此功能可讓您根據活動中設定的流量配置百分比，將控制流量傳送至相關體驗。接著，您可以根據該控制之控制流量，評估個人化流量的效能報表。

在[!UICONTROL Automated Personalization]和[!UICONTROL Auto-Target]活動中設定控制項的選項與其他活動型別稍有不同。 在手動[!UICONTROL A/B Test]中，您可以變更顯示為控制體驗的報表，而提升度會根據該控制體驗的轉換率計算。 您可以輕鬆進行此變更，因為無論控制一開始是設定至哪個體驗，流量都會隨機提供給包含在活動中的各個體驗。換言之，選取控制不會影響流量的提供方式。 在[!UICONTROL Automated Personalization]和[!UICONTROL Auto-Target]活動中，您選擇用來作為控制的決定確實會影響訪客流量的提供方式。 因此，您必須更謹慎思考您的決定。

在[!UICONTROL Automated Personalization]和[!UICONTROL Auto-Target]活動中，有兩個選項可供您的控制項使用：

* **隨機提供**：針對隨機控制，流量的控制百分比會隨機提供給活動中的所有體驗，而不考慮該訪客的設定檔。 控制有助於回答此問題：「如果我只隨機將體驗（或選件）提供給訪客，且不考慮其設定檔，該體驗（或選件）的轉換率為何？」 控制項就像AI活動中的[!UICONTROL A/B Test]。 擁有這項各個體驗或產品建議的非個人化轉換率的資訊，就能在分析活動結果時協助您輕鬆瞭解。

* **特定體驗**：特定體驗控制可讓您比較[!DNL Target]個人化模型與特定行銷人員定義體驗（例如您的預設首頁）所提供的流量。 透過此選項，流量的控制百分比會隨機將流量提供給該體驗。

## 指定特定體驗作為控制

1. 在建立或編輯[[!UICONTROL Automated Personalization]活動](/help/main/c-activities/t-automated-personalization/create-ap-activity.md)或[[!UICONTROL Auto-Target]活動](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md)時，視需要設定體驗。
1. 在[!UICONTROL Targeting]頁面（三步驟引導式工作流程的步驟2）上，按一下控制體驗，以在右窗格中顯示[!UICONTROL Control]選項。

   ![控制窗格](/help/main/c-activities/t-automated-personalization/assets/control.png)

1. 從[!UICONTROL Control]下拉式清單中，選取[!UICONTROL Random Experience]或選取您要用於控制項的體驗。

1. 按一下[!UICONTROL Traffic Allocation]控制項，然後指定控制項體驗和其他體驗所需的流量分配。

   ![流量分配邊欄](/help/main/c-activities/t-automated-personalization/assets/traffic-allocation.png)

   針對特定體驗控制，建議指定 10% 至 30%。

1. 繼續使用[!UICONTROL Goals & Settings]頁面。

## 已知限制和考量事項

使用特定體驗作為控制時，請記住下列重點：

* 不建議變更已上線活動中的控制體驗。選取的最新控制體驗會在報表中命名 (即使較舊報表是根據其他體驗也是如此)。
* 不建議刪除控制體驗。
* 不建議透過作為控制的特定體驗將許多新選件或體驗新增至上線活動。
* 在[!UICONTROL Automated Personalization]活動中，不建議在可能會進一步限制誰能看到控制體驗的該體驗上包含鎖定目標。
* 在[!UICONTROL Automated Personalization]個活動中，如果已選取特定體驗，提升度和信賴資訊在選件層級的報告中&#x200B;*NOT*&#x200B;可用。 在[!UICONTROL Automated Personalization]活動的整體「已鎖定目標」與「控制」流量層級提供提升度和信賴資訊。 如果已選取「隨機」作為控制，則可取得提升度和信賴資訊。此差異是因為比較特定體驗的轉換率與產品建議的轉換率，由於兩者單位不同，這種比較並不符合邏輯。無論選取哪種控制型別，[!UICONTROL Auto-Target]活動中可用的資訊都是相同的。
* 因為在您選取體驗作為控制時，所有控制流量都會進入單一體驗或一組產品建議 (相較之下，在隨機狀況中，控制流量則會分散在活動中的多個體驗或產品建議之中)，您通常不需要像流向控制如此多的流量。建議從 10% 開始。
* 如果您透過作為控制的特定體驗對上線活動執行下列其中一項操作，控制會自動重設為隨機提供體驗 (而不是先前選取的特定體驗):

   * 刪除體驗
   * 移除位置或選件（僅限[!UICONTROL Automated Personalization]）
   * 透過移除重複選件或透過排除群組（僅限[!UICONTROL Automated Personalization]）手動排除體驗
