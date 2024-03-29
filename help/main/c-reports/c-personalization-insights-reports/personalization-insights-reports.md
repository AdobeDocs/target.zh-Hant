---
keywords: 鎖定目標;AP 報表;自動個人化報表;自動鎖定目標;自動鎖定目標報表;個人化;前瞻分析;自動化區段;faq;常見問題集;重要屬性
description: 瞭解如何針對Automated Personalization (AP)和自動鎖定目標(AT)活動使用專用報表 — 自動化區段和重要屬性。
title: 如何使用個人化前瞻分析報表？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Reports
exl-id: 89295d95-f179-4277-ae63-453350e1bba8
source-git-commit: 07062b7df75300bd7558a24da5121df454520e42
workflow-type: tm+mt
source-wordcount: '908'
ht-degree: 52%

---

# 個人化前瞻分析報表

[!UICONTROL 自動個人化] (AP) 和自動鎖定目標 (AT) 活動使用者可用的兩種專用報表: [!UICONTROL 「自動化區段」]與「重要屬性」報表。

>[!NOTE]
>
>使用「個人化前瞻分析」報表時，請考量下列事項：
>
>* AP 和 AT 活動是 [!DNL Target Premium] 解決方案內建的功能。若沒有 [!DNL Target Standard] 授權，[!DNL Target Premium] 便未隨附這些解決方案。
>
>* [!UICONTROL 「個人化前瞻分析」報表僅適用於使用轉換最佳化目標的 AP 與 AT 活動。]也不支援最佳化目標在活動上線後已從收入變更為轉換的活動。
>
>* [!UICONTROL Personalization Insights] 報表僅適用於 [!UICONTROL 主要目標] 是從 [!UICONTROL 報表量度] 下拉式清單。
>
>* 「個人化前瞻分析」報表僅支援於[預設環境](/help/main/administrating-target/hosts.md)中使用。
>
>* [!UICONTROL Personalization Insights] 報表只會針對以下專案中的活動產生： [!UICONTROL 即時] 狀態和已啟動且接收流量至少15天。


## 「個人化前瞻分析」報表概覽  {#section_B47CD4A50FEB43D587F9FACD9FFD6D9D}

[!UICONTROL 「個人化前瞻分析」]報表的目標是提供有關 AP 和 AT 活動背後的 Target 個人化模型如何個人化訪客流量的更多資訊。此 [隨機森林演演算法](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) 是 [!DNL Target] 個人化模型。

因為 [!UICONTROL Personalization Insights] 報表是用來瞭解 [!DNL Target] 個人化模型決定向哪些訪客傳送哪些內容， [!UICONTROL Personalization Insights] 報表只會反映AP或AT活動提供之所有流量的子區段。 具體而言，這兩份報表反映了使用個人化模型的所有流量。換句話說，[!UICONTROL 「個人化前瞻分析」]報表不會將整體成功案例模型提供的控制流量或流量納入考量。

二 [!UICONTROL Personalization Insights] 報表可供使用：

| 報表 | 詳細資料 |
|--- |--- |
| [!UICONTROL 自動化區段] | 不同訪客對您的 AP/AT 活動中的選件/體驗有不同的反應。此報表顯示不同自動化區段定義的方式。 [!DNL Target] 個人化模型已回應活動中的選件/體驗。 |
| [!UICONTROL 重要屬性] | 在不同的活動中，不同屬性對於模型決定個人化的方式或多或少都有不同的重要性。此報表顯示影響模型及其相對重要性的常見屬性。 |

## 解譯「個人化前瞻分析」中的屬性 {#section_B5C45E723EC941BDA2A7A642EEB30E4D}

在 AP 或「自動鎖定目標」模型中使用的[!UICONTROL 「個人化前瞻分析」]報表中有兩種屬性:

* **自動收集的屬性:**[!DNL Target] Target 使用基礎資料集在 AP 和 AT 活動中建立反映在「個人化前瞻分析」中的個人化演算法。請參閱 [Target 個人化演算法的資料收集](/help/main/c-activities/t-automated-personalization/ap-data.md)，以瞭解資料類型、範例屬性，及其其[!UICONTROL 個人化前瞻分析]命名慣例。請注意，雖然考量到這些屬性，但個別活動的模型可能不會在最終模型中使用所有這些屬性。
* **傳遞至 Target 的屬性:**&#x200B;請參閱[上傳用於 Target 個人化演算法的資料](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md)。

