---
keywords: 建立自動鎖定目標； A/B測試；自動鎖定目標活動；新a/b活動；自動鎖定目標；針對個人化體驗自動鎖定目標；個人化；最佳化
description: 瞭解如何使用 [!UICONTROL 視覺化體驗撰寫器] (VEC)輸入 [!DNL Adobe Target] 以建立 [!UICONTROL 自動鎖定目標] A/B測試活動。
title: 如何建立 [!UICONTROL 自動鎖定目標] 活動？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Auto-Target
exl-id: 5521740c-eee2-4ba2-8931-cf56d56a4561
source-git-commit: 3e8c2d77f300bf0e2ca83a53d30e7b9eee48894e
workflow-type: tm+mt
source-wordcount: '874'
ht-degree: 48%

---

# 建立 [!UICONTROL 自動鎖定目標] 活動

使用 [!UICONTROL 視覺化體驗撰寫器] (VEC)輸入 [!DNL Adobe Target] 建立您的 [!UICONTROL 自動鎖定目標] [!UICONTROL A/B測試] 活動直接在 [!DNL Target] — 啟用頁面，並修改頁面部分於 [!DNL Target].

>[!NOTE]
>
>[!UICONTROL 自動鎖定目標]是 [!DNL Target Premium] 解決方案內建的功能。若無 [!DNL Target Standard] 授權，[!DNL Target Premium] 不提供此功能。如需此授權提供之進階功能的詳細資訊，請參閱 [Target Premium](/help/main/c-intro/intro.md)。

若要建立 [!UICONTROL 自動鎖定目標] 活動：

1. 從&#x200B;**[!UICONTROL 「活動」]**&#x200B;清單，按一下&#x200B;**[!UICONTROL 「建立活動」]**>**[!UICONTROL 「A/B 測試」]**。

   ![建立活動下拉式清單](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_select-new.png)

   可用的活動類型取決於您的 [!DNL Target] 帳戶。有些活動類型可能不會出現在您的清單中。例如，[!UICONTROL Recommendations] 是 [Target Premium 功能](/help/main/c-intro/intro.md#premium)。如需各種活動類型的相關資訊，請參閱[活動](/help/main/c-activities/activities.md)和 [Target 活動指南](/help/main/c-activities/target-activities-guide.md)。

1. 選取 **[!UICONTROL 視覺]**，如有必要。

   如果您偏好使用 [!UICONTROL 表單式體驗撰寫器]，選取 [!UICONTROL 表單]. 如需詳細資訊，請參閱[表單式體驗撰寫器](/help/main/c-experiences/form-experience-composer.md)。

   >[!NOTE]
   >
   >除了VEC和 [!UICONTROL 表單式體驗撰寫器]， [!DNL Target] 提供單頁應用程式VEC。 如需各種撰寫器的詳細資訊，請參閱[體驗和選件](/help/main/c-experiences/experiences.md)。
   >
   >如遇問題，需要關於 VEC 的疑難排解資訊，請參閱[疑難排解可視化體驗撰寫器](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)。

1. (視條件而定) 如果您是 [Target Premium 客戶](/help/main/c-intro/intro.md#premium)，請選擇[工作區](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)。

1. 指定[活動 URL](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md)，然後按一下&#x200B;**[!UICONTROL 下一步]**。

   如果您的帳戶設定了預設的 URL，該 URL 依預設會顯示。您可以將預設 URL 變更為其他 URL。

   [!UICONTROL 「可視化體驗撰寫器」]隨即開啟，顯示 URL 中指定的頁面。

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

   此 [!UICONTROL 視覺化體驗撰寫器] 建立活動後，會在左側顯示兩個標籤：體驗A和體驗B。體驗A是控制體驗。 您的焦點在體驗B索引標籤，您可以視需要修改它。 體驗B是可新增至測試的替代體驗。 您可以對測試新增多個體驗。如果您不想要包括預設網站體驗作為選項，則也可以從活動刪除體驗 A。

   如需在[!UICONTROL 可視化體驗撰寫器]中新增和修改體驗的相關資訊，請參閱[新增體驗](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md)。若要修改體驗 B，請從步驟 2 開始。

1. 按一下&#x200B;**[!UICONTROL 可視化體驗撰寫器]**&#x200B;頂端的[!UICONTROL 鎖定目標]，以前往三步驟引導工作流程中的下一個步驟。

   流程圖表隨即開啟。

   ![A/B 測試鎖定目標步驟](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new.png)

   流程圖表將引導您進行選擇活動對象和設定體驗的步驟。

1. 在 [!UICONTROL 對象] 方塊中，按一下編輯圖示（垂直的省略符號），然後按一下 **[!UICONTROL 取代對象]**，然後 [選取對象](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) （適用於您的活動）。

   依預設，對象會設為 [!UICONTROL 所有訪客].

1. 選擇符合您要讓其進入活動之訪客的百分比。

   ![受眾百分比](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/audperc-new.png)

   例如，您可將項目限制為所有訪客的 50%，或「加州人」觀眾的 45%。

1. 設定您的流量分配。

   您可以對相同對象顯示多個體驗。系統會顯示圖表，顯示您選取的對象以及您已新增至活動的體驗。

   選擇所需的流量分配方法. 若要建立 [!UICONTROL 自動鎖定目標] 活動，選取 **[!UICONTROL 針對個人化體驗自動鎖定目標]**.

   三種流量分配型別說明如下：

   * **[!UICONTROL 手動（預設）]**：指定您希望在各體驗上看見的加入者百分比。 您可以在所有體驗之間分割百分比，或對每個體驗指定較高或較低的百分比。所有體驗的總計必須等於 100%。如需詳細資訊，請參閱 [建立A/B測試](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md).

   * **[!UICONTROL 自動分配至最佳體驗]**：系統會自動將多數活動加入者導向表現較佳的體驗。 有些訪客會被分配至所有體驗，以保持能夠利用體驗並且可識別效能趨勢中的變更。如需詳細資訊，請參閱 [自動分配總覽](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md).

   * **[!UICONTROL 針對個人化體驗自動鎖定目標]**： [!DNL Target] 使用進階機器學習來個人化內容，並透過識別多個高效能、行銷人員定義的體驗，然後根據訪客的個別客戶設定檔與類似訪客先前的行為，提供訪客量身打造的最佳體驗，藉此促進轉換。

   您也可以按一下 **[!UICONTROL 新增]** 以新增其他體驗至活動。

1. 當您滿意您的對象、體驗選擇和流量分配選擇時，請按一下 **[!UICONTROL 下一個]** 移至三步驟引導式工作流程的第三個步驟。

1. 指定活動的[目標與設定](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md)。

   >[!NOTE]
   >
   >如果您想使用 [目標分析](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T)對於此活動，請參閱以下的重要資訊： [自動分配和自動鎖定目標活動的A4T支援](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md).

1. 按一下 **[!UICONTROL 儲存並關閉]** 或 **[!UICONTROL 儲存]**.

建立活動後， [!UICONTROL 概觀] 標籤會顯示活動的相關資訊，包括活動的圖表。

## 訓練影片: 建立 A/B 測試 (8:36)

此影片示範如何使用 [!DNL Target] 三個步驟引導工作流程來建立 A/B 測試。

* 建立 [!UICONTROL A/B測試] 中的活動 [!DNL Adobe Target]
* 使用手動分割或自動流量分配來分配流量

>[!VIDEO](https://video.tv.adobe.com/v/17391)
