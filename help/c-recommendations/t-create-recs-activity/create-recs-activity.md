---
keywords: 建立建議;Recommendations 活動;新建議;建議概覽
description: 使用 Target 可視化體驗撰寫器 (VEC) 直接在啟用 Target 的頁面上建立建議活動，以及在 Target 內修改頁面的部分。
title: 建立 Recommendations 活動
feature: Recommendations
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '1311'
ht-degree: 78%

---


# ![PREMIUM](/help/assets/premium.png) 建立 Recommendations 活動{#create-a-recommendations-activity}

使用 Target 可視化體驗撰寫器 (VEC) 直接在啟用 Target 的頁面上建立建議活動，以及在 Target 內修改頁面的部分。

1. 按一下&#x200B;**[!UICONTROL 「建立活動」]**>**[!UICONTROL 「Recommendations」]**。

   ![建立 Recommendations 活動](/help/c-recommendations/t-create-recs-activity/assets/Menu_CreateActivity.png)

1. 視需要選取&#x200B;**[!UICONTROL 視覺 (預設)]**。

   ![建立 Recommendations 活動對話方塊](/help/c-recommendations/t-create-recs-activity/assets/DB_NewRecAct.png)

   如果您偏好使用表單式體驗撰寫器，請選取[!UICONTROL 「表單」]。如需詳細資訊，請參閱[表單式體驗撰寫器](/help/c-experiences/form-experience-composer.md)。

   >[!NOTE]
   >
   >除了 VEC 和表單式體驗撰寫器之外，Target 還提供單頁應用程式 VEC 和適用於行動應用程式的 VEC。如需各種撰寫器的詳細資訊，請參閱[體驗和選件](/help/c-experiences/experiences.md)。
   >
   >如遇問題，需要關於 VEC 的疑難排解資訊，請參閱[疑難排解可視化體驗撰寫器](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)。
   >
   >上圖中的[!UICONTROL [選擇工作場所]](/help/administrating-target/c-user-management/property-channel/property-channel.md)選項是[Target Premium](/help/c-intro/intro.md)功能。 如果您沒有看到此選項，表示您的組織擁有的是 Target Standard 授權。

1. (視條件而定) 如果您是 [Target Premium 客戶](/help/c-intro/intro.md#premium)，請選擇[工作區](/help/administrating-target/c-user-management/property-channel/property-channel.md)。

1. 指定活動 URL，然後按&#x200B;**[!UICONTROL 「下一步」]**。

   >[!NOTE]
   >
   >[!DNL Target] 不會區分 URL 通訊協定([!DNL https] 和 [!DNL http])。因此，[!DNL `http://www.adobe.com`] 和 [!DNL `https://wwww.adobe.com`] 都相符。

   活動 URL 為將顯示建議所在的頁面。

   按[!UICONTROL 「下一步」]時，VEC 會開啟並顯示您的頁面。您可以使用建議取代目前的元素，或插入建議。

1. 按一下頁面上的元素，然後如果該元素所在位置有建議，請按一下「取代w/ Recommendations ]**」、「在]**&#x200B;之前插入建議」或「在&#x200B;]**之後插入建議」。**[!UICONTROL **[!UICONTROL **[!UICONTROL 

   只有符合建議資格時，您網站的訪客才會看到建議內容。 不符合建議資格的訪客將會看到預設內容。

   ![Recommendations 選項](/help/c-recommendations/t-create-recs-activity/assets/Menu_Replace-Insert.png)

   * **[!UICONTROL 取代Recommendations]**:以建議取代元素會刪除目前的內容，並以建議取代。當訪客瀏覽您的網站並符合建議資格時，他們會在指定區域看到建議項目，而非現有內容。
   * **[!UICONTROL 先插入建議]**:在選取的元素之前插入建議，將建議的內容置於該元素之前。根據您的頁面建構，建議會顯示在所選元素的上方或左側。
   * **[!UICONTROL 在下列項目後插入建議]**:在選取的元素後插入建議，將建議的內容放在該元素後。依您的頁面建構而定，建議會顯示在選取元素的下方或右側。

   **[!UICONTROL 展開選取範圍]**&#x200B;選項可讓您展開選取的位置（父容器），以協助您更輕鬆地識別並包含所要的頁面元素。