[!DNL Target] 提供許多方法，可以將其他資料傳遞給 ，使得用於在 AP 和 AT 活動中建立其個人化演算法的基礎資料集更豐富:[!DNL Target]

| 資料類型 | 說明 | 資料類型命名慣例 |
|--- |--- |--- |
| 設定檔屬性，包括設定檔指令碼、設定檔更新 API，以及頁面設定檔屬性 | 您決定包括在 Target 使用者設定檔的任何資訊。<br>此資訊可能來自設定檔指令碼、使用設定檔更新 API 上傳的資訊，或字首為 &quot;profile&quot; 的 mbox 內部設定檔參數。 | `Custom - Profile - [parameter name]` |
| 頁面引數（也稱為「mbox引數」） | 直接透過頁面代碼傳遞的名稱/值對，這些頁面代碼未儲存在訪客的設定檔中，以供未來使用。 | `Custom - Mbox Parameter - [parameter name]` |
| 客戶屬性 | 客戶屬性可讓您透過 FTP 將訪客設定檔資料上傳至 Experience Cloud。上傳後，即可在 Adobe Analytics 和 Adobe Target 中運用這些資料。 | `Custom - Customer Attributes - [parameter name]` |
| 共用對象 (Adobe Audience Manager 或 Adobe Analytics) | 透過 Adobe Audience Manager 或 Adobe Analytics 建立並與 Target 共用的對象。 | `Custom - Experience Cloud Segment - [segment name]` |
| 共用受眾(Adobe Experience Platform/Real-time CDP) | 透過Adobe Experience Platform/Real-time CDP建立並透過Destinations與Target共用的對象。 | `Custom - Adobe Experience Platform Segment - [segment name]` |
| 共用屬性(Adobe Experience Platform/Real-time CDP) | 透過Adobe Experience Platform/Real-time CDP建立並透過目的地與Target共用的屬性。 此功能目前處於Beta版。 | `Custom - Adobe Experience Platform Attribute - [attribute name]]` |
| 活動內報表對象/區段 | 在「目標與量度」中設定期間，在AP或自動鎖定目標活動中定義的對象。 | `Custom - Reporting Segment - [segment name]` |

## 常見問題集

以下專案的常見問題集清單： [!UICONTROL Automated Personalization] (AP)和 [!UICONTROL 自動鎖定目標] [!UICONTROL 深入分析] 報表。

### [!UICONTROL Automated Personalization] (AP) 和[!UICONTROL 自動鎖定目標]模型的資料會保留多長時間？

[!UICONTROL Automated Personalization] (AP)和 [!UICONTROL 自動鎖定目標] 模型會根據活動過去45天的使用者行為（使用者設定檔、曝光事件和轉換事件）進行訓練。

[!UICONTROL Automated Personalization] (AP)和 [!UICONTROL 自動鎖定目標] 模型會保留使用者行為、訓練記錄，以及模型決策資料90天以產生 [!UICONTROL 深入分析] 報表。 90天後，會捨棄訓練記錄和模型決策。 [!UICONTROL Automated Personalization] (AP)和 [!UICONTROL 自動鎖定目標] 模型也會將彙總的體驗/選件層級的曝光次數和轉換資料保留兩年，以用於報表用途。 此資料僅是彙總層級的資料，不包含任何個別層級的設定檔資料。

## 訓練影片：使用個人化前瞻分析報表 ![教學課程徽章](/help/main/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/25601/)

如需詳細資訊，請參閱 [在Adobe Target中使用個人化前瞻分析報表](https://helpx.adobe.com/target/kt/using/personalization-insights-report-feature-video-use.html).

## Adobe部落格

* 第1部分： [揭開AI驅動個人化的神秘面紗](https://theblog.adobe.com/taking-mystery-magic-ai-driven-personalization-part-1/)
* 第2部分： [在Adobe Target中透過AI實現個人化](https://theblog.adobe.com/a-peek-behind-the-curtain-of-ai-for-personalization-in-adobe-target/)
* 第3部分： [MAGIX — AI驅動的個人化黑匣子問題的解決方案](https://theblog.adobe.com/magix-the-solution-to-the-black-box-issue-of-ai-driven-personalization/)
