---
description: Target中的Visual Experience Composer可讓您輕鬆地在啓用Target的頁面上建立多變數測試(MVT)，並修改Target中的部分頁面。
keywords: MVT; 多變數測試; 多變數測試建立; 多變數測試建立; MVT 建立; MVT 建立; MVT 如何; 多變數測試如何
seo-description: Adobe Target中的Visual Experience Composer(CMS)可讓您輕鬆在啓用Target的頁面上建立多變數測試(MVT)，並修改Target中的部分頁面。
seo-title: 建立多變數測試
solution: Target
title: 建立多變數測試
uuid: 876441bd-d841-4974-b1ec-3ad7cb6ef3ee
translation-type: tm+mt
source-git-commit: 5dd87afce38e7ff9c763aa65031ec837689d4ae8

---


# 建立多變數測試{#create-a-multivariate-test}

[!UICONTROL Visual Experience Composer] (CMS)可 [!DNL Target] 讓您輕鬆在啓用Target的頁面上建立測試，並修改內頁部分 [!DNL Target]。

Target 指向和點按編輯程式可讓您挑選任何位置並新增多個選件。

[!UICONTROL 多變數測試] (MVT)會採用第一個頁面報表。換句話說，測試會在具有您為頁面所設計體驗的特定 URL 上執行。

1. 按一下 **[!UICONTROL 「建立活動]** &gt; **[!UICONTROL 多變數測試」]**。

   ![建立多變數測試](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/create-multivariate.png)

   >[!NOTE]
   >
   >可用的活動類型取決於您的 Target 帳戶。有些活動類型可能不會出現在您的清單中。For example, [!UICONTROL Automated Personalization] is a [Target Premium feature](/help/c-intro/intro.md#premium).
   >
   >For more information about the various activity types available in [!DNL Target] and their differences, see [Activities](../../../c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03). See [Target Activity types](/help/c-activities/target-activities-guide.md) to help you decide which activity type best suites your needs.

1. Select **[!UICONTROL Visual (Default)]**, if necessary.

   ![建立多變數測試活動對話方塊](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/create-mvt-dialog.png)

   >[!NOTE]
   >
   >如遇問題，需要關於 VEC 的疑難排解資訊，請參閱[疑難排解可視化體驗撰寫器](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)。
   >
   >The [!UICONTROL Choose Workplace] option in the preceding illustration is a [Target Premium](/help/c-intro/intro.md) feature. 如果您未看見此選項，則您的組織有Target Standard授權。]

1. (Conditional) If you are a Target Premium customer, [choose a workspace](/help/administrating-target/c-user-management/property-channel/property-channel.md).

1. [指定您要測試之頁面的URL](../../../c-activities/c-multivariate-testing/t-create-multivariate-test/url.md#concept_C12E4A85FF3B4E518E3110F6CF1AF9C0) ，然後按一下 **[!UICONTROL 「下一步」]**。

   >[!NOTE]
   >
   >使用完整的 URL，開頭要包括 HTTP 或 HTTPS。

   如果出現訊息，要求您啟用您的瀏覽器使用混合的內容，請遵循訊息中的說明。為您的瀏覽器啟用混合的內容之後，請從步驟 1 重新開始。

   可視化體驗撰寫器隨即開啟。

1. 輸入活動的名稱。

   ![活動名稱欄位](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/activityname.png)

   活動名稱中不允許下列字元:

   | 字元 | 說明 |
   |--- |--- |
   | / | 正斜線 |
   | ? | 問號 |
   | # | 數字符號 |
   | : | 冒號 |
   | = | 等號 |
   | + | 加號 |
   | - | 減號 |
   | @ | 「@」符號 |

1. [在每個位置中建立選件](../../../c-activities/c-multivariate-testing/t-create-multivariate-test/add-offers.md#concept_DCE6B45C30F7419B8EC17AFDEE8D8AA6)。

   ![「編輯文字/HTML」對話框](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/editoffers.png)

   您可以新增下列類型的選件:

   * HTML
   * 影像
   * 文字

1. Click **[!UICONTROL Preview]** to [preview your experiences](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/preview-experiences.md).

   ![預覽體驗](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/preview-mvt.png)

   您可以檢視每個體驗，以及排除不想在您的測試中包括的任何體驗。To exclude one or more experiences, select the desired checkboxes, then click **[!UICONTROL Exclude]** .

   ![排除體驗](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/preview-mvt-exclude.png)

1. [使用流量估算程式](../../../c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714)來測試您的測試計劃的可行性。

   ![流量指標](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt-traffic-indicator.png)

   下圖指出活動的流量不足。

   ![](assets/estimator.png)

   下圖指出活動的流量不足。

   ![](assets/estimator2.png)

1. Click **[!UICONTROL Next]** to advance to the [!UICONTROL Targeting] page.]

1. 選擇對象和符合您要讓其進入活動之訪客的百分比。

   ![MVT活動中的定位頁面](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt_audperc.png)

   例如，您可將項目限制為所有訪客的 50%，或「加州人」觀眾的 45%。

   >[!NOTE]
   >
   >除了選取現有對象，您可以結合多個對象來建立隨選結合的對象而非建立新對象。如需詳細資訊，請參閱[合併多個對象](../../../c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)。

1. [檢閱測試摘要](../../../c-activities/c-multivariate-testing/t-create-multivariate-test/test-summary.md#reference_971AB225963A4DC18EEB5B0E20F0A4A7) 並進行任何所需變更，然後按一下「下一 **[!UICONTROL 步」]**。

1. [指定測試的目標與設定](../../../c-activities/c-multivariate-testing/t-create-multivariate-test/goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)。

1. 按一下 **[!UICONTROL 「儲存並關閉」]** 來建立活動。

## 訓練影片: 建立多變數測試 (9:25)

此影片示範如何使用 Target 三步驟引導式工作流程來規劃和建立多變數測試。

* 定義和設計多變數測試
* 建立多變數測試

>[!VIDEO](https://video.tv.adobe.com/v/17395?captions=chi_hant)
