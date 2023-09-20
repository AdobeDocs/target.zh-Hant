---
keywords: 建立A/B； A/B測試； A/B活動；新a/b活動；建立a/b
description: 瞭解如何在Adobe中使用視覺化體驗撰寫器(VEC) [!DNL Target] 若要直接在建立A/B測試活動 [!DNL Target]-enabled頁面。
title: 如何建立A/B測試？
feature: A/B Tests
exl-id: 76002873-0b7c-44a8-8e89-8ad28b63eccb
source-git-commit: ec1041fd1823d1ab7f1af147af5825c3ae8662b5
workflow-type: tm+mt
source-wordcount: '926'
ht-degree: 44%

---

# 建立 A/B 測試

使用 [!UICONTROL 視覺化體驗撰寫器] (VEC)輸入 [!DNL Adobe Target] 建立您的 [!UICONTROL A/B測試] 活動直接在 [!DNL Target] — 啟用頁面，並修改頁面部分於 [!DNL Target].

>[!NOTE]
>
>除了手動（預設） [!UICONTROL A/B測試] 活動（將在本文中探討）， [!DNL Target] 提供另外兩種型別 [!UICONTROL A/B測試] 活動： [!UICONTROL 自動分配] 和 [!UICONTROL 自動鎖定目標].
>
>另請參閱 [A/B測試活動的型別](/help/main/c-activities/t-test-ab/test-ab.md#types) 在 *A/B測試概覽*.

若要建立手動 [!UICONTROL A/B測試] 活動：

1. 從&#x200B;**[!UICONTROL 「活動」]**&#x200B;清單，按一下&#x200B;**[!UICONTROL 「建立活動」]**>**[!UICONTROL 「A/B 測試」]**。

   ![建立活動下拉式清單](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_select-new.png)

   >[!NOTE]
   >
   >可用的活動類型取決於您的 [!DNL Target] 帳戶。有些活動類型可能不會出現在您的清單中。例如，[!UICONTROL Recommendations] 是 [Target Premium 功能](/help/main/c-intro/intro.md#premium)。
   >
   >如需各種活動類型的相關資訊，請參閱[活動](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)和 [Target 活動指南](/help/main/c-activities/target-activities-guide.md)。

1. 從建立A/B測試活動對話方塊中，選取 **[!UICONTROL 視覺（預設）]**，如有必要。

   如果您偏好使用 [!UICONTROL 表單式體驗撰寫器]，選取 [!UICONTROL 表單]. 如需詳細資訊，請參閱[表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md)。

   >[!NOTE]
   >
   >除了VEC和 [!UICONTROL 表單式體驗撰寫器]， [!DNL Target] 提供單頁應用程式VEC。 如需各種撰寫器的詳細資訊，請參閱[體驗和選件](/help/main/c-experiences/experiences.md)。
   >
   >如遇問題，需要關於 VEC 的疑難排解資訊，請參閱[疑難排解可視化體驗撰寫器](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)。

1. （視條件而定）如果您是 [Target Premium客戶](/help/main/c-intro/intro.md#premium)，來自 **[!UICONTROL 選擇工作區]** 從下拉式清單中選擇 [工作區](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

   此 [[!UICONTROL 選擇工作場所]](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) 上圖中的選項為 [Target Premium](/help/main/c-intro/intro.md) 功能，如果貴組織擁有 [!UICONTROL Target Standard] 授權。

1. 在 **[!UICONTROL 輸入活動URL]** 方塊，指定您的 [活動URL](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md)，然後按一下 **[!UICONTROL 建立]**.

   如果您的帳戶[設定了預設的 URL](/help/main/administrating-target/visual-experience-composer-set-up.md)，該 URL 依預設會顯示。您可以視需要將預設URL變更為其他URL。

   [!UICONTROL 「可視化體驗撰寫器」]隨即開啟，顯示 URL 中指定的頁面。

1. 按一下 **[!UICONTROL 未命名的活動]** 在VEC頂端，然後在提供的空間中指定活動的名稱。

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
   | ;+ | 分號，加號 |
   | ;- | 分號，減號 |
   | ;@ | 分號， At sign |
   | ,= | 逗號，等於 |
   | ,+ | 逗號，加號 |
   | ,- | 逗號，減號 |
   | ,@ | 逗號， At sign |
   | `[`&quot; | 左方括弧，雙引號 |
   | &quot;`]` | 雙引號，右方括弧 |

1. 建立任何新體驗，透過變更頁面上的元素。

   在您建立新增活動之後，[!UICONTROL 可視化體驗撰寫器]會在左邊顯示兩個標籤: 體驗 A 和體驗 B。體驗 A 為控制體驗。您的焦點在體驗B索引標籤，您可以視需要修改它。 體驗B是可新增至測試的替代體驗。 您可以對測試新增多個體驗。如果您不想要包括預設網站體驗作為選項，則也可以從活動刪除體驗 A。

   如需在[!UICONTROL 可視化體驗撰寫器]中新增和修改體驗的相關資訊，請參閱[新增體驗](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md#task_454646F2895242D3B92DC395A0CE1A00)。若要修改體驗 B，請從步驟 2 開始。

1. 按一下&#x200B;**[!UICONTROL 可視化體驗撰寫器]**&#x200B;頂端的[!UICONTROL 鎖定目標]，以前往三步驟引導工作流程中的下一個步驟。

   流程圖表隨即開啟。

   ![A/B 測試鎖定目標步驟](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new.png)

   流程圖表將引導您進行選擇活動對象和設定體驗的步驟。

1. 在 **[!UICONTROL 對象]** 方塊中，按一下編輯圖示（垂直的省略符號），然後按一下 **[!UICONTROL 取代對象]**，然後 [選取對象](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) （適用於您的活動）。

   依預設，對象會設為 [!UICONTROL 所有訪客].

1. 選擇符合您要讓其進入活動之訪客的百分比。

   ![受眾百分比](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/audperc-new.png)

   例如，您可將項目限制為所有訪客的 50%，或「加州人」觀眾的 45%。

1. 設定您的流量分配。

   您可以對相同對象顯示多個體驗。系統會顯示圖表，顯示您選取的對象以及您新增至活動的體驗。

   選擇所需的流量分配方法:

   * **[!UICONTROL 手動（預設）]**：指定您希望在各體驗上看見的加入者百分比。 您可以在所有體驗之間分割百分比，或對每個體驗指定較高或較低的百分比。所有體驗的總計必須等於 100%。

   * **[!UICONTROL 自動分配至最佳體驗]**: 系統會自動將多數活動加入者導向表現較佳的體驗。有些訪客會被分配至所有體驗，以保持能夠利用體驗並且可識別效能趨勢中的變更。如需詳細資訊，請參閱 [[!UICONTROL 自動分配] 概述](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4).

   * **[!UICONTROL 針對個人化體驗自動鎖定目標]**： [!DNL Target] 使用進階機器學習來個人化內容，並透過識別多個高效能、行銷人員定義的體驗，然後根據訪客的個別客戶設定檔與類似訪客先前的行為，提供訪客量身打造的最佳體驗，藉此促進轉換。 如需詳細資訊，請參閱 [自動鎖定目標總覽](/help/main/c-activities/auto-target/auto-target-to-optimize.md).

   您也可以按一下 **[!UICONTROL 新增]** 以新增其他體驗至活動。

1. 當您滿意您的對象、體驗選擇和流量分配選擇時，請按一下 **[!UICONTROL 下一個]** 移至三步驟引導式工作流程的第三個步驟。

1. 指定活動的[目標與設定](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md)。

1. 按一下 **[!UICONTROL 儲存並關閉]** 或 **[!UICONTROL 儲存]**.

建立活動後， [!UICONTROL 概觀] 標籤會顯示活動的相關資訊，包括活動的圖表。

## 訓練影片：建立A/B測試(8:36) ![教學課程徽章](/help/main/assets/tutorial.png)

此影片示範如何使用 [!DNL Target] 三個步驟引導工作流程來建立 A/B 測試。

* 建立 [!UICONTROL A/B測試] 中的活動 [!DNL Adobe Target]
* 使用手動分割或自動流量分配來分配流量

>[!VIDEO](https://video.tv.adobe.com/v/17391)
