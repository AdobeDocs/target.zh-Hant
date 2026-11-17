---
keywords: 多個客群; 體驗版本; 鎖定體驗版本
description: 瞭解如何在A/B活動中使用相同體驗的版本鎖定不同的受眾區段。
title: 我可以在A/B活動中使用多個體驗版本嗎？
feature: A/B Tests
exl-id: 7afe36f0-ec46-4d63-bfff-45d2c8923a04
TQID: 'https://experienceleague.adobe.com/FleyH-u5cWI5vku9E4-RMWeIc95WgPy-VQ-eytxka18'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ab2570eb-4844-49aa-8334-e91a345525e5
    internal-label: A/B Tests
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 4876228feee28031373f7e0abe62a66b05b15274
workflow-type: tm+mt
source-wordcount: '488'
ht-degree: 8%
---
# A/B 測試中的多個體驗客群 {#multiple-experience-audiences}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解如何在A/B活動中使用相同體驗的版本鎖定不同的對象，並以使用案例加以說明，包含要遵循的步驟和最佳實務。

>[!ENDSHADEBOX]

在[!DNL Adobe Target]個A/B活動中，您可以將相同體驗的版本鎖定至不同的對象。 您可以在&#x200B;**[!UICONTROL 視覺化體驗撰寫器]** (VEC)或表單式體驗撰寫器中為體驗設定多個對象。

系統會為體驗收集資料（不論版本為何），因此報表會顯示體驗的效能，而非每個版本的效能。 訪客也可以在設定檔變更時，在體驗對象之間切換。 他們不會在活動的生命週期中卡在相同的體驗中。

## 使用案例 {#use-case}

您正在測試兩個體驗：

* 地理目標橫幅

* 通用橫幅。

每個地理位置的橫幅必須不同，但測試的目標是判斷地理鎖定目標是否比一般內容表現更好。

如果您為每個地點設定個別的體驗，您可以測量每個地理位置與其他地理位置的表現。 和一般橫幅相比，地理鎖定目標是否有助於達成成功目標時，您無法測量。

在此情況下，您需要有地理特定版本的體驗，以便您將地理鎖定目標體驗與非地理鎖定目標控制項測試。

若要設定地理特定版本：

1. [建立一個 A/B 活動](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)，如同您一般的作法。

   當您設定具有多個版本的體驗時，請依照下列步驟所述，選取每個版本的對象。

1. 選取體驗，然後按一下&#x200B;**[!UICONTROL 設定]** > **[!UICONTROL 多個對象]**。

1. 在&#x200B;**[!UICONTROL 體驗對象]**&#x200B;窗格中，按一下&#x200B;**[!UICONTROL 新增對象]**&#x200B;圖示（ ![新增圖示](/help/main/assets/icons/Add.svg) ），然後選取您要鎖定的第一個對象。 對每個客群重複。

   如果對象尚未存在，[請建立對象](/help/main/c-target/c-audiences/create-audience.md)並加以設定。

1. 繼續設定活動。

## 最佳做法 {#best-practices}

* 選擇互斥的對象。 如果訪客符合一個以上對象的資格，系統會傳回所有這些對象的內容，而頁面上會顯示最後列出的對象內容。 這適用於VEC中建立的活動。
* 圖表中所定義的活動專案對象，會使用AND條件與體驗對象結合。 若要進入活動，訪客必須符合活動對象和其中一個體驗對象的資格。
* 新增相同的對象作為報表的區段。 這有助於您在體驗A與B的高層級上檢視測試結果，在體驗A與B的低層級上僅檢視「瀏覽器lang ja_JP」的測試結果。 這僅適用於以[!DNL Target]為基礎的報表，不適用於以[!DNL Analytics]為基礎的報表。
