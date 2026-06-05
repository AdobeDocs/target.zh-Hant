---
keywords: 建立體驗; 體驗建立; 優先順序; 客群; 體驗; 可視化體驗撰寫器
description: 瞭解如何使用 [!DNL Adobe Target] [!UICONTROL 視覺化體驗撰寫器] (VEC)來建立和編輯[!UICONTROL 體驗鎖定目標] (XT)活動之頁面上的體驗。
title: 如何在[!UICONTROL 體驗鎖定目標]活動中建立體驗？
feature: Experience Targeting
exl-id: ec3fcd93-5557-4f69-8f9c-4d00569188ad
TQID: https://experienceleague.adobe.com/neRp-1hK4qnksT5dJA-A3HD-ShbbpuL2bjkB4He8qPQ
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 975
ht-degree: 21%

---

# 在[!UICONTROL 體驗鎖定目標] (XT)活動中建立體驗

[!DNL Adobe Target]中的[!UICONTROL 視覺化體驗撰寫器] (VEC)提供視覺化介面，可用於編輯[!UICONTROL 體驗鎖定目標] (XT)活動之頁面上的體驗。

1. 選取您要變更的元素，並進行所需的變更。

   在[建立[!UICONTROL 體驗鎖定目標]活動](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md)時，三步驟引導式工作流程的步驟一（[!UICONTROL 體驗]）會顯示具有[!UICONTROL 所有訪客]受眾的預設[!UICONTROL 體驗A]。

   ![所有訪客客群](/help/main/c-activities/t-experience-target/t-xt-create/assets/all-visitors-new.png)

   您所做的任何變更現在都會套用至[!UICONTROL 體驗A]。在下列步驟中，按一下&#x200B;**[!UICONTROL 新增體驗鎖定目標]**&#x200B;以建立其他體驗。

   當您將滑鼠停留在頁面上的元素上時，這些元素會反白顯示。 任何強調顯示的元素可以使用 VEC 加以更改。 如需可以在元素上執行以變更體驗的動作清單，請參閱[可視化體驗撰寫器選項](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)。

   >[!NOTE]
   >
   >根據預設，VEC 不允許對包含 JavaScript 的元素進行變更，例如旋轉橫幅。 您可以使用VEC停用JavaScript以更改這些元素。

