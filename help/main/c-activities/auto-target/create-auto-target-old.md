---
keywords: 建立自動鎖定目標； A/B測試；自動鎖定目標活動；新a/b活動；自動鎖定目標；針對個人化體驗自動鎖定目標；個人化；最佳化
description: 瞭解如何在[!UICONTROL Visual Experience Composer]中使用 [!DNL Adobe Target]  (VEC)來建立[!UICONTROL Auto-Target] A/B測試活動。
title: 如何建立[!UICONTROL Auto-Target]活動？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Auto-Target
exl-id: 5521740c-eee2-4ba2-8931-cf56d56a4561
source-git-commit: 32a91a41cd182d3a55ded7dea8c1c6ea6f46aa71
workflow-type: tm+mt
source-wordcount: '795'
ht-degree: 42%

---

# 建立[!UICONTROL Auto-Target]活動

在[!UICONTROL Visual Experience Composer]中使用[!DNL Adobe Target] (VEC)直接在啟用[!UICONTROL Auto-Target]的頁面上建立您的[!UICONTROL A/B Test] [!DNL Target]活動，以及在[!DNL Target]內修改頁面的部分。

>[!NOTE]
>
>[!UICONTROL Auto-Target]是[!DNL Target Premium]解決方案的一部分。 若無 [!DNL Target Standard] 授權，[!DNL Target Premium] 不提供此功能。如需此授權提供之進階功能的詳細資訊，請參閱 [Target Premium](/help/main/c-intro/intro.md)。

若要建立[!UICONTROL Auto-Target]活動：

