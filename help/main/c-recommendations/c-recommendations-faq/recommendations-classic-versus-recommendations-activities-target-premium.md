---
keywords: 推薦;推薦演算法;推薦活動;推薦經典版
description: 檢閱資訊，以協助您瞭解舊Recommendations Classic與[!DNL Target] Premium中的Recommendations活動之間的差異。
title: Recommendations Classic與[!DNL Target] Premium中的Recommendations之間有何差異？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=zh-Hant#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Recommendations
exl-id: 07548155-9548-4870-b886-6cb4ff37a0bd
TQID: 'https://experienceleague.adobe.com/EoTkyY0kOwRKT52WIwOuTCoUziIJOnNtTo6llsTNpsM'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '629'
ht-degree: 19%
---
# Recommendations Classic與Recommendations活動在[!DNL Target] Premium中的比較 {#classic-versus-activities}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解[!DNL Recommendations Classic]與[!DNL Target Premium]中的[!DNL Recommendations]個活動有何不同，以便選擇。

>[!ENDSHADEBOX]

>[!NOTE]
>
>[!DNL Recommendations] 活動是 [!DNL Target Premium] 解決方案內建的功能。 在沒有 [!DNL Target Standard] 授權的 [!DNL Target Premium] 中無法使用。

在 Classic 版 [!DNL Recommendations] 產品中，您需要在頁面上建立資料收集 mbox，然後在特定的頁面位置新增顯示 mbox，才能顯示建議。 [!DNL Target Premium]中的[!DNL Recommendations]活動會收集訪客資訊，並在頁面上的任何位置建立建議，而不使用建議產品或內容之每個位置的mbox。 頁面標頭中的JavaScript參考可讓您在頁面上的任何位置啟用建議。 此參考會將金鑰（例如`entity.id`和`entity.categoryId`金鑰）傳遞至全域[!DNL Target] mbox。

[!DNL Recommendations Classic] 在 [!DNL Experience Cloud] UI 中顯示為專用的卡片。 可以從 [!DNL Recommendations] 工作流程內使用 [!DNL Target Premium] 活動。

[!DNL Recommendations Classic] 使用者可以繼續使用在 [!DNL Target Recommendations] 中使用 [!DNL Recommendations] mbox。 也可以保留mbox，並在標頭中使用JavaScript程式碼為頁面上的其他元素啟用[!DNL Recommendations]功能，將Classic和[!DNL Target]方法結合。 但是，為了取得完整的[!DNL Target]功能，[!DNL Recommendations Classic]使用者可能偏好刪除舊的mbox，而完全依賴[!DNL Target Recommendations]。

[!DNL Target]中的[!DNL Recommendations]活動在下列主要方面比[!DNL Recommendations Classic]改善。

## 推薦作為產品建議 {#recs-as-offer}

建議可包含在[!UICONTROL A/B測試] （包括[!UICONTROL 自動分配]和[!UICONTROL 自動鎖定目標]）和[!UICONTROL 體驗鎖定目標] (XT)活動中。 除了其他功能以外，這還允許測試和鎖定相同活動中的建議與非建議內容。 如需詳細資訊，請參閱 [推薦作為產品建議](/help/main/c-recommendations/recommendations-as-an-offer.md)。

## 條件 {#criteria-comparison}

[!DNL Target Recommendations]包含條件程式庫，其中包含預先封裝的規則集和設定集。 在[!DNL Recommendations Classic]中，每個建議都是手動建立，需要填寫表單並從一長串規則中選擇。 建立[!DNL Recommendations]活動時，會選擇預先設定的條件集。 您仍可建立自訂建議，但條件庫包含許多最常見的設定，這些設定已預先建立以簡化程式，並使用人們懂得的語言。 預封裝條件可以依原樣使用，也可以複製和編輯以符合特定需求。

![投影片顯示條件卡片Up-Sell，其語言為人們所瞭解、規則和邏輯，以及標示為](assets/overview_criteria.png)的組態

條件都依照行業別、頁面類型和實施來預先設定和排序。 例如，您可以在產品頁面上找到適用於零售業的條件，以顯示來自特定類別的產品（由`entity.categoryID`引數定義）。

如需使用和建立條件的相關資訊，請參閱[條件](/help/main/c-recommendations/c-algorithms/algorithms.md)。

## 工作流程 {#workflow-comparison}

[!DNL Recommendations]工作流程已簡化。 視覺化工作流程並非是複雜的表單，而是會引導您完成以下步驟：

1. 選取條件。
1. Select預先設定的[設計](/help/main/c-recommendations/c-design-overview/create-design.md#create-design)。
1. 預覽建議結果。

## 視覺預覽 {#visual-preview}

建議可在設定後預覽，並可進行任何必要的變更，而無須在頁面上建立建議，然後進行測試。 從 [!DNL Target] 內可以使用預覽。

## 目標定位 {#targeting-comparison}

[!DNL Recommendations Classic]有六個鎖定目標選項。 [!DNL Recommendations]個活動使用全部[!DNL Target]個鎖定目標選項。 已使用[!DNL Target]或其他[!DNL Adobe Experience Cloud]對象（例如[!DNL Audience Manager]和[!DNL Analytics]）定義對象。 接著會選取可看見每個設計的活動加入者百分比，以及可看見控制項的活動加入者百分比。

![所有訪客受眾的流量圖表、向上銷售條件、三個設計（每個設計有30%的流量）以及「無建議」控制群組](assets/overview_targeting.png)

## 報表 {#reporting-comparison}

在[!DNL Target]中，[!DNL Recommendations]提供改良的報告，這些報告利用[!DNL Target]和[!DNL Experience Cloud]的功能。 報表不會只顯示[!DNL Recommendations]提供的提升度來對照沒有這些提升度的結果，而是顯示有關[!DNL Recommendations]活動的完整資訊。

