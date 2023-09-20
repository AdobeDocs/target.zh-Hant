---
keywords: 建立體驗; 體驗建立; 優先順序; 對象; 體驗; 可視化體驗撰寫器
description: 瞭解如何使用 [!DNL Adobe Target] [!UICONTROL 視覺化體驗撰寫器] (VEC)來建立和編輯您頁面上的體驗，於 [!UICONTROL 體驗鎖定] (XT)活動。
title: 如何在中建立體驗 [!UICONTROL 體驗鎖定] 活動？
feature: Experience Targeting
exl-id: ec3fcd93-5557-4f69-8f9c-4d00569188ad
source-git-commit: 0dfdd995c00961ed2aed91ec03406e8493292af7
workflow-type: tm+mt
source-wordcount: '953'
ht-degree: 39%

---

# 在中建立體驗 [!UICONTROL 體驗鎖定] (XT)活動

此 [!UICONTROL 視覺化體驗撰寫器] (VEC)輸入 [!DNL Adobe Target] 提供視覺化介面，用於編輯中頁面上的體驗 [!UICONTROL 體驗鎖定] (XT)活動。

1. 選取您要變更的元素，並進行所需的變更。

   當 [建立 [!UICONTROL 體驗鎖定] 活動](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md)，三步驟引導式工作流程的步驟一([!UICONTROL 體驗])顯示預設值 [!UICONTROL 體驗A] 具有 [!UICONTROL 所有訪客] 對象。

   ![所有訪客受眾](/help/main/c-activities/t-experience-target/t-xt-create/assets/all-visitors.png)

   您所做的任何變更現在都會套用至 [!UICONTROL 體驗A]. 在下列步驟中，您按一下 **[!UICONTROL 新增體驗鎖定目標]** 以建立其他體驗。

   當您將滑鼠停留在頁面上的元素上時，這些元素會反白顯示。 任何強調顯示的元素可以使用 VEC 加以更改。如需可以在元素上執行以變更體驗的動作清單，請參閱[可視化體驗撰寫器選項](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)。

   >[!NOTE]
   >
   >根據預設，VEC 不允許對包含 JavaScript 的元素進行變更，例如旋轉橫幅。您可以使用VEC停用JavaScript來更改這些元素。

1. 若要建立其他體驗，請按一下&#x200B;**[!UICONTROL 新增體驗鎖定目標]**。

   ![新增體驗鎖定目標連結](/help/main/c-activities/t-experience-target/t-xt-create/assets/add-experience-targeting.png)

   此 [!UICONTROL 新增對象] 對話方塊隨即顯示。 若要將體驗鎖定至某個受眾，請在新增體驗之前選取受眾。

   受眾資料庫包含先前已定義的受眾，包括一些隨著 [!DNL Target] 預先建置的共通受眾。您可以從資料庫中選取受眾或[建立新受眾](/help/main/c-target/c-audiences/audiences.md#concept_65BE870D290E412D8BBF557EEA67C271)。

   除了選取現有對象，您可以結合多個對象來建立隨選結合的對象而非建立新對象。如需詳細資訊，請參閱[合併多個對象](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)。

   建立對象時，您可以選取位置並指定該位置的引數。 在 [!UICONTROL 自訂] ([!UICONTROL 建立對象] > [!UICONTROL 自訂])，選取位置，然後指定所需的引數。

   >[!NOTE]
   >
   >當您開啟對象清單時，系統會自動在背景匯入對象，且匯入的對象已超過十分鐘。

1. 選取體驗要鎖定的一或多個受眾，然後按一下&#x200B;**[!UICONTROL 完成]**。

   ![體驗 B](/help/main/c-activities/t-experience-target/t-xt-create/assets/experience-b.png)

   體驗B現在顯示於上圖中，且此體驗已鎖定美國訪客受眾。

1. 選取您要針對此體驗變更的元素，並進行所需的變更，如上述步驟1所述。

1. 視需要重複上述步驟，建立其他鎖定目標的體驗。

1. 當您完成體驗設計時，請按一下&#x200B;**[!UICONTROL 下一步]**。

   活動圖表顯示:

   ![XT 鎖定目標圖表](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_diagram-new.png)

   >[!NOTE]
   >
   >您可以從主要頁面以外的來源（例如在上託管的影像）傳送影像 `akamai.net` 並傳遞於 `adobe.com`)。 在其他位置託管的影像不會顯示在流程圖中所顯示頁面的縮圖中。