1. 選取頁面類型。

   頁面類型可包括:

   * 購物車頁面
   * 類別頁面
   * 首頁
   * 登陸頁面
   * 產品頁面
   * 搜尋結果頁面
   * 感謝頁面
   * 其他

   ![選取頁面類型選項](/help/c-recommendations/t-create-recs-activity/assets/Menu_PageType.png)

1. 選取[一或多個條件](/help/c-recommendations/c-algorithms/algorithms.md)。

   條件會以卡片的形式顯示，顯示每個條件的相關資訊。依預設，[!UICONTROL 選擇標準]畫面會顯示與您的產業垂直及您在上一步驟中選取的頁面類型相容的標準。 您可以變更這些選項以顯示其他條件。

   >[!NOTE]
   >
   >不是每個條件都能在每個頁面上正確執行。頁面或 mbox 必須傳入 `entity.id` 或 `entity.categoryId`，目前項目/目前類別建議才能相容。一般來說，最好只顯示相容的條件。不過，如果您想要讓不相容的條件可供活動使用，請清除&#x200B;**[!UICONTROL 「相容」]**&#x200B;核取方塊。視您的「Recommendations」設定 ([!UICONTROL 「Recommendations] > **[!UICONTROL 設定]** > **[!UICONTROL 篩選不相容的條件」]**) 而定，系統可能不會顯示&#x200B;**[!UICONTROL 「相容」]**&#x200B;選項。如需詳細資訊，請參閱[設定](/help/c-recommendations/plan-implement.md#concept_C1E1E2351413468692D6C21145EF0B84)。

   ![選取條件對話方塊](/help/c-recommendations/t-create-recs-activity/assets/SCRN_SelectCriteria2.png)

   如果您選取多個條件，流量會在選取的條件間平均分割。例如，如果您已選取了兩個條件，而您的活動是設計為對 20% 的活動加入者顯示預設內容，那麼 40% 的活動加入者將看到每個條件所控制的建議。沒有選項可變更每個條件的百分比。

   * 若要搜尋現有條件 (例如，如果顯示了大量條件卡片)，請在搜尋欄位中輸入內容，直到需要的條件出現為止，接著選取條件，然後按一下&#x200B;**[!UICONTROL 下一步]**。

      有些條件是由 [!DNL Recommendations] 提供。您和您的團隊也可以建立自己的自訂條件。

   * 若要建立新標準，請按一下「建立標準&#x200B;**** > **[!UICONTROL 建立標準]**」，然後填寫新標準的資訊。 如需關於建立新條件的資訊，請參閱[建立條件](/help/c-recommendations/c-algorithms/create-new-algorithm.md)。
   * 您也可以將條件群組為序列。要建立新標準序列，請按一下「建立標準」。 ********&#x200B;如需詳細資訊，請參閱[建立准則序列](/help/c-recommendations/c-algorithms/create-criteria-sequence.md)。

