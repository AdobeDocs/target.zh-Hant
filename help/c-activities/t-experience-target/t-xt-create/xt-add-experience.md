---
keywords: create experience;experience create;priority;audience;experience;visual experience composer
description: Adobe Target 可視化體驗撰寫器 (VEC) 提供視覺介面，可用於編輯體驗鎖定目標 (XT) 活動之頁面上的體驗。
title: 建立體驗
feature: xt
topic: Advanced,Standard,Classic
uuid: ce559c3c-5a16-46b8-b2a7-df696626c7c0
translation-type: tm+mt
source-git-commit: 95450abc32be19d04b791af3c62673e9411ab53c
workflow-type: tm+mt
source-wordcount: '962'
ht-degree: 93%

---


# 建立體驗{#create-experience}

[!UICONTROL 可視化體驗撰寫器] (VEC) 提供視覺化介面，可用於編輯[!UICONTROL 體驗鎖定目標] (XT) 活動之頁面上的體驗。

1. 選取您要變更的元素，並進行需要的變更。

   [建立 XT 活動](/help/c-activities/t-experience-target/t-xt-create/xt-create.md)時，三步驟引導式工作流程的步驟一 ([!UICONTROL 體驗]) 會顯示具有[!UICONTROL 所有訪客]受眾的預設[!UICONTROL 體驗 A]。

   ![所有訪客受眾](/help/c-activities/t-experience-target/t-xt-create/assets/all-visitors.png)

   您所做的任何變更會立即套用至體驗 A。在下列步驟中，您將按一下&#x200B;**[!UICONTROL 新增體驗鎖定目標]**&#x200B;以建立其他體驗。

   將游標移至頁面上的元素時，元素會強調顯示。任何強調顯示的元素可以使用 VEC 加以更改。如需可以在元素上執行以變更體驗的動作清單，請參閱[可視化體驗撰寫器選項](/help/c-experiences/c-visual-experience-composer/viztarget-options.md)。

   If you created a [!DNL Target] request on the page using [!DNL Target Classic], that [!DNL Target] request appears as an element that shows the request name, and can be modified like any other element.

   >[!NOTE]
   >
   >根據預設，VEC 不允許對包含 JavaScript 的元素進行變更，例如旋轉橫幅。您可以選取停用 JavaScript，以使用 VEC 更改這些元素。

