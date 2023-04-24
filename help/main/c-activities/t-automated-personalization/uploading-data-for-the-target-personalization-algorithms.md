---
keywords: Automated Personalization;ap；上傳資料；離線資料；個人化演算法；自動鎖定目標；最佳作法
description: 了解在Adobe中建立個人化模型時，如何上傳離線資料（例如CRM資訊） [!DNL Target] Automated Personalization(AP)活動。
title: 如何上傳用於個人化演算法的資料？
feature: Automated Personalization
exl-id: c750e0e5-8ebd-49a2-9705-05f593aaf0b9
source-git-commit: 2fc704a1779414a370ffd00ef5442fce36e7a5dd
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 32%

---

# 上傳 [!DNL Target] 個人化演算法

離線資料（例如CRM資訊或客戶流失傾向分數）在中建立個人化模型時，可能會有難以置信的價值 [!DNL Adobe Target] [!UICONTROL Automated Personalization] (AP)活動。

有數種方式可以在[!UICONTROL 自動個人化] (AP) 和[!UICONTROL 自動鎖定目標]個人化演算法中輸入資料。除了 [將資料傳入Target的方法](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html){target=_blank}, Experience Cloud shared audiences (Adobe Analytics, Audience Management){target=_blank} 和活動內報表對象也用於演算法中。

如需自動個人化和自動鎖定目標個人化演算法自動收集和使用之資料的相關資訊，請參閱[自動個人化資料收集](/help/main/c-activities/t-automated-personalization/ap-data.md)。

## 最佳實務 {#section_DE96C7B7D114491DBB67FB5B7DA3D37B}

以下清單介紹了為 Target 個人化演算法上傳資料的最佳作法:

* Target的個人化演算法所提供的高品質資料越多，AP和自動鎖定目標活動中產生的模型品質就越高。
* 限制使用多個提供相同用途的設定檔指令碼或屬性。
* 若不需要，請勿傳遞唯一ID，例如工作階段ID。
* 檢閱Target自動收集的資料( [Target個人化演算法的資料收集](/help/main/c-activities/t-automated-personalization/ap-data.md))，以免傳送重複資訊。 例如，Target 會使用 IP 位址來判斷訪客的郵遞區號。不必以單獨的變數傳遞此資訊。
* 請勿在相同屬性/變數中傳遞多個值。如果串連了多個變數，Target的個人化演算法會將每個字串視為唯一值，減少個人化資訊的值。
* 使用難忘且有意義的命名慣例，讓您 [個人化前瞻分析報表](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767) 更容易理解。
