---
keywords: 鎖定目標;AP 報表;自動個人化報表;自動鎖定目標;自動鎖定目標報表;個人化;前瞻分析;自動化區段;faq;常見問題集;重要屬性
description: 瞭解如何針對Automated Personalization (AP)和自動鎖定目標(AT)活動使用專用報表 — 自動化區段和重要屬性。
title: 如何使用Personalization前瞻分析報表？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=zh-Hant#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Reports
exl-id: 89295d95-f179-4277-ae63-453350e1bba8
source-git-commit: 6c8f042acb257fc908349c679bf745e477f94af4
workflow-type: tm+mt
source-wordcount: '877'
ht-degree: 28%

---

# [!UICONTROL Personalization Insights]個報告

[!UICONTROL Automated Personalization] (AP)和[!UICONTROL Auto-Target] (AT)活動的使用者可以使用兩個專用報告： [!UICONTROL Automated Segments]和[!UICONTROL Important Attributes]報告。

## 考量事項

使用[!UICONTROL Personalization Insights]報表時，請考量下列事項：

* AP和AT活動是[[!DNL Target Premium] 解決方案](/help/main/c-intro/intro.md#premium)的一部分。 若沒有 [!DNL Target Standard] 授權，[!DNL Target Premium] 便未隨附這些解決方案。

* [!UICONTROL Personalization Insights]報告僅適用於設定如下AP和AT活動：

   * [!DNL Target]報告> [!UICONTROL Conversion]

     例如：

     ![目標報告>轉換](/help/main/c-reports/assets/conversion.png)

   * [!DNL Analytics]報告> [!DNL Conversion]

     例如：

     ![Analytic Reporting >轉換](/help/main/c-reports/assets/analytics-reporting-conversion.png)

   * [!DNL Analytics]報告> [!UICONTROL Use an Analytics metric] > [!UICONTROL Maximize Visit Conversion Rate]

     例如：

     ![使用Analytics量度>最大化造訪轉換率](/help/main/c-reports/assets/maximize-visit-conversion-rate.png)

* 也不支援最佳化目標在活動上線後已從收入變更為轉換的活動。

* 必須從[!UICONTROL Personalization Insights]下拉式清單中選取[!UICONTROL Primary Goal]，才能使用[!UICONTROL Report Metric]報告。

* 僅[!UICONTROL Personalization Insights]預設環境[支援](/help/main/administrating-target/hosts.md)報告。

* [!UICONTROL Personalization Insights]報告只會針對處於[!UICONTROL Live]狀態且已啟用且接收流量至少15天的活動產生。

## Personalization前瞻分析報表概覽 {#section_B47CD4A50FEB43D587F9FACD9FFD6D9D}

[!UICONTROL Personalization Insights]報表的目標是提供有關AP和AT活動背後的[!UICONTROL Target]個人化模型如何個人化訪客流量的詳細資訊。 [隨機森林演演算法](/help/main/c-activities/t-automated-personalization/algo-random-forest.md)是[!DNL Target]個人化模型的基礎。

由於[!UICONTROL Personalization Insights]報表的目標是瞭解[!DNL Target]個人化模型如何決定向哪些訪客傳送哪些內容，因此[!UICONTROL Personalization Insights]報表僅反映AP或AT活動提供服務之所有流量的子區段。 具體而言，這兩份報表反映了使用個人化模型的所有流量。換句話說，[!UICONTROL Personalization Insights]報表不會將整體成功案例模型提供的控制流量或流量納入考量。

有兩份[!UICONTROL Personalization Insights]報告可供使用：

| 報表 | 詳細資料 |
|--- |--- |
| [!UICONTROL Automated Segments] | 不同訪客對您的 AP/AT 活動中的產品建議/體驗有不同的反應。此報表顯示[!DNL Target]個人化模型定義的不同自動化區段如何回應活動中的選件/體驗。 |
| [!UICONTROL Important Attributes] | 在不同的活動中，不同屬性對於模型決定個人化的方式或多或少都有不同的重要性。此報表顯示影響模型及其相對重要性的常見屬性。 |

## 解譯Personalization Insights中的屬性 {#section_B5C45E723EC941BDA2A7A642EEB30E4D}

在[!UICONTROL Personalization Insights]個報表中，有兩個型別的屬性用於您的AP或自動鎖定目標模型：

* Target自動收集的&#x200B;**屬性：** [!DNL Target]使用基底資料集，在Personalization Insights中反映的AP和AT活動中建置其個人化演演算法。 如需資料型別、範例屬性及其[命名慣例，請參閱](/help/main/c-activities/t-automated-personalization/ap-data.md)Target Personalization演演算法的資料收集[!UICONTROL Personalization Insights]。 請注意，雖然考量到這些屬性，但個別活動模型可能不會在最終模型中使用所有這些屬性。
* **傳遞至Target的屬性：**&#x200B;請參閱[上傳Target Personalization演演算法的資料](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md)。

[!DNL Target]提供許多方式，讓您傳入[!DNL Target]的其他資料，以擴充在AP和AT活動中建置其個人化演演算法時所用的基底資料集：

| 資料類型 | 說明 | 資料類型命名慣例 |
|--- |--- |--- |
| 設定檔屬性，包括設定檔指令碼、設定檔更新 API，以及頁面設定檔屬性 | 您決定包括在 Target 使用者輪廓的任何資訊。<br>此資訊可能來自設定檔指令碼、使用設定檔更新 API 上傳的資訊，或字首為 &quot;profile&quot; 的 mbox 內部設定檔參數。 | `Custom - Profile - [parameter name]` |
| 頁面引數（又稱為「mbox引數」） | 直接透過頁面代碼傳遞的名稱/值對，這些頁面代碼未儲存在訪客的設定檔中，以供未來使用。 | `Custom - Mbox Parameter - [parameter name]` |
| 客戶屬性 | 客戶屬性可讓您透過 FTP 將訪客設定檔資料上傳至 Experience Cloud。上傳後，即可在 Adobe Analytics 和 Adobe Target 中運用這些資料。 | `Custom - Customer Attributes - [parameter name]` |
| 共用對象 (Adobe Audience Manager 或 Adobe Analytics) | 透過 Adobe Audience Manager 或 Adobe Analytics 建立並與 Target 共用的對象。 | `Custom - Experience Cloud Segment - [segment name]` |
| 共用受眾(Adobe Experience Platform/Real-time CDP) | 透過Adobe Experience Platform/Real-time CDP建立對象，並透過目的地與Target共用。 | `Custom - Adobe Experience Platform Segment - [segment name]` |
| 共用屬性(Adobe Experience Platform/Real-time CDP) | 透過Adobe Experience Platform/Real-time CDP建立並透過目標與Target共用的屬性。 此功能目前在Beta中。 | `Custom - Adobe Experience Platform Attribute - [attribute name]]` |
| 活動內報表對象/區段 | 在「目標與量度」中設定期間，在您的AP或自動鎖定目標活動中定義的對象。 | `Custom - Reporting Segment - [segment name]` |

## 常見問題集

有關[!UICONTROL Automated Personalization] (AP)和[!UICONTROL Auto-Target] [!UICONTROL Insights]報告的常見問題集清單。

### [!UICONTROL Automated Personalization] (AP)和[!UICONTROL Auto-Target]模型的資料會保留多長時間？

[!UICONTROL Automated Personalization] (AP)和[!UICONTROL Auto-Target]模型已針對活動過去45天的使用者行為（使用者設定檔、曝光事件和轉換事件）進行訓練。

[!UICONTROL Automated Personalization] (AP)和[!UICONTROL Auto-Target]模型會保留使用者行為、訓練記錄和模型決定資料90天，以產生[!UICONTROL Insights]個報告。 90天後，會捨棄訓練記錄和模型決策。 [!UICONTROL Automated Personalization] (AP)和[!UICONTROL Auto-Target]模型也會保留彙總的體驗/選件層級的曝光次數和轉換資料兩年，以用於報表用途。 此資料僅是彙總層級的資料，不包含任何個別層級的設定檔資料。

## 訓練影片：使用Personalization Insights報表![教學課程徽章](/help/main/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/25601/)

如需詳細資訊，請參閱[在Adobe Target中使用Personalization前瞻分析報表](https://helpx.adobe.com/target/kt/using/personalization-insights-report-feature-video-use.html)。

## Adobe部落格

* 第1部分：[揭開AI驅動Personalization的神秘面紗](https://theblog.adobe.com/taking-mystery-magic-ai-driven-personalization-part-1/)
* 第2部分：[在Adobe Target中Personalization的AI幕後窺視](https://theblog.adobe.com/a-peek-behind-the-curtain-of-ai-for-personalization-in-adobe-target/)
* 第3部分： [MAGIX — AI導向Personalization的黑匣子問題的解決方案](https://theblog.adobe.com/magix-the-solution-to-the-black-box-issue-of-ai-driven-personalization/)