1. 若要建立其他體驗，請按一下&#x200B;**[!UICONTROL 新增體驗鎖定目標]**。

   ![新增體驗鎖定目標連結](/help/c-activities/t-experience-target/t-xt-create/assets/add-experience-targeting.png)

   [!UICONTROL 選擇受眾]對話方塊隨即顯示。若要將體驗鎖定至某個受眾，則必須先選取受眾才能新增體驗。

   受眾資料庫包含先前已定義的受眾，包括一些隨著 [!DNL Target] 預先建置的共通受眾。您可以從資料庫中選取受眾或[建立新受眾](/help/c-target/c-audiences/audiences.md#concept_65BE870D290E412D8BBF557EEA67C271)。

   >[!NOTE]
   >
   >除了選取現有對象，您可以結合多個對象來建立隨選結合的對象而非建立新對象。如需詳細資訊，請參閱[合併多個對象](/help/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)。

   建立對象時，您可以選取位置並指定該位置的參數。 Under [!UICONTROL Custom] (Create Audience > Add Rule > Custom), select the location, then specify the desired parameters.

   >[!NOTE]
   >
   >當您開啟對象清單時，系統會自動在背景匯入對象，且匯入的是登入超過 10 分鐘的對象。

1. 選取體驗要鎖定的一或多個受眾，然後按一下&#x200B;**[!UICONTROL 完成]**。

   ![體驗 B](/help/c-activities/t-experience-target/t-xt-create/assets/experience-b.png)

   您會發現體驗 B 現已顯示於上圖中，且此體驗已鎖定至美國訪客受眾。

1. 選取您要針對此體驗變更的元素，並進行所需的變更 (如以上步驟 1 所述)。

1. 視需要重複上述步驟，建立其他鎖定目標的體驗。

1. 當您完成體驗設計時，請按一下&#x200B;**[!UICONTROL 下一步]**。

   活動圖表顯示:

   ![XT 鎖定目標圖表](/help/c-activities/t-experience-target/t-xt-create/assets/xt_diagram-new.png)

   >[!NOTE]
   >
   >如果您從主要頁面以外的來源 (例如在 `akamai.net` 上託管並在 `adobe.com` 上傳送的影像) 傳送影像，該影像不會顯示在流程圖中所顯示頁面的縮圖中。

1. (視條件而定) 在建立或編輯 XT 活動時拖放受眾/體驗配對，以使用所需順序排列配對。

   系統會以由上到下的順序評估訪客的體驗。

   ![移動體驗](/help/c-activities/t-experience-target/t-xt-create/assets/move_experiences-new.png)

   [!UICONTROL 體驗鎖定目標]會假設順序重要。如果訪客落入第一個對象/體驗配對，即會傳送第一個體驗。

   例如，假設您不知道建立 XT 活動時順序很重要。您後續在測試期間發現，您認為應該符合體驗 B 或 C 資格的訪客卻符合體驗 A 的資格。這可能是因為該對象非互斥卻採用不適當的順序 (例如，體驗 A = 美國，體驗 B = 舊金山，而體驗 C = 加州)。在此案例中，來自美國的所有使用者會符合體驗 A 的資格，即便他們位於舊金山或加州的其他地方。您可以從最多限制到最少限制 (舊金山 > 加州 > 美國) 重新排序對象/體驗配對，而不需重新建立整個活動。

   如果您有[!UICONTROL 所有訪客]受眾，請確保這不是圖表中的第一個受眾。鎖定在「所有訪客」的體驗，可用來做為體驗鎖定目標活動中的最後一個體驗，以「捕捉」未落入任何其他體驗的任何訪客。

## 重新命名或編輯體驗

您可以按一下 XT 活動中某個體驗的[!UICONTROL 編輯] (三個垂直的點) 圖示，並視需要選擇下列選項:

* 重新命名
* 編輯  

![重新命名和編輯選項](/help/c-activities/t-experience-target/t-xt-create/assets/experience_edit-new.png)

## 刪除體驗

在&#x200B;**[!UICONTROL 體驗]**&#x200B;頁面 (三步驟引導式工作流程的第一步)，按一下三個垂直的點 > **[!UICONTROL 刪除]**。

![刪除體驗](/help/c-activities/t-experience-target/t-xt-create/assets/delete-experience.png)

## 複製體驗

您可以複製 XT 活動中的體驗，不必從頭再次建立體驗，即可進行微幅變更。

在&#x200B;**[!UICONTROL 「體驗」]**&#x200B;頁面 (三步驟引導式工作流程的第一步)，按一下三個垂直的點 > **[!UICONTROL 「複製」]**。

![複製體驗](/help/c-activities/t-experience-target/t-xt-create/assets/duplicate_experience-new.png)

## 訓練影片:

以下影片含有本文章探討之概念的詳細資訊。

### 從 A/B 測試到體驗鎖定目標

這部影片說明如何運用「體驗鎖定目標」(XT) 進一步進行 A/B 測試。

* 說明設定 XT 活動的三步驟引導式工作流程
* 說明如何提供特定地點內容給位於不同地理區域的對象
* 說明如何重新排序體驗，確保提供合適內容給合適對象

>[!VIDEO](https://video.tv.adobe.com/v/22418/)

### 活動類型 (9:03)

此影片說明 Target Standard/Premium 中的可用活動類型。體驗鎖定目標的討論在 5:15 開始。

* 說明 [!DNL Adobe Target] 中包括的活動類型
* 選取達成目標的適當活動類型
* 說明適用所有活動類型的三個步驟引導工作流程

>[!VIDEO](https://video.tv.adobe.com/v/17386)

### 使用可視化體驗撰寫器

這部影片提供關於使用可視化體驗撰寫器選項的資訊。

* 變更頁面的內容
* 變更頁面的配置

>[!VIDEO](https://video.tv.adobe.com/v/17399)