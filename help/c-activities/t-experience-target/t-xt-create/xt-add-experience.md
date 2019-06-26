---
description: Visual Experience Composer(CMS)提供一個視覺化介面，用於編輯您在「體驗鎖定(XT)」活動中頁面上的體驗。
keywords: 建立體驗; 體驗建立; 優先順序; 對象; 體驗; 可視化體驗撰寫器
seo-description: Adobe Target Visual Experience Composer(CMS)提供一個視覺化介面，用於編輯您在「體驗鎖定(XT)」活動中頁面上的體驗。
seo-title: 建立體驗
solution: Target
title: 建立體驗
topic: Advanced,Standard,Classic
uuid: ce559c3c-5a16-46b8-b2a7-df696626c7c0
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Create experience{#create-experience}

Visual Experience Composer(CMS)提供一個視覺化介面，用於編輯您在「體驗鎖定(XT)」活動中頁面上的體驗。

1. 選取您要變更的元素，並進行需要的變更。

   [建立XT活動](/help/c-activities/t-experience-target/t-xt-create/xt-create.md)時，三部分引導式工作流程(體驗)之一會顯示預設 [!UICONTROL A] 與 [!UICONTROL 所有訪客] 對象的預設體驗A。

   ![所有訪客對象](/help/c-activities/t-experience-target/t-xt-create/assets/all-visitors.png)

   Any changes you make now apply to Experience A. In a step below, you&#39;ll click **[!UICONTROL Add Experience Targeting]** to create additional experiences.

   將游標移至頁面上的元素時，元素會強調顯示。任何反白顯示的元素都可以使用CMS進行變更。For a list of actions that can be performed on an element to change the experience, see [Visual Experience Composer Options](/help/c-experiences/c-visual-experience-composer/viztarget-options.md).

   如果您在使用 Target Classic (先前的 Test&amp;Target) 的頁面上建立 mbox，該 mbox 會以元素的形式出現並顯示 mbox 名稱，且可如同任何其他元素般加以修改。

   >[!NOTE]
   >
   >依預設，可視化體驗撰寫器不允許對包含 JavaScript 的元素進行變更，例如旋轉橫幅。如果您想要使用CMS變更這些元素，可以選取停用JavaScript。

1. To create additional experiences, click **[!Add Experience Targeting]**.

   ![新增體驗定位連結](/help/c-activities/t-experience-target/t-xt-create/assets/add-experience-targeting.png)

   The [!UICONTROL Choose Audience] dialog box displays. 若要將體驗定位給對象，您必須先選取對象，才能新增體驗。

   對象資料庫包含先前已定義的對象，包括一些隨著 Target 預先建置的共通對象。您可以從資料庫選取對象，或是[建立新對象](../../../c-target/c-audiences/audiences.md#concept_65BE870D290E412D8BBF557EEA67C271)。

   >[!NOTE]
   >
   >除了選取現有對象，您可以結合多個對象來建立隨選結合的對象而非建立新對象。如需詳細資訊，請參閱[合併多個對象](../../../c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)。

   建立觀眾時，您可以選取位置 (mbox) 並指定該位置的參數。Under [!UICONTROL Custom] (Create Audience &gt; Add Rule &gt; Custom), select the mbox, then specify the desired parameters.

   >[!NOTE]
   >
   >當您開啟對象清單時，系統會自動在背景匯入對象，且匯入的是登入超過 10 分鐘的對象。

1. Select one or more audiences to target with the experience, then click **[!UICONTROL Done]**.

   ![體驗 B](/help/c-activities/t-experience-target/t-xt-create/assets/experience-b.png)

   您會注意到，「體驗B」現在會顯示在上一個插圖中，而這個體驗將會鎖定在「美國訪客」對象中。

1. 選取您要變更此體驗的元素並進行所需變更，請參閱上述步驟1。

1. 視需要重復上述步驟，以建立其他目標體驗。

1. Click **[!UICONTROL Next]** when you are finished designing your experiences.

   活動圖表顯示:

   ![XT定位圖](/help/c-activities/t-experience-target/t-xt-create/assets/xt_diagram-new.png)

   >[!NOTE]
   >
   >如果您從主頁面以外的來源傳送影像(例如Akamai. net上裝載的影像，並以adobe.com傳送)，則該影像不會顯示在流程圖中所顯示頁面的縮圖中。

1. (條件性)在建立或編輯XT活動時拖放對象/體驗配對，以依照所需順序排列配對。

   訪客會依順序、由上到下的體驗進行評估。

   ![移動體驗](/help/c-activities/t-experience-target/t-xt-create/assets/move_experiences-new.png)

   體驗鎖定目標會假設順序重要。如果訪客落入第一個對象/體驗配對，即會傳送第一個體驗。

   例如，假設您不知道建立 XT 活動時順序很重要。您後續在測試期間發現，您認為應該符合體驗 B 或 C 資格的訪客卻符合體驗 A 的資格。這可能是因為該對象非互斥卻採用不適當的順序 (例如，體驗 A = 美國，體驗 B = 舊金山，而體驗 C = 加州)。在此案例中，來自美國的所有使用者會符合體驗 A 的資格，即便他們位於舊金山或加州的其他地方。您可以從最多限制到最少限制 (舊金山 &gt; 加州 &gt; 美國) 重新排序對象/體驗配對，而不需重新建立整個活動。

   If you have an [!UICONTROL All Visitors] audience, ensure that it is not the first audience in the diagram. 鎖定在「所有訪客」的體驗，可用來做為體驗鎖定目標活動中的最後一個體驗，以「捕捉」未落入任何其他體驗的任何訪客。

## 重新命名或編輯體驗

You can click the [!UICONTROL Edit] icon (three vertical ellipses) on an experience in an XT activity and choose from the following options, as necessary:

* 重新命名
* 編輯  

![重新命名和編輯選項](/help/c-activities/t-experience-target/t-xt-create/assets/experience_edit-new.png)

## 刪除體驗

On the **[!UICONTROL Experiences]** page (the first step in the three-step guided workflow), click the three vertical ellipses &gt; **[!UICONTROL Delete]**.

![刪除體驗](/help/c-activities/t-experience-target/t-xt-create/assets/delete-experience.png)

## 複製體驗

您可以複製體驗鎖定目標 (XT) 活動中的體驗，不必從頭再次建立體驗，即可進行微幅變更。

在 **[!UICONTROL 「體驗」]** 頁面 (三步驟引導式工作流程的第一步)，按一下三個垂直的點 &gt; **[!UICONTROL 「複製」]**。

![重復體驗](/help/c-activities/t-experience-target/t-xt-create/assets/duplicate_experience-new.png)

## 訓練影片:

以下影片含有本文章探討之概念的詳細資訊。

### 從 A/B 測試到體驗鎖定目標

這部影片說明如何運用「體驗鎖定目標」(XT) 進一步進行 A/B 測試。

* 說明設定 XT 活動的三步驟引導式工作流程
* 說明如何提供特定地點內容給位於不同地理區域的對象
* 說明如何重新排序體驗，確保提供合適內容給合適對象

>[!VIDEO](https://video.tv.adobe.com/v/22418/?captions=chi_hant)

### 活動類型 (9:03)

此影片說明 Target Standard/Premium 中的可用活動類型。體驗鎖定目標的討論在 5:15 開始。

* 說明 [!DNL Adobe Target] 中包括的活動類型
* 選取達成目標的適當活動類型
* 說明適用所有活動類型的三個步驟引導工作流程

>[!VIDEO](https://video.tv.adobe.com/v/17386?captions=chi_hant)

### 使用視覺體驗撰寫器

這部影片提供關於使用可視化體驗撰寫器選項的資訊。

* 變更頁面的內容
* 變更頁面的配置

>[!VIDEO](https://video.tv.adobe.com/v/17399?captions=chi_hant)