1. 從&#x200B;**[!UICONTROL Activities]**&#x200B;清單，按一下&#x200B;**[!UICONTROL Create Activity]** > **[!UICONTROL A/B Test]**。

   ![建立活動下拉式清單](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_select-new.png)

   可用的活動類型取決於您的 [!DNL Target] 帳戶。有些活動類型可能不會出現在您的清單中。例如，[!UICONTROL Recommendations]是[Target Premium功能](/help/main/c-intro/intro.md#premium)。 如需各種活動類型的相關資訊，請參閱[活動](/help/main/c-activities/activities.md)和 [Target 活動指南](/help/main/c-activities/target-activities-guide.md)。

1. 視需要選取&#x200B;**[!UICONTROL Visual]**。

   如果您偏好使用[!UICONTROL Form-Based Experience Composer]，請選取[!UICONTROL Form]。 如需詳細資訊，請參閱[表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md)。

   >[!NOTE]
   >
   >除了VEC和[!UICONTROL Form-Based Experience Composer]，[!DNL Target]還提供單頁應用程式VEC。 如需各種撰寫器的詳細資訊，請參閱[體驗和產品建議](/help/main/c-experiences/experiences.md)。
   >
   >如遇問題，需要關於 VEC 的疑難排解資訊，請參閱[疑難排解可視化體驗撰寫器](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)。

1. (視條件而定) 如果您是 [Target Premium 客戶](/help/main/c-intro/intro.md#premium)，請選擇[工作區](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)。

1. 指定您的[活動URL](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md)，然後按一下&#x200B;**[!UICONTROL Next]**。

   如果您的帳戶設定了預設的 URL，該 URL 依預設會顯示。您可以將預設 URL 變更為其他 URL。

   [!UICONTROL Visual Experience Composer]隨即開啟，顯示URL中指定的頁面。

   ![VEC](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/vec-new.png)

1. 在提供的空間中輸入活動的名稱。

   ![名稱欄位](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_newname-new.png)

   活動名稱的開頭不能是下列任一字元：

   | 字元 | 說明 |
   |--- |--- |
   | `=` | 等號 |
   | `+` | 加號 |
   | `-` | 減號 |
   | `@` | 「@」符號 |

1. 建立任何體驗，透過變更頁面上的元素。

   建立活動後，[!UICONTROL Visual Experience Composer]在左側顯示兩個標籤：體驗A和體驗B。體驗A是控制體驗。 您的焦點在體驗B索引標籤，您可以視需要修改它。 體驗B是可新增至測試的替代體驗。 您可以對測試新增多個體驗。如果您不想要包括預設網站體驗作為選項，則也可以從活動刪除體驗 A。

   如需在[!UICONTROL Visual Experience Composer]中新增及修改體驗的詳細資訊，請參閱[新增體驗](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md)。 若要修改體驗 B，請從步驟 2 開始。

1. 按一下&#x200B;**[!UICONTROL Targeting]**&#x200B;頂端的[!UICONTROL Visual Experience Composer]，以前往三步驟引導工作流程中的下一個步驟。

   流程圖表隨即開啟。

   ![A/B 測試鎖定目標步驟](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new.png)

   流程圖表將引導您進行選擇活動客群和設定體驗的步驟。

1. 在[!UICONTROL Audience]方塊中，按一下編輯圖示（垂直省略符號），按一下&#x200B;**[!UICONTROL Replace Audience]**，然後[為您的活動選取對象](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md)。

   依預設，對象會設為[!UICONTROL All Visitors]。

1. 選擇符合您要讓其進入活動之訪客的百分比。

   ![客群百分比](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/audperc-new.png)

   例如，您可將項目限制為所有訪客的 50%，或「加州人」客群的 45%。

1. 設定您的流量分配。

   您可以對相同對象顯示多個體驗。系統會顯示圖表，顯示您選取的對象以及您已新增至活動的體驗。

   選擇所需的流量分配方法。 若要建立[!UICONTROL Auto-Target]活動，請選取&#x200B;**[!UICONTROL Auto-Target for personalized experiences]**。

   三種流量分配型別說明如下：

   * **[!UICONTROL Manual (Default)]**：指定您希望在各體驗上看見的加入者百分比。 您可以在所有體驗之間分割百分比，或對每個體驗指定較高或較低的百分比。所有體驗的總計必須等於 100%。如需詳細資訊，請參閱[建立A/B測試](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)。

   * **[!UICONTROL Auto-Allocate to best experience]**：系統會自動將多數活動加入者導向表現較佳的體驗。 有些訪客會被分配至所有體驗，以保持能夠利用體驗並且可識別效能趨勢中的變更。如需詳細資訊，請參閱[自動分配總覽](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)。

   * **[!UICONTROL Auto-Target for personalized experiences]**： [!DNL Target]會使用進階機器學習來個人化內容，並透過識別多個高效能、行銷人員定義的體驗，然後根據訪客的個別客戶設定檔與類似訪客先前的行為，提供訪客量身打造的最佳體驗，藉此促進轉換。

   您也可以按一下「**[!UICONTROL Add]**」以新增其他體驗至活動。

1. 在您滿意您的對象、體驗選擇和流量配置選擇後，請按一下&#x200B;**[!UICONTROL Next]**&#x200B;以移至三步驟引導式工作流程的第三個步驟。

1. 指定活動的[目標與設定](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md)。

   >[!NOTE]
   >
   >如果您想要將[Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T)與此活動搭配使用，請參閱[自動分配和自動鎖定目標活動](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md)的A4T支援中的重要資訊。

1. 按一下&#x200B;**[!UICONTROL Save & Close]**&#x200B;或&#x200B;**[!UICONTROL Save]**。

建立活動後，[!UICONTROL Overview]索引標籤會顯示有關活動的資訊，包括活動的圖表。

## 訓練影片：建立A/B測試(8:36)

此影片示範如何使用 [!DNL Target] 三個步驟引導工作流程來建立 A/B 測試。

* 在[!UICONTROL A/B Test]中建立[!DNL Adobe Target]活動
* 使用手動分割或自動流量分配來分配流量

>[!VIDEO](https://video.tv.adobe.com/v/17391)