1. （視條件而定）在建立或編輯對象和體驗配對時拖放對象 [!UICONTROL 體驗鎖定] 活動，以使用所需順序排列配對。

   系統會以由上到下的順序評估訪客的體驗。

   ![移動體驗](/help/main/c-activities/t-experience-target/t-xt-create/assets/move_experiences-new.png)

   [!UICONTROL 體驗鎖定目標]會假設順序重要。如果訪客屬於第一個受眾和體驗組，則會傳送第一個體驗。

   例如，假設您在建立 [!UICONTROL 體驗鎖定] 活動。 您後續在測試期間發現，您認為應該符合體驗 B 或 C 資格的訪客卻符合體驗 A 的資格。這可能是因為該對象非互斥卻採用不適當的順序 (例如，體驗 A = 美國，體驗 B = 舊金山，而體驗 C = 加州)。在此案例中，所有來自美國的使用者都有資格使用體驗A，即使他們位於舊金山或加州的其他地方亦然。 您可以重新排序對象和體驗配對，從限制最高到限制最低（舊金山>加州>美國），而不需要重新建立整個活動。

   如果您有[!UICONTROL 所有訪客]受眾，請確保這不是圖表中的第一個受眾。鎖定目標的體驗&quot;[!UICONTROL 所有訪客]「 」可作為中的最後一個體驗 [!UICONTROL 體驗鎖定] 活動，可「捕捉」未落入任何其他體驗的任何訪客。

## 重新命名或編輯體驗

您可以按一下 [!UICONTROL 編輯] 圖示（垂直省略符號）在中的體驗 [!UICONTROL 體驗鎖定] 活動，並視需要選擇下列選項：

* [!UICONTROL 重新命名]
* [!UICONTROL 編輯]

![重新命名和編輯選項](/help/main/c-activities/t-experience-target/t-xt-create/assets/experience_edit-new.png)

## 刪除體驗

在 **[!UICONTROL 體驗]** 頁面（三步驟引導式工作流程的第一步），按一下垂直的省略符號> **[!UICONTROL 刪除]**.

![刪除體驗](/help/main/c-activities/t-experience-target/t-xt-create/assets/delete-experience.png)

## 複製體驗

您可以複製中的體驗 [!UICONTROL 體驗鎖定] 活動，因此您可以進行微幅變更，而無須重新建立整個體驗。

在 **[!UICONTROL 體驗]** 頁面（三步驟引導式工作流程的第一步），按一下垂直的省略符號> **[!UICONTROL 複製]**.

![複製體驗](/help/main/c-activities/t-experience-target/t-xt-create/assets/duplicate_experience-new.png)

## 訓練影片:

以下影片含有本文章探討之概念的詳細資訊。

### 從A/B測試到 [!UICONTROL 體驗鎖定]

本影片說明如何使用將A/B測試提升到新的境界 [!UICONTROL 體驗鎖定] (XT)。

* 說明設定「 」的三步驟引導式工作流程 [!UICONTROL 體驗鎖定] 活動
* 說明如何將特定位置的內容提供給不同地理區域的受眾
* 說明如何重新排序體驗，確保提供合適內容給合適對象

>[!VIDEO](https://video.tv.adobe.com/v/22418/)

### 活動類型 (9:03)

此影片說明 [!DNL Target] 中的可用活動類型。[!UICONTROL 體驗鎖定目標的討論在 5:15 開始。]

* 說明 [!DNL Adobe Target] 中包括的活動類型
* 選取達成目標的適當活動類型
* 說明適用所有活動類型的三個步驟引導工作流程

>[!VIDEO](https://video.tv.adobe.com/v/17386)

### 使用 [!UICONTROL 視覺化體驗撰寫器]

本影片提供有關使用 [!UICONTROL 體驗鎖定] (VEC)選項。

* 變更頁面的內容
* 變更頁面的配置

>[!VIDEO](https://video.tv.adobe.com/v/17399)
