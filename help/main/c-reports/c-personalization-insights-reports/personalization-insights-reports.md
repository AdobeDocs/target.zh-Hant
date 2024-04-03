---
keywords: 鎖定目標;AP 報表;自動個人化報表;自動鎖定目標;自動鎖定目標報表;個人化;前瞻分析;自動化區段;faq;常見問題集;重要屬性
description: 瞭解如何針對Automated Personalization (AP)和自動鎖定目標(AT)活動使用專用報表 — 自動化區段和重要屬性。
title: 如何使用個人化前瞻分析報表？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Reports
exl-id: 89295d95-f179-4277-ae63-453350e1bba8
source-git-commit: 6c8f042acb257fc908349c679bf745e477f94af4
workflow-type: tm+mt
source-wordcount: '877'
ht-degree: 28%

---

# [!UICONTROL Personalization Insights] 報表

兩個專用報表可供以下使用者使用： [!UICONTROL Automated Personalization] (AP)和 [!UICONTROL Auto-Target] (AT)活動： [!UICONTROL Automated Segments] 和 [!UICONTROL Important Attributes] 報表。

## 考量事項

使用時，請考慮下列事項 [!UICONTROL Personalization Insights] 報表：

* AP和AT活動是 [[!DNL Target Premium] 解決方案](/help/main/c-intro/intro.md#premium). 若沒有 [!DNL Target Standard] 授權，[!DNL Target Premium] 便未隨附這些解決方案。

* [!UICONTROL Personalization Insights] 報表僅適用於設定如下AP和AT活動：

   * [!DNL Target] 報告> [!UICONTROL Conversion]

     例如：

     ![Target報表>轉換](/help/main/c-reports/assets/conversion.png)

   * [!DNL Analytics] 報告> [!DNL Conversion]

     例如：

     ![Analytic Reporting >轉換](/help/main/c-reports/assets/analytics-reporting-conversion.png)

   * [!DNL Analytics] 報告> [!UICONTROL Use an Analytics metric] > [!UICONTROL Maximize Visit Conversion Rate]

     例如：

     ![使用Analytics量度>最大化造訪轉換率](/help/main/c-reports/assets/maximize-visit-conversion-rate.png)

* 也不支援最佳化目標在活動上線後已從收入變更為轉換的活動。

* [!UICONTROL Personalization Insights] 報告僅限在 [!UICONTROL Primary Goal] 是從 [!UICONTROL Report Metric] 下拉式清單。

* [!UICONTROL Personalization Insights] 報告支援 [預設環境](/help/main/administrating-target/hosts.md) 僅限。

* [!UICONTROL Personalization Insights] 系統只會針對下列位置中的活動產生報表： [!UICONTROL Live] 狀態和已啟動且接收流量至少15天。

## 個人化前瞻分析報表概覽 {#section_B47CD4A50FEB43D587F9FACD9FFD6D9D}

的目標 [!UICONTROL Personalization Insights] 報表是提供詳細資訊，說明如何 [!UICONTROL Target] AP和AT活動背後的個人化模型可將訪客流量個人化。 此 [隨機森林演演算法](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) 是 [!DNL Target] 個人化模型。

因為 [!UICONTROL Personalization Insights] 報表是用來瞭解 [!DNL Target] 個人化模型決定向哪些訪客傳送哪些內容， [!UICONTROL Personalization Insights] 報表只會反映AP或AT活動提供之所有流量的子區段。 具體而言，這兩份報表反映了使用個人化模型的所有流量。換句話說， [!UICONTROL Personalization Insights] 報表不會將整體成功案例模型提供的控制流量或流量納入考量。

兩個 [!UICONTROL Personalization Insights] 報表可供使用：

| 報表 | 詳細資料 |
|--- |--- |
| [!UICONTROL Automated Segments] | 不同訪客對您的 AP/AT 活動中的選件/體驗有不同的反應。此報表顯示使用者定義之不同自動化區段 [!DNL Target] 個人化模型會回應活動中的選件/體驗。 |
| [!UICONTROL Important Attributes] | 在不同的活動中，不同屬性對於模型決定個人化的方式或多或少都有不同的重要性。此報表顯示影響模型及其相對重要性的常見屬性。 |

## 解譯「個人化前瞻分析」中的屬性 {#section_B5C45E723EC941BDA2A7A642EEB30E4D}

有兩種型別的屬性在 [!UICONTROL Personalization Insights] 在您的AP或自動鎖定目標模型中使用的報表：

* **Target自動收集的屬性：** [!DNL Target] 使用基本資料集在AP和AT活動中建置其個人化演演算法，並反映在個人化前瞻分析中。 另請參閱 [Target個人化演演算法的資料收集](/help/main/c-activities/t-automated-personalization/ap-data.md) 針對資料型別，範例屬性及其 [!UICONTROL Personalization Insights] 命名慣例。 請注意，雖然考量到這些屬性，但個別活動模型可能不會在最終模型中使用所有這些屬性。
* **傳遞至Target的屬性：** 另請參閱 [上傳用於Target個人化演演算法的資料](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md).

[!DNL Target] 提供多種將其他資料傳遞至的方法 [!DNL Target] 若要豐富在AP和AT活動中建置其個人化演演算法所用的基本資料集：

| 資料類型 | 說明 | 資料類型命名慣例 |
|--- |--- |--- |
| 設定檔屬性，包括設定檔指令碼、設定檔更新 API，以及頁面設定檔屬性 | 您決定包括在 Target 使用者設定檔的任何資訊。<br>此資訊可能來自設定檔指令碼、使用設定檔更新 API 上傳的資訊，或字首為 &quot;profile&quot; 的 mbox 內部設定檔參數。 | `Custom - Profile - [parameter name]` |
| 頁面引數（又稱為「mbox引數」） | 直接透過頁面代碼傳遞的名稱/值對，這些頁面代碼未儲存在訪客的設定檔中，以供未來使用。 | `Custom - Mbox Parameter - [parameter name]` |
| 客戶屬性 | 客戶屬性可讓您透過 FTP 將訪客設定檔資料上傳至 Experience Cloud。上傳後，即可在 Adobe Analytics 和 Adobe Target 中運用這些資料。 | `Custom - Customer Attributes - [parameter name]` |
| 共用對象 (Adobe Audience Manager 或 Adobe Analytics) | 透過 Adobe Audience Manager 或 Adobe Analytics 建立並與 Target 共用的對象。 | `Custom - Experience Cloud Segment - [segment name]` |
| 共用受眾(Adobe Experience Platform/Real-time CDP) | 透過Adobe Experience Platform/Real-time CDP建立對象，並透過目的地與Target共用。 | `Custom - Adobe Experience Platform Segment - [segment name]` |
| 共用屬性(Adobe Experience Platform/Real-time CDP) | 透過Adobe Experience Platform/Real-time CDP建立並透過目標與Target共用的屬性。 此功能目前在Beta版中提供。 | `Custom - Adobe Experience Platform Attribute - [attribute name]]` |
| 活動內報表對象/區段 | 在「目標與量度」中設定期間，在您的AP或自動鎖定目標活動中定義的對象。 | `Custom - Reporting Segment - [segment name]` |

## 常見問題集

常見問題集清單 [!UICONTROL Automated Personalization] (AP)和 [!UICONTROL Auto-Target] [!UICONTROL Insights] 報表。

### 資料持續多長時間 [!UICONTROL Automated Personalization] (AP)和 [!UICONTROL Auto-Target] 模型是否持續存在？

[!UICONTROL Automated Personalization] (AP)和 [!UICONTROL Auto-Target] 模型會根據活動過去45天的使用者行為（使用者設定檔、曝光事件和轉換事件）進行訓練。

[!UICONTROL Automated Personalization] (AP)和 [!UICONTROL Auto-Target] 模型會保留使用者行為、訓練記錄，以及模型決定資料90天以產生 [!UICONTROL Insights] 報表。 90天後，會捨棄訓練記錄和模型決策。 [!UICONTROL Automated Personalization] (AP)和 [!UICONTROL Auto-Target] 模型也會保留彙總的體驗/選件層級曝光和轉換資料兩年，以用於報表用途。 此資料僅是彙總層級的資料，不包含任何個別層級的設定檔資料。

## 訓練影片：使用個人化前瞻分析報表 ![教學課程徽章](/help/main/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/25601/)

如需詳細資訊，請參閱 [在Adobe Target中使用個人化前瞻分析報表](https://helpx.adobe.com/target/kt/using/personalization-insights-report-feature-video-use.html).

## Adobe部落格

* 第1部分： [揭開AI驅動個人化神秘的面紗](https://theblog.adobe.com/taking-mystery-magic-ai-driven-personalization-part-1/)
* 第2部分： [AI幕後窺視Adobe Target中的個人化](https://theblog.adobe.com/a-peek-behind-the-curtain-of-ai-for-personalization-in-adobe-target/)
* 第3部分： [MAGIX — AI驅動個人化黑匣子問題的解決方案](https://theblog.adobe.com/magix-the-solution-to-the-black-box-issue-of-ai-driven-personalization/)
