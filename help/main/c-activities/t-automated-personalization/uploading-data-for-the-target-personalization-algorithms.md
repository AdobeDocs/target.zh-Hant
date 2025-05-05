---
keywords: Automated Personalization；ap；上傳資料；離線資料；個人化演演算法；自動鎖定目標；自動鎖定目標；最佳實務
description: 瞭解如何在 [!DNL Adobe Target] [!UICONTROL Automated Personalization] (AP)和[!UICONTROL Auto-Target]活動中建立個人化模型時上傳離線資料。
title: 如何上傳用於Personalization演演算法的資料？
feature: Automated Personalization, Auto-Target
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=zh-Hant#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
exl-id: c750e0e5-8ebd-49a2-9705-05f593aaf0b9
source-git-commit: 3f64da1c9a1146e4d2d9389d6d5ce764764d2d9c
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 10%

---

# 上傳[!DNL Target]個人化演演算法的資料

在[!DNL Adobe Target] [!UICONTROL Automated Personalization] (AP)和[!UICONTROL Auto-Target]活動中建立個人化模型時，離線資料（例如CRM資訊或客戶流失傾向分數）可能會非常寶貴。

有數種方式可以在[!UICONTROL Automated Personalization] (AP)和[!UICONTROL Auto-Target]個人化演演算法中輸入資料。 除了[將資料傳入Target](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=zh-Hant){target=_blank}的方法以外，[!DNL Target]演演算法中也使用[!DNL Experience Cloud]個共用對象([!UICONTROL Adobe Analytics]、[!DNL Audience Manager])和活動內報表對象。

有關[!UICONTROL Automated Personalization]和[!UICONTROL Auto-Target]個人化演演算法自動收集和使用之資料的資訊，請參閱[Automated Personalization資料收集](/help/main/c-activities/t-automated-personalization/ap-data.md)。

## 最佳實務 {#section_DE96C7B7D114491DBB67FB5B7DA3D37B}

下列清單提供上傳[!DNL Target]個人化演演算法資料的最佳實務：

* [!DNL Target]個人化演演算法可用的高品質資料越多，[!UICONTROL Automated Personalization]和[!UICONTROL Auto-Target]活動中產生的模型品質越好。
* 限制使用多個提供相同用途的設定檔指令碼或屬性。
* 請勿傳遞唯一ID，例如工作階段ID （若不需要）。
* 檢閱[!DNL Target]自動收集哪些資料([Target Personalization演演算法的資料收集](/help/main/c-activities/t-automated-personalization/ap-data.md))，這樣您就不會傳送重複的資訊。 例如，[!DNL Target]使用IP位址來判斷訪客的郵遞區號。 不必以單獨的變數傳遞此資訊。
* 請勿在相同的屬性或變數中傳遞多個值。 如果串連多個變數，[!DNL Target]個人化演演算法會將每個字串視為唯一值，減少個人化資訊的值。
* 使用令人難忘且有意義的命名慣例，讓您的[Personalization Insights報表](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767)更易於理解。
