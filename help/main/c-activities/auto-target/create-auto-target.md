---
keywords: 建立自動鎖定目標； A/B測試；自動鎖定目標活動；新a/b活動；自動鎖定目標；針對個人化體驗自動鎖定目標；個人化；最佳化
description: 瞭解如何使用[!UICONTROL 視覺化體驗撰寫器] (VEC)來建立[!UICONTROL 自動鎖定目標] A/B測試活動。
title: 如何建立[!UICONTROL 自動鎖定目標]活動？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Auto-Target
exl-id: 5521740c-eee2-4ba2-8931-cf56d56a4561
TQID: https://experienceleague.adobe.com/qbt-h-4C4uVz6r6xmwKmSeU-RuBdWikmtDQq40dBq9k
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
  - id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 1062
ht-degree: 17%

---

# 建立自動鎖定目標[!UICONTROL 活動]

在[!DNL Adobe Target]中使用[!UICONTROL 視覺化體驗撰寫器] (VEC)，直接在啟用[!DNL Target]的頁面上建立您的[!UICONTROL 自動鎖定目標] [!UICONTROL A/B測試]活動，以及在[!DNL Target]內修改頁面的部分。

>[!NOTE]
>
>[!UICONTROL 自動鎖定目標]屬於[!DNL Target Premium]方案的一部分。 若無 [!DNL Target Standard] 授權，[!DNL Target Premium] 不提供此功能。 如需此授權提供之進階功能的詳細資訊，請參閱 [Target Premium](/help/main/c-intro/intro.md)。

若要建立[!UICONTROL 自動鎖定目標]活動：

1. 在&#x200B;**[!UICONTROL 活動]**&#x200B;清單中，按一下&#x200B;**[!UICONTROL 建立活動]** > **[!UICONTROL A/B測試]**。

1. 從[!UICONTROL 建立A/B測試活動]對話方塊中，視需要選取&#x200B;**[!UICONTROL 視覺]**。

   如果您偏好使用[!UICONTROL 表單式體驗撰寫器]，請選取[!UICONTROL 表單]。 如需詳細資訊，請參閱[表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md)。

   >[!NOTE]
   >
   >除了VEC和[!UICONTROL 表單式體驗撰寫器]，[!DNL Target]還提供[!UICONTROL 單頁應用程式] VEC。 如需各種撰寫器的詳細資訊，請參閱[體驗和產品建議](/help/main/c-experiences/experiences.md)。
   >
   >如需VEC的疑難排解資訊，請參閱[疑難排解視覺化體驗撰寫器](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)。

