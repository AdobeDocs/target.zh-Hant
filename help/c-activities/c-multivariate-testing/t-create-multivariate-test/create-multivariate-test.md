---
keywords: MVT; 多變數測試; 多變數測試建立; 多變數測試建立; MVT 建立; MVT 建立; MVT 如何; 多變數測試如何
description: 瞭解如何使用Adobe Target的視覺體驗撰寫器(VEC)，直接在Target啟用的頁面上建立多變數測試(MVT)。
title: 如何建立多變數測試？
feature: 多變數測試
translation-type: tm+mt
source-git-commit: e87786f2df104d66d97cacd83921875dacd78afe
workflow-type: tm+mt
source-wordcount: '569'
ht-degree: 87%

---


# 建立多變數測試{#create-a-multivariate-test}

[!DNL Adobe Target] 中的[!UICONTROL 可視化體驗撰寫器] (VEC) 讓您直接在啟用 Target 的頁面上輕鬆建立您的測試，以及在 [!DNL Target] 內修改頁面的部分。

[!DNL Target]點按編輯器可讓您選擇任何位置並新增多個選件。

[!UICONTROL 多變數測試] (MVT) 需要頁面優先的報表。換句話說，測試會在具有您為頁面所設計體驗的特定 URL 上執行。

1. 按一下&#x200B;**[!UICONTROL 「建立活動」]**>**[!UICONTROL 「多變數測試」]**。

   ![建立多變數測試](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/create-multivariate.png)

   >[!NOTE]
   >
   >可用的活動類型取決於您的 Target 帳戶。有些活動類型可能不會出現在您的清單中。例如，[!UICONTROL Automated Personalization] 是 [Target Premium 功能](/help/c-intro/intro.md#premium)。
   >
   >如需有關 [!DNL Target] 提供的各種活動類型及其差異的詳細資訊，請參閱[活動](/help/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)。請參閱[Target 活動類型](/help/c-activities/target-activities-guide.md)，協助您決定哪種活動類型最適合您的需求。

1. 視需要選取&#x200B;**[!UICONTROL 視覺 (預設)]**。

   ![建立多變數測試活動對話方塊](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/create-mvt-dialog.png)

   >[!NOTE]
   >
   >如遇問題，需要關於 VEC 的疑難排解資訊，請參閱[疑難排解可視化體驗撰寫器](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)。
   >
   >上圖中的[!UICONTROL 選擇工作區]選項是 [Target Premium](/help/c-intro/intro.md) 功能。如果您沒有看到此選項，表示您的組織擁有的是 Target Standard 授權。

1. (視條件而定) 如果您是 Target Premium 客戶，請[選擇工作區](/help/administrating-target/c-user-management/property-channel/property-channel.md)。

1. 為您要測試的頁面[指定 URL](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/url.md#concept_C12E4A85FF3B4E518E3110F6CF1AF9C0)，然後按一下&#x200B;**[!UICONTROL 下一步]**。

   >[!NOTE]
   >
   >使用完整的 URL，開頭要包括 HTTP 或 HTTPS。

   如果出現訊息，要求您啟用您的瀏覽器使用混合的內容，請遵循訊息中的說明。為您的瀏覽器啟用混合的內容之後，請從步驟 1 重新開始。

   可視化體驗撰寫器隨即開啟。

1. 輸入活動的名稱。

   ![活動名稱欄位](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/activityname.png)

   活動名稱不能以下列任何字元開頭：

   | 字元 | 說明 |
   |--- |--- |
   | `=` | 等號 |
   | `+` | 加號 |
   | `-` | 減號 |
   | `@` | 「@」符號 |

1. [在每個位置中建立選件](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/add-offers.md#concept_DCE6B45C30F7419B8EC17AFDEE8D8AA6)。

   ![編輯文字/HTML 對話方塊](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/editoffers.png)

   您可以新增下列類型的選件:

   * HTML
   * 影像
   * 文字

1. 按一下&#x200B;**[!UICONTROL 預覽]**&#x200B;以[預覽您的體驗](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/preview-experiences.md)。

   ![預覽體驗](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/preview-mvt.png)

   您可以檢視每個體驗，以及排除不想在您的測試中包括的任何體驗。若要排除一或多個體驗，請選取所需的核取方塊，然後按一下&#x200B;**[!UICONTROL 排除]**。

   ![排除體驗](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/preview-mvt-exclude.png)

1. [使用流量估算程式](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714)來測試您的測試計劃的可行性。

   ![流量指標](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt-traffic-indicator.png)

   下圖顯示活動有充足的流量。

   ![](assets/estimator.png)

   下圖顯示活動有充足的流量。

   ![](assets/estimator2.png)

1. 按一下&#x200B;**[!UICONTROL Next]**&#x200B;進入[!UICONTROL Targeting]頁面。

1. 選擇對象和符合您要讓其進入活動之訪客的百分比。

   ![MVT 活動中的鎖定目標頁面](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt_audperc.png)

   例如，您可將項目限制為所有訪客的 50%，或「加州人」觀眾的 45%。

   >[!NOTE]
   >
   >除了選取現有對象，您可以結合多個對象來建立隨選結合的對象而非建立新對象。如需詳細資訊，請參閱[合併多個對象](/help/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)。

1. [檢閱測試摘要](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/test-summary.md#reference_971AB225963A4DC18EEB5B0E20F0A4A7)，並進行任何需要的變更，然後按一下&#x200B;**[!UICONTROL 下一步]**。

1. [指定測試的目標與設定](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)。

1. 按一下&#x200B;**[!UICONTROL 「儲存並關閉」]**&#x200B;來建立活動。

## 訓練影片：建立多變數測試(9:25)![教學課程標章](/help/assets/tutorial.png)

此影片示範如何使用 Target 三步驟引導式工作流程來規劃和建立多變數測試。

* 定義和設計多變數測試
* 建立多變數測試

>[!VIDEO](https://video.tv.adobe.com/v/17395)
