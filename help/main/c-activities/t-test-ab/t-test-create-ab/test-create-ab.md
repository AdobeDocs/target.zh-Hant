---
keywords: 建立A/B； A/B測試； A/B活動；新a/b活動；建立a/b
description: 使用[!UICONTROL Visual Experience Composer] (VEC)直接在啟用 [!DNL Target]的頁面上建立A/B測試活動。
title: 如何建立A/B測試？
feature: A/B Tests
exl-id: 76002873-0b7c-44a8-8e89-8ad28b63eccb
source-git-commit: 9cc1eb4c5c95ea51bc0a1fc9e89b245a18c9914b
workflow-type: tm+mt
source-wordcount: '888'
ht-degree: 17%

---

# 建立A/B測試活動

運用[!DNL Adobe Target]中的[!UICONTROL Visual Experience Composer] (VEC)，直接在啟用[!DNL Target]的頁面上建立[!UICONTROL A/B Test]活動，以及修改[!DNL Target]內的頁面區段。

>[!NOTE]
>
>除了[!UICONTROL Manual] （預設） [!UICONTROL A/B Test]活動（本文中討論）之外，[!DNL Target]還提供另外兩種型別的[!UICONTROL A/B Test]活動： [!UICONTROL Auto-Allocate]和[!UICONTROL Auto-Target]。
>
>檢視&#x200B;*A/B測試總覽*&#x200B;中的[A/B測試活動型別](/help/main/c-activities/t-test-ab/test-ab.md#types)。

若要建立手動[!UICONTROL A/B Test]活動：

1. 從&#x200B;**[!UICONTROL Activities]**&#x200B;清單，按一下&#x200B;**[!UICONTROL Create Activity]** > **[!UICONTROL A/B Test]**。

1. 必要時，從[!UICONTROL Create A/B Test Activity]對話方塊選取&#x200B;**[!UICONTROL Visual]**。

   如果您偏好使用[!UICONTROL Form-Based Experience Composer]，請選取[!UICONTROL Form]。 如需詳細資訊，請參閱[表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md)。

   >[!NOTE]
   >
   >除了VEC和[!UICONTROL Form-Based Experience Composer]，[!DNL Target]還提供[!UICONTROL Single Page Application] VEC。 如需各種撰寫器的詳細資訊，請參閱[體驗和產品建議](/help/main/c-experiences/experiences.md)。
   >
   >如需VEC的疑難排解資訊，請參閱[疑難排解視覺化體驗撰寫器](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)。