1. （視條件而定）如果您是[Target Premium客戶](/help/main/c-intro/intro.md#premium)，請從&#x200B;**[!UICONTROL 選擇Workspace]**&#x200B;下拉式清單中選擇[工作區](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)。

   [[!UICONTROL 選擇工作區]](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)選項是[Target Premium](/help/main/c-intro/intro.md)功能，如果您的組織有[!UICONTROL Target Standard]授權，則可能無法顯示。

1. 在&#x200B;**[!UICONTROL 輸入活動URL]**&#x200B;方塊中，指定您的[活動URL](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md)。

   如果您的帳戶[設定了預設的 URL](/help/main/administrating-target/visual-experience-composer-set-up.md)，該 URL 依預設會顯示。 您可以視需要將預設URL變更為其他URL。

1. 按一下&#x200B;**[!UICONTROL 建立]**。

   [!UICONTROL 「可視化體驗撰寫器」]隨即開啟，顯示 URL 中指定的頁面。

1. 按一下「**[!UICONTROL 重新命名]**」圖示（「![重新命名」圖示](/help/main/assets/icons/MoreSmallListVert.svg)），按一下「**[!UICONTROL 重新命名]**」，指定活動的名稱，然後按一下「**[!UICONTROL 儲存]**」。

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
   | ;= | 分號，等於 |
   | ;+ | 分號，加號 |
   | ;- | 分號，減號 |
   | ;@ | 分號， At sign |
   | ,= | 逗號，等於 |
   | ,+ | 逗號，加號 |
   | ,- | 逗號，減號 |
   | ,@ | 逗號， At sign |
   | `[`&quot; | 左方括弧，雙引號 |
   | &quot;`]` | 雙引號，右方括弧 |

1. 建立新體驗，透過變更頁面上的元素。

   建立新活動後，[!UICONTROL 視覺化體驗撰寫器]在左側顯示兩個標籤： [!UICONTROL 體驗A]和[!UICONTROL 體驗B]。[!UICONTROL 體驗A]是控制體驗。 您的焦點在[!UICONTROL 體驗B]索引標籤上，您可以視需要修改此索引標籤。 [!UICONTROL 體驗B]是可新增至測試的替代體驗。 您可以按一下[!UICONTROL 體驗]窗格頂端的[!UICONTROL 新增]圖示（![新增圖示](/help/main/assets/icons/Add.svg)），新增多個體驗至測試。 如果您不想要包括預設網站體驗作為選項，則也可以從活動刪除體驗 A。

   如需在[!UICONTROL 視覺化體驗撰寫器]中新增及修改體驗的詳細資訊，請參閱[新增體驗](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md#task_454646F2895242D3B92DC395A0CE1A00)。 若要修改體驗 B，請從步驟 2 開始。

1. 按一下[!UICONTROL 視覺化體驗撰寫器]頂端的&#x200B;**[!UICONTROL 鎖定目標]**，以前往三步驟引導工作流程中的下一個步驟。

   流程圖表隨即開啟。

   ![A/B 測試鎖定目標步驟](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new-ui.png)

   流程圖表將引導您進行指派對象及其流量百分比、選取流量分配方法，以及指定活動中每個體驗的流量分配的步驟。

1. （視條件而定）按一下&#x200B;**[!UICONTROL 所有訪客]**&#x200B;控制項以選取活動的其他對象。

   [!UICONTROL 所有訪客]對象已設定為預設值。 如果您選取其他對象，其名稱會顯示在最左側的控制項中。

   右側框架隨即顯示，可讓您新增或刪除對象，以及指派活動的訪客百分比。

   1. 若要變更對象，請按一下右側框架中的&#x200B;**[!UICONTROL 取代]圖示** （ ![取代圖示](/help/main/assets/icons/Retweet.svg) ）。
   1. 在[!UICONTROL 新增對象]對話方塊中，[選取所需的對象](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md)，然後按一下&#x200B;**[!UICONTROL 指派對象]**。

      您可以按一下&#x200B;**結合對象**&#x200B;到[建立結合多個對象的對象](/help/main/c-target/combining-multiple-audiences.md)。

      如果您需要建立不在[!UICONTROL 對象庫]中的新對象，請按一下&#x200B;**建立對象**。 在[建立對象工作流程](/help/main/c-target/c-audiences/audiences.md)期間，您可以從下列選項中選擇：

      * **[!UICONTROL 受眾程式庫]**：建立儲存至[!UICONTROL 受眾程式庫]的隨選受眾，以供在其他活動中重複使用
      * **[!UICONTROL 僅此活動]**：建立未儲存至[!UICONTROL 對象庫]且僅能用於目前活動的[活動特定對象](/help/main/c-target/creating-activity-only-audience.md)

   1. 按一下右側框架中的&#x200B;**[!UICONTROL 訪客百分比]**，然後選擇符合您要讓其進入活動之訪客的百分比。

   例如，您可將項目限制為所有訪客的 50%，或「加州人」客群的 45%。

1. 按一下&#x200B;**[!UICONTROL 流量分配]**&#x200B;控制項，然後在右窗格中選擇所需的流量分配方法。 在此案例中，按一下&#x200B;**[!UICONTROL 針對個人化體驗自動鎖定目標]**。

   ![流量分配方法設定](/help/main/c-activities/assets/auto-target.png)

   下列為可用的流量分配方法：

   * **[!UICONTROL 手動（預設）]**：指定您希望在各體驗上看見的加入者百分比。 您可以在所有體驗之間分割百分比，或對每個體驗指定較高或較低的百分比。 所有體驗的總計必須等於 100%。

   * **[!UICONTROL 自動分配至最佳體驗]**：系統會自動將多數活動加入者導向表現較佳的體驗。 有些訪客會被分配至所有體驗，以保持能夠利用體驗並且可識別效能趨勢中的變更。 如需詳細資訊，請參閱[[!UICONTROL 自動分配]總覽](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)。

   * **[!UICONTROL 針對個人化體驗自動鎖定目標]**： [!DNL Target]會使用進階機器學習來個人化內容，並透過識別多個高效能、行銷人員定義的體驗，然後根據訪客的個別客戶設定檔與類似訪客先前的行為，提供訪客量身打造的最佳體驗，藉此促進轉換。 如需詳細資訊，請參閱[自動鎖定目標總覽](/help/main/c-activities/auto-target/auto-target-to-optimize.md)。

1. 按一下右窗格中的&#x200B;**[!UICONTROL 體驗]**，然後指定每個體驗所需的流量分配。

1. 在您滿意您的對象、體驗選擇和流量配置選擇後，請按一下[下一步] **[!UICONTROL 移至三步驟引導式工作流程的第三個步驟。]**

1. 指定活動的[目標與設定](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md)。

   >[!NOTE]
   >
   >如果您想要將[Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T)與此活動搭配使用，請參閱[自動分配和自動鎖定目標活動](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md)的A4T支援中的重要資訊。

1. 按一下&#x200B;**[!UICONTROL 儲存並關閉]**&#x200B;或&#x200B;**[!UICONTROL 儲存]**。

建立活動後，[!UICONTROL 總覽]索引標籤會顯示有關活動的資訊，包括活動的圖表。
