---
keywords: 體驗;控制;automated personalization;自動鎖定目標
description: 瞭解如何在[!DNL Adobe Target]中建立[!UICONTROL Automated Personalization] (AP)或[!UICONTROL 自動鎖定目標]活動時，選取要用來作為控制的體驗。
title: 如何在[!UICONTROL Automated Personalization]活動中使用特定體驗作為控制？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Automated Personalization, Auto-Target
solution: Target,Analytics
exl-id: a0a36ace-3cba-4d8d-9bbd-e35204ff6453
TQID: 'https://experienceleague.adobe.com/a-lIVDWxeAi-VCp7-lLD-zaClCDCKJGfa25XMKF0vZA'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: f0055dd2-93f3-4ac8-9abc-d69d4ed2d977
    internal-label: Automated personalization
  - id: db15a02f-03cd-46fe-a53e-02064cdeadfa
    internal-label: Auto target
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 44c6bdd4ab818226e76477782d7e4238b49d5cdc
workflow-type: tm+mt
source-wordcount: '801'
ht-degree: 3%
---
# 選取控制體驗 {#experience-as-control}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解如何選擇&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;或&#x200B;**[!UICONTROL 自動鎖定目標]**&#x200B;活動的控制權，以及當您使用特定體驗作為控制時要考量的事項。

>[!ENDSHADEBOX]

建立[**[!UICONTROL Automated Personalization]**](/help/main/c-activities/t-automated-personalization/automated-personalization.md#automated-personalization-overview) (AP)或[**[!UICONTROL 自動鎖定目標]**](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (AT)活動時，您可以選取要用來作為控制的隨機提供的體驗或特定體驗。 控制流量會根據活動中設定的流量分配百分比路由到相關體驗，以便您可以對照控制流量評估個人化流量的效能報表。

在手動&#x200B;**[!UICONTROL A/B測試]**&#x200B;中，您可以變更顯示為控制的報表，而提升度會從該體驗中計算，因為流量是隨機提供給所有體驗，無論控制是什麼。 在&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;和&#x200B;**[!UICONTROL 自動鎖定目標]**&#x200B;活動中，控制項會影響訪客流量的提供方式，因此請謹慎選擇。

控制項有兩個可用選項：

* **隨機提供：**&#x200B;流量的控制百分比會隨機提供給活動中的所有體驗，而不考慮訪客的設定檔。 它在您的活動中運作方式類似於&#x200B;**[!UICONTROL A/B測試]**，而且會顯示每個體驗或選件的非個人化轉換率，這有助於您分析結果。

* **特定體驗：**&#x200B;流量的控制百分比只會隨機提供該體驗。 此選項可讓您比較[!DNL Target]個人化模型提供的流量與您定義的特定體驗，例如您的預設首頁。

## 考量事項 {#considerations}

使用特定體驗作為控制時，請記住下列重點：

* 不建議變更已上線活動中的控制體驗。 即使較舊報表是根據其他體驗，所選的最新控制體驗會在報表中命名。

* 不建議刪除控制體驗。

* 不建議透過作為控制的特定體驗將許多新選件或體驗新增至上線活動。

* 在&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活動中，不建議在可能會進一步限制誰能看到控制體驗的該體驗上包含鎖定目標。

* 在&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活動中，如果已選取特定體驗，則提升度和可信度資訊在選件層級的報告中&#x200B;*無法*&#x200B;使用。 這是因為比較特定體驗的轉換率與選件的轉換率，由於兩者單位不同，這種比較並不符合邏輯。 提升度和信賴資訊可在活動的整體「鎖定目標」與「控制」流量層級取得，如果選取「隨機」作為控制，則可在所有層級取得。 無論選取哪種控制型別，**[!UICONTROL 自動鎖定目標]**&#x200B;活動中可用的資訊都是相同的。

* 當您選取特定體驗作為控制時，所有控制流量都會流向單一體驗或一組選件。 若使用隨機控制，控制流量會根據您的活動中的體驗或選件數進行分割。 因此，您通常不需要太多流量就能透過特定體驗流向控制。 建議從 10% 開始。

* 如果您透過作為控制的特定體驗對上線活動執行下列其中一項操作，控制會自動重設為隨機提供體驗（而不是先前選取的特定體驗）：

  * 刪除體驗。
  * 移除位置或選件（僅限&#x200B;**[!UICONTROL Automated Personalization]**）。
  * 透過移除重複選件或透過排除群組（僅限&#x200B;**[!UICONTROL Automated Personalization]**）手動排除體驗。


## 指定特定體驗作為控制 {#specify-control}

將特定體驗指定為控制項，可為個人化流量提供在活動報表中用來比較的已知體驗，例如您目前的預設體驗。

1. 在建立或編輯[**[!UICONTROL Automated Personalization ]**活動](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#create-ap-activity)或[**[!UICONTROL 自動鎖定目標]**&#x200B;活動](/help/main/c-activities/auto-target/create-auto-target.md#create-auto-target-activity)時，視需要設定體驗。

1. 在&#x200B;**[!UICONTROL 鎖定目標]**&#x200B;頁面（三步驟引導式工作流程的步驟2）上，按一下控制體驗，以在右窗格中顯示&#x200B;**[!UICONTROL 控制項]**&#x200B;選項。

   ![控制窗格](/help/main/c-activities/t-automated-personalization/assets/control.png)

1. 從&#x200B;**[!UICONTROL 控制]**&#x200B;下拉式清單中，選取&#x200B;**[!UICONTROL 隨機體驗]**，或選取您要用來作為控制的體驗。

1. 按一下&#x200B;**[!UICONTROL 流量分配]**&#x200B;控制，然後指定控制體驗和其他體驗的流量分配。

   ![流量分配邊欄](/help/main/c-activities/t-automated-personalization/assets/traffic-allocation.png)

   針對特定體驗控制，建議指定 10% 至 30%。

1. 繼續進行&#x200B;**[!UICONTROL 目標與設定]**&#x200B;頁面。

活動上線後，其報表會將個人化流量與您選取的控制體驗進行比較。 在變更已上線的活動之前，請先檢閱[考量事項](#considerations)，因為有些變更會自動將控制項重設為隨機提供的體驗。