1. 若要建立其他體驗，請按一下&#x200B;**[!UICONTROL 新增]** （![新增按鈕](/help/main/assets/icons/Add.svg) ）。

   [!UICONTROL 新增對象]對話方塊隨即顯示。 若要將體驗鎖定至某個受眾，請在新增體驗之前選取受眾。

   客群資料庫包含先前已定義的客群，包括一些隨著 [!DNL Target] 預先建置的共通客群。 您可以從資料庫中選取客群或[建立新客群](/help/main/c-target/c-audiences/audiences.md#concept_65BE870D290E412D8BBF557EEA67C271)。

   除了選取現有對象，您可以結合多個對象來建立隨選結合的對象而非建立新對象。 如需詳細資訊，請參閱[合併多個客群](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)。

   建立對象時，您可以選取位置並指定該位置的引數。 在[!UICONTROL 自訂] （[!UICONTROL 建立對象] > [!UICONTROL 自訂]）下，選取位置，然後指定所要的引數。

   >[!NOTE]
   >
   >當您開啟對象清單時，系統會自動在背景匯入對象，且匯入的對象已超過十分鐘。

1. 選取體驗要鎖定的一或多個對象，然後按一下&#x200B;**[!UICONTROL 指派對象]**。

   體驗B現在顯示於上圖中，且此體驗已鎖定至適當的對象。

1. 選取您要針對此體驗變更的元素，並進行所需的變更，如上述步驟1所述。

1. 視需要重複上述步驟，建立其他鎖定目標的體驗。

1. 完成體驗設計時，請按一下&#x200B;**[!UICONTROL 下一步]**。

   活動圖表顯示:

   ![XT 鎖定目標圖表](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_diagram-refresh.png)

   >[!NOTE]
   >
   >您可以從主要頁面以外的來源（例如在`akamai.net`上託管並在`adobe.com`上傳送的影像）傳送影像。 在其他位置託管的影像不會顯示在流程圖中所顯示頁面的縮圖中。

1. （視條件而定）在建立或編輯[!UICONTROL 體驗鎖定目標]活動時，拖放對象和體驗配對，以使用所需順序排列配對。

   按一下「重新排序」圖示（![重新排序圖示](/help/main/assets/icons/Reorder.svg)）以在右側顯示[!UICONTROL 體驗]欄，然後視需要重新排列體驗。

   系統會以由上到下的順序評估訪客的體驗。

   [!UICONTROL 體驗鎖定目標]會假設順序重要。 如果訪客屬於第一個受眾和體驗組，則會傳送第一個體驗。

   例如，假設您在建立[!UICONTROL 體驗鎖定目標]活動時不知道順序很重要。 您稍後在測試期間發現，您認為應符合體驗B或C的訪客，反而符合體驗A。此情況可能是因為對象並非互斥，且順序不正確（例如，體驗A =美國、體驗B =舊金山，以及體驗C =加州）。 在此案例中，所有來自美國的使用者都有資格使用體驗A，即使他們位於舊金山或加州的其他地方亦然。 您可以重新排序對象和體驗配對，從限制最高到限制最低（舊金山>加州>美國），而不需要重新建立整個活動。

   如果您有[!UICONTROL 所有訪客]對象，請確定這不是圖表中的第一個對象。 鎖定在「[!UICONTROL 所有訪客]」的體驗，可用作[!UICONTROL 體驗鎖定目標]活動中的最後一個體驗，以「捕捉」未落入任何其他體驗的任何訪客。

## 重新命名、編輯、複製或刪除體驗

按一下[!UICONTROL 體驗鎖定目標]活動之圖表中的體驗，以在右側顯示[!UICONTROL 體驗]欄。

![重新命名和編輯選項](/help/main/c-activities/t-experience-target/t-xt-create/assets/experience_edit-refresh.png)

視需要選擇下列選項：

* **[!UICONTROL 重新命名]**：在[!UICONTROL 名稱]欄位中輸入所要的名稱。
* **[!UICONTROL 編輯]**：按一下「編輯」圖示（ ![編輯圖示](/help/main/assets/icons/Edit.svg)），然後進行您想要的變更。
* **[!UICONTROL 複製]**：複製[!UICONTROL 體驗鎖定目標]活動中的體驗，不必重新建立整個體驗，即可進行微幅變更。 按一下「[!UICONTROL 複製]」圖示（「![複製」圖示](/help/main/assets/icons/Duplicate.svg)），然後視需要編輯體驗。
* **[!UICONTROL 刪除]**：按一下[!UICONTROL 刪除]圖示（![刪除圖示](/help/main/assets/icons/Delete.svg)），然後確認您的刪除。

## 訓練影片:

以下影片含有本文章探討之概念的詳細資訊。

### 從A/B測試到[!UICONTROL 體驗鎖定目標]

此影片說明如何使用[!UICONTROL 體驗鎖定目標] (XT)將A/B測試提升到下一個層級。

* 說明設定[!UICONTROL 體驗鎖定目標]活動的三步驟引導式工作流程
* 說明如何將特定位置的內容提供給不同地理區域的受眾
* 說明如何重新排序體驗，確保提供合適內容給合適對象

>[!VIDEO](https://video.tv.adobe.com/v/22418/)

### 活動型別(9:03)

此影片說明 [!DNL Target] 中的可用活動類型。 從5:15開始討論[!UICONTROL 體驗鎖定目標]。

* 說明 [!DNL Adobe Target] 中包括的活動類型
* 選取達成目標的適當活動類型
* 說明適用所有活動類型的三個步驟引導工作流程

>[!VIDEO](https://video.tv.adobe.com/v/17386)

### 使用[!UICONTROL 視覺化體驗撰寫器]

此影片提供有關使用[!UICONTROL 體驗鎖定目標] (VEC)選項的資訊。

* 變更頁面的內容
* 變更頁面的配置

>[!VIDEO](https://video.tv.adobe.com/v/17399)