1. （視條件而定）如果您是[Target Premium客戶](/help/main/c-intro/intro.md#premium)，請從&#x200B;**[!UICONTROL Choose Workspace]**&#x200B;下拉式清單中選擇[工作區](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)。

   [[!UICONTROL Choose Workplace]](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)選項是[Target Premium](/help/main/c-intro/intro.md)功能，如果貴組織擁有[!UICONTROL Target Standard]授權，可能無法顯示。

1. 在&#x200B;**[!UICONTROL Enter Activity URL]**&#x200B;方塊中，指定您的[活動URL](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md)。

   如果您的帳戶[設定了預設的 URL](/help/main/administrating-target/visual-experience-composer-set-up.md)，該 URL 依預設會顯示。您可以視需要將預設URL變更為其他URL。

1. 按一下 **[!UICONTROL Create]**。

   [!UICONTROL Visual Experience Composer]隨即開啟，顯示URL中指定的頁面。

1. 若要命名活動，請按一下「[!UICONTROL Untitled Activity]」旁的&#x200B;**[!UICONTROL Edit]**&#x200B;圖示（![編輯圖示](/help/main/assets/icons/Edit.svg) ），指定活動的描述性名稱，然後按一下&#x200B;**[!UICONTROL Save]**。

   活動名稱的開頭不能是下列任一字元：

   | 字元 | 說明 |
   |--- |--- |
   | `=` | 等號 |
   | `+` | 加號 |
   | `-` | 減號 |
   | `@` | 「@」符號 |

   活動名稱不能包含下列任一字元順序：

   | 字元順序 | 說明 |
   |--- |--- |
   | ；= | 分號，等於 |
   | ；+ | 分號，加號 |
   | ；- | 分號，減號 |
   | ；@ | 分號， At sign |
   | ，= | 逗號，等於 |
   | ，+ | 逗號，加號 |
   | ，- | 逗號，減號 |
   | ，@ | 逗號， At sign |
   | `[`&quot; | 左方括弧，雙引號 |
   | &quot;`]` | 雙引號，右方括弧 |

1. 建立新體驗，透過變更頁面上的元素。

   建立新活動後，[!UICONTROL Visual Experience Composer]在左側顯示兩個標籤：體驗A和體驗B。體驗A是控制體驗。 您的焦點在體驗B索引標籤，您可以視需要修改它。 體驗B是可新增至測試的替代體驗。 您可以按一下[!UICONTROL Experiences]窗格頂端的[!UICONTROL Add]圖示（![新增圖示](/help/main/assets/icons/Add.svg) ），新增多個體驗至測試。 如果您不想要包括預設網站體驗作為選項，則也可以從活動刪除體驗 A。

   如需在[!UICONTROL Visual Experience Composer]中新增及修改體驗的詳細資訊，請參閱[新增體驗](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md#task_454646F2895242D3B92DC395A0CE1A00)。 若要修改體驗 B，請從步驟 2 開始。

1. 按一下[!UICONTROL Visual Experience Composer]頂端的&#x200B;**[!UICONTROL Targeting]**，以前往三步驟引導工作流程中的下一個步驟。

   流程圖表隨即開啟。

   ![A/B 測試鎖定目標步驟](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new-ui.png)

   流程圖表將引導您進行指派對象及其流量百分比、選取流量分配方法，以及指定活動中每個體驗的流量分配的步驟。

1. （視條件而定）按一下&#x200B;**[!UICONTROL All Visitors]**&#x200B;控制項以選取活動的其他對象。

   [!UICONTROL All Visitors]對象已設定為預設值。 如果您選取其他對象，其名稱會顯示在最左側的控制項中。

   右側框架隨即顯示，可讓您新增或刪除對象，以及指派活動的訪客百分比。

   1. 若要變更對象，請按一下右側框架中的&#x200B;**[!UICONTROL Replace]圖示** （ ![取代圖示](/help/main/assets/icons/Retweet.svg) ）。
   1. 在[!UICONTROL Add Audience]對話方塊中，[選取所需的對象](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md)，然後按一下&#x200B;**[!UICONTROL Assign Audience]**。

      您可以按一下&#x200B;**結合對象**&#x200B;到[建立結合多個對象的對象](/help/main/c-target/combining-multiple-audiences.md)。

      如果您需要建立不在[!UICONTROL Audience Library]中的新對象，請按一下&#x200B;**建立對象**。 在[建立對象工作流程](/help/main/c-target/c-audiences/audiences.md)期間，您可以從下列選項中選擇：

      * **[!UICONTROL Audience Library]**：建立儲存至[!UICONTROL Audience Library]、可於其他活動中重複使用的隨選對象。
      * **[!UICONTROL This activity only]**：建立未儲存至[!UICONTROL Audience Library]且只能用於目前活動的[活動特定對象](/help/main/c-target/creating-activity-only-audience.md)。

   1. 按一下右側框架中的&#x200B;**[!UICONTROL Visitor Percentage]**，然後選擇符合您要讓其進入活動之訪客的百分比。

   例如，您可將項目限制為所有訪客的 50%，或「加州人」客群的 45%。

1. 按一下&#x200B;**[!UICONTROL Traffic Allocation]**&#x200B;控制項，然後在右窗格中選擇所需的流量分配方法，如下所示：

   ![流量分配方法設定](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/traffic-allocation-method-new.png)

   選擇所需的流量分配方法:

   * **[!UICONTROL Manual (Default)]**：指定您希望在各體驗上看見的加入者百分比。 您可以在所有體驗之間分割百分比，或對每個體驗指定較高或較低的百分比。所有體驗的總計必須等於 100%。

   * **[!UICONTROL Auto-Allocate to best experience]**：系統會自動將多數活動加入者導向表現較佳的體驗。 有些訪客會被分配至所有體驗，以保持能夠利用體驗並且可識別效能趨勢中的變更。如需詳細資訊，請參閱[[!UICONTROL Auto-Allocate]總覽](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)。

   * **[!UICONTROL Auto-Target for personalized experiences]**： [!DNL Target]會使用進階機器學習來個人化內容，並透過識別多個高效能、行銷人員定義的體驗，然後根據訪客的個別客戶設定檔與類似訪客先前的行為，提供訪客量身打造的最佳體驗，藉此促進轉換。 如需詳細資訊，請參閱[自動鎖定目標總覽](/help/main/c-activities/auto-target/auto-target-to-optimize.md)。

1. 按一下右窗格中的&#x200B;**[!UICONTROL Experiences]**，然後指定每個體驗所需的流量分配。

1. 在您滿意您的對象、體驗選擇和流量配置選擇後，請按一下&#x200B;**[!UICONTROL Next]**&#x200B;以移至三步驟引導式工作流程的第三個步驟。

1. 指定活動的[目標與設定](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md)。

1. 按一下&#x200B;**[!UICONTROL Save & Close]**&#x200B;或&#x200B;**[!UICONTROL Save]**。

建立活動後，[!UICONTROL Overview]索引標籤會顯示有關活動的資訊，包括活動的圖表。
