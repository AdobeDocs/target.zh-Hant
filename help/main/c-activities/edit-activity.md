---
keywords: 活動；活動型別；編輯活動；編輯；複製
description: 瞭解您可以編輯現有活動的不同方式。
title: 如何編輯活動？
feature: Activities
exl-id: 5f2a930a-9950-430e-a898-50af1f917ec1
source-git-commit: cf7bc0f9ce72d5a170db76f5a932b196d4e1ddb0
workflow-type: tm+mt
source-wordcount: '890'
ht-degree: 28%

---

# 編輯活動

瞭解如何編輯[!DNL Adobe Target]中的現有活動。 本文介紹[!DNL Target]介面中可用來修改活動的不同方法。 無論您是要更新體驗、調整鎖定目標規則或設定目標，[!DNL Target]都可以確保在啟用之前安全地儲存您的變更。

[!DNL Target]在UI中提供可以編輯現有活動的各種位置。 程式會依您選擇的方法而有所不同。

## 在活動頁面上使用暫留[!UICONTROL More Actions]圖示來編輯活動 {#section_29EE2ECA6B88473A8F9AC5600FFBB174}

1. 從&#x200B;**[!UICONTROL Activities]**&#x200B;頁面，按一下您要編輯的活動旁的&#x200B;**[!UICONTROL More Actions]**&#x200B;圖示（![更多動作圖示](/help/main/assets/icons/MoreSmall.svg) ），然後按一下&#x200B;[!UICONTROL **編輯**]。

   Target會在[!UICONTROL Visual Experience Composer] (VEC)中開啟活動，而您會看到[!UICONTROL Experiences]頁面（三步驟引導式工作流程的第一步）。

1. 視需要使用 [VEC 選項](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)編輯活動。

1. 按一下&#x200B;**[!UICONTROL Next]**&#x200B;以前往下一個步驟，然後進行任何必要的編輯。

1. 前往&#x200B;**目標與設定**&#x200B;頁面時，您有以下選項：

   * **[!UICONTROL Save & Close]：**&#x200B;按一下&#x200B;**[!UICONTROL Save and Close]**&#x200B;以儲存您的變更並顯示活動的[!UICONTROL Overview]頁面。
   * **儲存：**&#x200B;按一下&#x200B;**[!UICONTROL More Actions]**&#x200B;圖示（![更多動作圖示](/help/main/assets/icons/MoreSmallListVert.svg) ），然後選取&#x200B;**[!UICONTROL Save]**&#x200B;以儲存您的變更並留在VEC中，讓您可以繼續變更。 等候儲存完成，之後再進行其他變更。儲存完成後，VEC 會透過重新整理的變更重新載入。

## 從[!UICONTROL Activities]頁面按一下活動名稱以編輯活動 {#section_176180DAD17E40CEA441903F39E0AA1C}

1. 若要避免逐步執行工作流程，請從「[!UICONTROL Activities]」頁面中按一下所需的活動以開啟，從「**[!UICONTROL Edit Activity]**」下拉式清單中選取選項，然後選取所需的選項。

   * **編輯體驗：**&#x200B;帶您直接前往[!UICONTROL Experiences]頁面（三步驟引導式工作流程的第一步）。
   * **編輯鎖定目標**：帶您直接前往[!UICONTROL Targeting]頁面（三步驟引導式工作流程的第二步）。
   * **[!UICONTROL Goals & Settings]**：帶您直接前往[!UICONTROL Goals & Settings]頁面（三步驟引導式工作流程中的第三個步驟）。

1. 進行所需的變更，然後儲存活動。

   * **[!UICONTROL Save & Close]：**&#x200B;按一下&#x200B;**[!UICONTROL Save and Close]**&#x200B;以儲存您的變更並顯示活動的[!UICONTROL Overview]頁面。
   * **儲存：**&#x200B;按一下&#x200B;**[!UICONTROL More Actions]**&#x200B;圖示（![更多動作圖示](/help/main/assets/icons/MoreSmallListVert.svg) ），然後選取&#x200B;**[!UICONTROL Save]**&#x200B;以儲存您的變更並留在VEC中，讓您可以繼續變更。 等候儲存完成，之後再進行其他變更。儲存完成後，VEC 會透過重新整理的變更重新載入。

## 使用在[!DNL Recommendations Classic]中建立的舊版活動 {#classic}

