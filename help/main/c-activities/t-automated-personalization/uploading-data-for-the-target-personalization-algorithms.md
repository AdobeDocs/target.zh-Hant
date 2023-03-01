---
keywords: Automated Personalization;ap；上傳資料；離線資料；個人化演算法；自動鎖定目標；最佳作法
description: 了解在Adobe中建立個人化模型時，如何上傳離線資料（例如CRM資訊） [!DNL Target] Automated Personalization(AP)活動。
title: 如何上傳用於個人化演算法的資料？
feature: Automated Personalization
exl-id: c750e0e5-8ebd-49a2-9705-05f593aaf0b9
source-git-commit: 3ac61272ee1ccd72a8670966f181e7798cbe9f76
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 67%

---

# 上傳 [!DNL Target] 個人化演算法

離線資料（例如CRM資訊或客戶流失傾向分數）在中建立個人化模型時，可能會有難以置信的價值 [!DNL Adobe Target] [!UICONTROL Automated Personalization] (AP)活動。

有數種方式可以在[!UICONTROL 自動個人化] (AP) 和[!UICONTROL 自動鎖定目標]個人化演算法中輸入資料。除了 [將資料傳入Target的方法](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/methods-to-get-data-into-target/){target=_blank}, Experience Cloud shared audiences (Adobe Analytics, Audience Management){target=_blank} 和活動內報表對象也用於演算法中。

如需自動個人化和自動鎖定目標個人化演算法自動收集和使用之資料的相關資訊，請參閱[自動個人化資料收集](/help/main/c-activities/t-automated-personalization/ap-data.md)。

## 最佳實務 {#section_DE96C7B7D114491DBB67FB5B7DA3D37B}

以下清單介紹了為 Target 個人化演算法上傳資料的最佳作法:

* Target 的個人化演算法可得到高品質資料越多，AP 和自動鎖定目標活動中產生的模型品質就越好。
* 限制使用多個提供相同用途的設定檔指令碼或屬性。
* 如果不需要，請勿傳遞唯一的 ID，例如工作階段 ID。
* 複查 Target 自動收集的資料 ([Target 個人化演算法的資料收集](/help/main/c-activities/t-automated-personalization/ap-data.md))，如此一來，您便不會傳送重複的資訊。例如，Target 會使用 IP 位址來判斷訪客的郵遞區號。不必以單獨的變數傳遞此資訊。
* 請勿在相同屬性/變數中傳遞多個值。如果連接多個變數，Target 的個人化演算法會將每個字串視為唯一值，降低個人化資訊的價值。
* 使用易記且有意義的命名慣例讓您的[個人化前瞻分析報表](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767)更清晰易懂。
