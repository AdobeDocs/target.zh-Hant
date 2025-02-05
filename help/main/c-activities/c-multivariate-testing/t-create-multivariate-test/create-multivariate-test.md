---
keywords: MVT; 多變數測試; 多變數測試建立; 多變數測試建立; MVT 建立; MVT 建立; MVT 如何; 多變數測試如何
description: 瞭解如何在 [!DNL Adobe Target] 中使用[!UICONTROL Visual Experience Composer] (VEC)來建立[!UICONTROL Multivariate Test] (MVT)。
title: 如何建立[!UICONTROL Multivariate Test]？
feature: Multivariate Tests
exl-id: 7712b747-543a-4e19-b689-bea36c44805c
source-git-commit: be118753eed999ce24d547c90ac9d195cce7e9e9
workflow-type: tm+mt
source-wordcount: '724'
ht-degree: 26%

---

# 建立多變數測試

[!DNL Adobe Target]中的[!UICONTROL Visual Experience Composer] (VEC)可讓您輕鬆建立[!UICONTROL Multivariate Test]，以及在[!DNL Target]內修改頁面的部分。

[!DNL Target]點選編輯器可讓您挑選任何位置並新增多個選件。

[!UICONTROL Multivariate Test] (MVT)需要頁面優先的報表。 換句話說，測試會在具有您為頁面所設計體驗的特定 URL 上執行。

1. 按一下&#x200B;**[!UICONTROL Create Activity]** > **[!UICONTROL Multivariate Test]**。

   >[!NOTE]
   >
   >如需有關 [!DNL Target] 提供的各種活動類型及其差異的詳細資訊，請參閱[活動](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)。請參閱[Target 活動類型](/help/main/c-activities/target-activities-guide.md)，協助您決定哪種活動類型最適合您的需求。

1. （視條件而定）選擇傳遞型別： [!UICONTROL Web]、[!UICONTROL Mobile]、[!UICONTROL Email]或[!UICONTROL Other/API]。

1. （視條件而定）如果您是[Target Premium](/help/main/c-intro/intro.md#premium)客戶，[請選擇工作區](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)。

1. [為您要測試的頁面指定URL](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/url.md#concept_C12E4A85FF3B4E518E3110F6CF1AF9C0)，然後按一下&#x200B;**[!UICONTROL Create]**。

   >[!NOTE]
   >
   >請使用完整的URL，開頭要包括HTTP或HTTPS。

   如果出現訊息，要求您啟用您的瀏覽器使用混合的內容，請遵循訊息中的說明。為您的瀏覽器啟用混合的內容之後，請從步驟 1 重新開始。

   [!UICONTROL Visual Experience Composer]隨即開啟。

1. 
   1. 按一下&#x200B;**[!UICONTROL Rename]**&#x200B;圖示（![重新命名圖示](/help/main/assets/icons/MoreSmallListVert.svg)）、按一下&#x200B;**[!UICONTROL Rename]**、指定活動的名稱，然後按一下&#x200B;**[!UICONTROL Save]**。

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

1. [在每個位置中建立產品建議](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/add-offers.md#concept_DCE6B45C30F7419B8EC17AFDEE8D8AA6)。

   您可以新增下列類型的產品建議:

   * HTML
   * 影像
   * 文字

1. 按一下&#x200B;**[!UICONTROL Preview]**&#x200B;以[預覽您的體驗](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/preview-experiences.md)。

1. 按一下&#x200B;**[!UICONTROL Show Experiences]**&#x200B;圖示（![顯示體驗圖示](/help/main/assets/icons/WebPages.svg) ）以顯示左側框架中的所有體驗清單。

1. 按一下清單中的特定體驗來檢視該體驗。

1. （視條件而定）若要將一或多個體驗從活動中排除，請按一下&#x200B;**[!UICONTROL Manage Content]**&#x200B;圖示（ ![管理體驗圖示](/help/main/assets/icons/Experience.svg) ）以顯示[!UICONTROL Manage Experiences]對話方塊。

1. （視條件而定）在[!UICONTROL Manage Experiences]對話方塊中，按一下您要排除的體驗旁的&#x200B;**[!UICONTROL More Actions]**&#x200B;圖示（ ![更多動作圖示](/help/main/assets/icons/MoreSmallList.svg) ），然後按一下&#x200B;**[!UICONTROL Exclude]**。

   您可能會選擇排除顯示發生衝突變數的體驗，或是審美觀點上不平衡的體驗。

1. （視條件而定）若要排除多個體驗，請選取所需體驗的核取方塊，然後按一下&#x200B;**[!UICONTROL Exclude]**。

1. [使用流量估算程式](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714)來測試您的測試計劃的可行性。

1. 按一下「**[!UICONTROL Next]**」以進入[!UICONTROL Targeting]頁面。

   如果您曾使用其他[!DNL Target]活動型別，**鎖定目標**&#x200B;步驟看起來會很熟悉。 您可以在此選取受眾，並指定看到每個體驗的訪客百分比。

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

1. [檢閱測試摘要](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/test-summary.md#reference_971AB225963A4DC18EEB5B0E20F0A4A7)並進行任何需要的變更，然後按一下&#x200B;**[!UICONTROL Next]**。

1. [指定測試的目標與設定](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)。

1. 按一下&#x200B;**[!UICONTROL Save and Close]**&#x200B;以建立活動。

## 訓練影片：建立多變數測試(9:25) ![教學課程徽章](/help/main/assets/tutorial.png)

此影片示範如何使用[!DNL Target]三步驟引導式工作流程來規劃和建立多變數測試。

* 定義和設計多變數測試
* 建立多變數測試

>[!VIDEO](https://video.tv.adobe.com/v/17395)