[!UICONTROL Activities]清單顯示在各種來源中建立的活動，包括[!DNL Recommendations Classic]。 使用在 [!DNL Recommendations Classic] 中建立的舊版活動時，以下是可供使用的動作:

* [!UICONTROL Activate]
* [!UICONTROL Deactivate]
* [!UICONTROL Archive]
* [!UICONTROL Copy]
* [!UICONTROL Delete]

您無法直接編輯 [!DNL Recommendations] 活動。若要編輯活動，您應使用 [!DNL Target Premium] 建立活動複本，然後儲存新建立的活動。接著即可視需要編輯這個新建立的活動。

## 以草稿形式儲存活動 {#section_968CD7A63027432EBD8FAE3A0F7404C3}

另存為草稿功能已無法使用。 如需詳細資訊，請參閱&#x200B;*[!UICONTROL Status]*&#x200B;將篩選器套用至活動清單[下的](/help/main/c-activities/activities.md#filters)。

## 使用工作區時複製/編輯活動 {#section_45A92E1DD3934523B07E71EF90C4F8B6}

工作區可讓組織將特定一組使用者指派至特定一組屬性。工作區有許多地方皆與 [!DNL Adobe Analytics] 中的報表套裝相似。

>[!NOTE]
>
>工作區是 [!DNL Target Premium] 解決方案所提供的「屬性和權限」功能的一部分。在沒有 [!DNL Target Standard] 授權的 [!DNL Target Premium] 中無法使用。

如果您屬於多國組織，可能會有一個工作區用於歐洲網頁、屬性或網站，以及另一個工作區用於美洲網頁、屬性或網站。如果您屬於多品牌組織，則可能會有每個品牌的個別工作區。

如需工作區與「企業使用者許可權」功能的詳細資訊，請參閱[企業使用者許可權](/help/main/administrating-target/c-user-management/property-channel/property-channel.md#concept_E396B16FA2024ADBA27BC056138F9838)。

如果環境中已啟用「企業使用者權限」，您可以將活動複製到同一個工作區，或另一個工作區。您目前無法將活動從一個工作區移動至另一個工作區。若要將活動複製到另一個工作區，請從[!UICONTROL Activities]頁面，按一下您要複製之活動旁的&#x200B;**[!UICONTROL More Actions]**&#x200B;圖示（![更多動作圖示](/help/main/assets/icons/MoreSmall.svg) ），然後按一下&#x200B;[!UICONTROL **複製**]&#x200B;或&#x200B;**[!UICONTROL Edit]**。

在工作區中使用複製/編輯功能時，請考量下列資訊:

* 如果您將同一工作區中的活動或從預設工作區複製到非預設工作區，則會自動開啟「活動精靈」。 在跨工作區副本中，您可能只需要更新活動屬性。
* 將活動從非預設工作區複製到另一個工作區（無論預設或非預設）時，活動精靈會開啟，並且需要一些手動輸入才能完成設定：
   * **[!UICONTROL Properties]**：不同工作區之間的屬性可能不同。 此情況可能會觸發警告：

      * 在[!UICONTROL Form-Based Experience Composer]中，警告會直接顯示在使用者介面中，以便立即顯示。

        ![表單式工作區警告](/help/main/c-activities/assets/form-based-warning.png)

      * 在VEC中，按一下[!UICONTROL Configure] > [!UICONTROL Properties]時會顯示警告。

        ![vec警告](/help/main/c-activities/assets/vec-warning.png)

        若要解決此問題，請按一下[!UICONTROL Add/Remove]，以便只顯示目的地工作區中可用的屬性以供選取。

   * **對象和選件**：必須取代原始工作區中的所有對象和選件。 或者，您可以從[!UICONTROL Audiences]或[!UICONTROL Offers]頁面複製它們，然後從活動內的對應清單中選取適當的專案。

   * **必要的手動變更**：所有必要的手動變更都摘要於最後步驟([!UICONTROL Save & Close])。 快顯視窗會顯示需要更新的實體清單，有助於確保在完成活動設定之前完成所有必要的調整。

     ![Workspace驗證警告](/help/main/c-activities/assets/work-space-validation.png)

如果您的環境未啟用[!UICONTROL Enterprise User Permissions]功能，則在複製之前，所有活動都會以編輯模式開啟。