---
keywords: 體驗;控制;automated personalization;自動鎖定目標
description: 瞭解如何在建立時選取要用來作為控制的體驗 [!UICONTROL Automated Personalization] (AP)或 [!UICONTROL 自動鎖定目標] 中的活動 [!DNL Adobe Target].
title: 如何在中使用特定體驗作為控制 [!UICONTROL Automated Personalization] 活動？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Automated Personalization, Auto-Target
solution: Target,Analytics
exl-id: a0a36ace-3cba-4d8d-9bbd-e35204ff6453
source-git-commit: a9508c4bc454faeb8d6763677cce17a264a4a70f
workflow-type: tm+mt
source-wordcount: '783'
ht-degree: 42%

---

# 選擇您的控制項 [!UICONTROL Automated Personalization] 或 [!UICONTROL 自動鎖定目標] 活動

您可以在建立「 」時選取要用來作為控制的隨機提供的體驗或特定體驗 [[!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP)或 [[!UICONTROL 自動鎖定目標]](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (AT)活動。

此功能可讓您根據活動中設定的流量配置百分比，將控制流量傳送至相關體驗。接著，您可以根據該控制之控制流量，評估個人化流量的效能報表。

設定控制項的選項 [!UICONTROL Automated Personalization] 和 [!UICONTROL 自動鎖定目標] 活動與其他活動型別略有不同。 在手冊 [!UICONTROL A/B測試]，您可以變更將哪些報表顯示為控制，而提升度是根據該控制體驗的轉換率計算。 您可以輕鬆進行此變更，因為無論控制一開始是設定至哪個體驗，流量都會隨機提供給包含在活動中的各個體驗。換言之，選取控制不會影響流量的提供方式。 在 [!UICONTROL Automated Personalization] 和 [!UICONTROL 自動鎖定目標] 活動，您選擇用來作為控制的相關決策確實會影響訪客流量的提供方式。 因此，您必須更謹慎思考您的決定。

您的控制有兩個可用選項 [!UICONTROL Automated Personalization] 和 [!UICONTROL 自動鎖定目標] 活動：

* **隨機提供**：針對隨機控制，流量的控制百分比會隨機提供給活動中的所有體驗，而不考慮該訪客的設定檔。 控制有助於回答此問題：「如果我只隨機將體驗（或選件）提供給訪客，且不考慮其設定檔，該體驗（或選件）的轉換率為何？」 控制項類似於 [!UICONTROL A/B測試] 在您的AI活動中。 擁有這項各個體驗或選件的非個人化轉換率的資訊，就能在分析活動結果時協助您輕鬆瞭解。

* **特定體驗**：特定體驗控制可讓您比較以下專案所提供的流量： [!DNL Target] 將個人化模型套用到特定行銷人員定義的體驗（例如您的預設首頁）。 透過此選項，流量的控制百分比會隨機將流量提供給該體驗。

## 指定特定體驗作為控制

1. 建立 [[!UICONTROL Automated Personalization] 活動](/help/main/c-activities/t-automated-personalization/create-ap-activity.md) 或 [[!UICONTROL 自動鎖定目標] 活動](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md)，視需要設定體驗。
1. 在[!UICONTROL 鎖定目標]頁面 (三步驟引導式工作流程的步驟 2) 上，選取要用來作為控制的體驗。
1. 真對控制體驗和其他體驗，指定所需的流量分配。

   針對特定體驗控制，建議指定 10% 至 30%。

1. 繼續前往[!UICONTROL 目標與設定]頁面。

## 已知限制和考量事項

使用特定體驗作為控制時，請記住下列重點：

* 不建議變更已上線活動中的控制體驗。選取的最新控制體驗會在報表中命名 (即使較舊報表是根據其他體驗也是如此)。
* 不建議刪除控制體驗。
* 不建議透過作為控制的特定體驗將許多新選件或體驗新增至上線活動。
* 在 [!UICONTROL Automated Personalization] 不建議使用活動，包括針對可能會進一步限制誰能看到控制體驗的該體驗進行定位。
* 在 [!UICONTROL Automated Personalization] 活動、提升度和可信度資訊為 *NOT* 如果選取特定體驗，可在選件層級報表中使用。 提升度和可信度資訊可在整體「鎖定目標」與「控制」流量層級取得，針對 [!UICONTROL Automated Personalization] 活動。 如果已選取「隨機」作為控制，則可取得提升度和信賴資訊。此差異是因為比較特定體驗的轉換率與選件的轉換率，由於兩者單位不同，這種比較並不符合邏輯。此資訊位於 [!UICONTROL 自動鎖定目標] 無論選取哪種控制型別，活動都是相同的。
* 因為在您選取體驗作為控制時，所有控制流量都會進入單一體驗或一組選件 (相較之下，在隨機狀況中，控制流量則會分散在活動中的多個體驗或選件之中)，您通常不需要像流向控制如此多的流量。建議從 10% 開始。
* 如果您透過作為控制的特定體驗對上線活動執行下列其中一項操作，控制會自動重設為隨機提供體驗 (而不是先前選取的特定體驗):

   * 刪除體驗
   * 移除位置或選件([!UICONTROL Automated Personalization] 僅限)
   * 透過移除重複選件或透過排除群組([!UICONTROL Automated Personalization] 僅限)