1. 按&#x200B;**[!UICONTROL 「下一步」]**。
1. 選取[設計](/help/c-recommendations/c-design-overview/design-overview.md)。

   設計是一種用來決定位置在您頁面上外觀的範本。[!DNL Target] 包含數種預先設定的設計。您也可以建立自己的自訂設計。如需詳細資訊，請參閱[建立設計](/help/c-recommendations/c-design-overview/create-design.md#task_CC5BD28C364742218C1ACAF0D45E0E14)和[自訂設計](/help/c-recommendations/c-design-overview/customizing-a-template.md#concept_94F1554C3F2E4CDB9A2C3D78F10EDA59)。

   ![選取設計對話方塊](/help/c-recommendations/t-create-recs-activity/assets/Card_SelectDesign.png)

   每個設計會顯示其外觀的圖形呈現，而圖示會顯示目前您的已上線和非使用中的活動有多少使用該設計。

   * 若要選取一或多個現有設計，按一下設計，然後按一下&#x200B;**[!UICONTROL 下一步]**。

      如果您選取了多個條件，則僅能選取一個設計。

   * 若要建立自訂設計，請按一下&#x200B;**[!UICONTROL 建立設計]**，然後填寫新設計的名稱和代碼。按&#x200B;**[!UICONTROL 「下一步」]**，然後選取或上傳影像並按一下&#x200B;**[!UICONTROL 「完成」]**>**[!UICONTROL 「完成」]**。如需關於建立新設計的資訊，請參閱[建立設計](/help/c-recommendations/c-design-overview/create-design.md#task_CC5BD28C364742218C1ACAF0D45E0E14)。

1. 按&#x200B;**[!UICONTROL 「下一步」]**。

   您有選項可將促銷活動新增至您的建議。如需關於新增前端和後端促銷活動的詳細資訊，請參閱[新增促銷活動](/help/c-recommendations/t-create-recs-activity/adding-promotions.md#task_CC5BD28C364742218C1ACAF0D45E0E14)。

1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

   VEC 畫面會在您的頁面上顯示建議的設計。

1. (可選) 按一下&#x200B;**[!UICONTROL 「預覽」]**&#x200B;來查看向訪客呈現的活動效果。

   [!UICONTROL 預覽]模式可讓您與您的建議互動，雖然訪客會這麼做。

   預覽完建議時，請按一下&#x200B;**[!UICONTROL 「撰寫」]**。

1. 在 VEC 中檢閱您的建議，然後按&#x200B;**[!UICONTROL 「下一步」]**。

1. 在流程圖表中檢閱您的 [!DNL Recommendations] 活動，並進行任何必要的變更。

   ![Recommendations 流程圖](/help/c-recommendations/t-create-recs-activity/assets/SCRN_Workflow.png)

   流程圖表將引導您進行選擇活動對象和設定體驗的步驟，並指定成功量度。

   您可從流程圖表執行下列工作: 

   * 變更將看見建議的對象

      >[!NOTE]
      >
      >除了選取現有對象，您還可以[建立僅限於此活動的對象](/help/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483)，或是[結合多個對象](/help/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)來建立隨選對象而非建立新對象。

      依預設，所有使用者都會看到建議。不過，您可以將建議鎖定在特定對象。

      針對 [!DNL Recommendations] 活動，控制群組會看見沒有任何建議的頁面。

   * 檢視條件
   * 變更集合 ([!UICONTROL 「條件」]標籤旁)
   * 變更可看見控制體驗的加入者百分比
   * 檢視設計代碼
   * 變更或移除設計

1. 完成後，按&#x200B;**[!UICONTROL 「下一步」]**。
1. 指定您的活動設定。

   例如，輸入活動的名稱 (必要) 和目標 (可選)。如需關於設定的資訊，請參閱 [Recommendations 活動設定](/help/c-recommendations/t-create-recs-activity/recs-activity-settings.md#reference_3FDA8388CEEC4159949151C1829E2FBB)。

   >[!NOTE]
   >
   >如果指定的 [!DNL Recommendation] 活動名稱是 [!DNL Recommendations Classic] 中另一個已存在活動的名稱，則會將新活動重新同步為新名稱。新名稱為原始名稱附加時間戳記的唯一名稱。這個新名稱會顯示在 [!DNL Target Standard/Premium] 和 [!DNL Recommendations Classic] 中。

1. 完成時，按一下&#x200B;**[!UICONTROL 儲存並關閉]**。

   您的活動概覽隨即顯示。

   從[!UICONTROL 「概覽」]頁面，您可以:

   * 啟動活動
   * 編輯活動
   * 將活動分享到您的Experience Cloud摘要
   * QA活動
   * 檢視您的體驗 URL
   * 下載資料
   * 變更可看見控制體驗的活動加入者百分比
   * 顯示或隱藏條件詳細資料
   * 檢視您的設計的代碼

1. (可選) 開啟[!UICONTROL 「報表」]頁面來檢視可顯示您的 [!DNL Recommendations] 活動效能的報表。

1. (可選) 開啟[!UICONTROL 「衝突」]頁面以檢視可能發生的任何[活動衝突](/help/c-experiences/c-visual-experience-composer/activity-collisions.md)。

   當多個活動設為傳送內容至相同的頁面時會發生活動衝突，並且可能造成顯示未預期的內容。

## 訓練影片: 建立 Recommendations 活動 (7:15)  ![教學課程徽章](/help/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/27688)