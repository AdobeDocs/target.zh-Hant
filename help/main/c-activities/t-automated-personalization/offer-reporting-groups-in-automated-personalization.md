---
keywords: 自動個人化；選件；報表；群組；報表群組；ap
description: 瞭解如何在[!DNL Adobe Target] [!UICONTROL Automated Personalization]活動中使用選件報表群組。
title: 我可以在[!UICONTROL Automated Personalization]活動中使用選件報表群組嗎？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Reports
exl-id: 9058a6c5-c651-480f-9b23-d0782a13b042
TQID: 'https://experienceleague.adobe.com/VW3zVGXb3IuQMDaRyidbkjsbUrojvwFsvwP3yRVeHp4'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: e8a43148-398f-56c7-9433-6564f96999c2
    internal-label: Reports
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 44c6bdd4ab818226e76477782d7e4238b49d5cdc
workflow-type: tm+mt
source-wordcount: '926'
ht-degree: 3%
---
# [!UICONTROL Automated Personalization]中的選件報表群組 {#offer-reporting-groups}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解優惠方案報告群組如何在&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活動中運作、如何設定群組，以及如何在報告中檢視群組。

>[!ENDSHADEBOX]

報表群組可讓您將[!DNL Adobe Target] [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP)活動的選件組織成群組。 報表群組執行兩個重要功能:

* 這些功能可讓您查看 AP 活動報表中分組的選件。
* 它們在[!DNL Target]個人化模型的運作方式中起著關鍵作用。

當您使用報表群組時，[!DNL Target]會使用該群組所有選件的資料，為每個報表群組建立一個個人化模型。 若沒有報表群組，[!DNL Target]會為您的AP活動中的每個選件建立個人化模型。

當您的活動設定沒有足夠的資料來建置每個選件的個人化模型時，報表群組也會減少使用&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;的資料需求。 它們有助於解決新選件的「冷啟動」問題，這些選件會與類似選件分組，以便每個模型具有更多可供培訓的資料。

如果訪客以相同方式回應群組中的所有優惠方案，因此群組優惠方案的轉換率相近，此方法即會很好運作。 切勿將所有優惠方案放入單一報表群組中，也不要將具有不同轉換率的優惠方案分組，因為兩個選擇都可能會降低[!DNL Target]個人化模型的有效性。

>[!NOTE]
>
>如果從報表群組中移除或取代選件，則也會從群組中刪除看到該選件的歷史流量，因此刪除的選件不會對[!DNL Target]個人化模型用來學習的資料做出貢獻。


## 考量事項

### 使用已上線活動的報表群組

報表群組會影響[!DNL Target]建立模型的方式。 因此，[!DNL Adobe]建議，只有在您打算在活動上線時取代或新增優惠方案時，才使用報表群組。 如果將新優惠方案引入已上線的活動中，將新優惠方案放入具有現有類似優惠方案的群組中，可讓[!DNL Target]使用已為群組內其他優惠方案收集的資料來瞭解新優惠方案。

### 如何記錄優惠和位置的資料

AP活動具有位置和選件（可模型）的組合。 當[!DNL Target]在報表中記錄資料時，會考量這些組合，因此可清楚瞭解選件是來自哪個事件（顯示、按一下等）。

例如，活動可能有數個位置和數個選件，這些位置和選件可能會重疊。 如果訪客在不同位置看到多個這些選件，[!DNL Target]只會記錄這些選件的資料。 如果同一位訪客稍後點按了選件，[!DNL Target]只會記錄該組合中的事件（並非針對所有組合）。

同樣地，如果點按來自於量度中出現但未顯示選件的不同位置，則事件會記錄於活動下方，但不會記錄選件和位置的任何組合。 因此，此選件不會出現在選件報表群組中。 發生此行為是因為點選可能來自與提供選件不同的mbox。 在此情況下，量度會與活動建立關聯，但不會與選件建立關聯。

## 設定報表群組

將優惠方案指派給報表群組會決定[!DNL Target]如何建立其個人化模型，以及優惠方案在活動報表中的顯示方式。 在您建立活動時設定群組，或稍後如果您將新優惠方案新增至已上線活動。

1. 在AP活動的&#x200B;**[!UICONTROL 體驗]**&#x200B;頁面上，按一下&#x200B;**[!UICONTROL 管理內容]**&#x200B;圖示（![管理內容圖示](/help/main/assets/icons/Experience.svg)）。

1. 按一下&#x200B;**[!UICONTROL 「管理內容」]**&#x200B;對話方塊頂端的&#x200B;**[!UICONTROL 「選件」]**&#x200B;索引標籤。

   ![設定圖示](../assets/ap-offers-2.png)

1. （視條件而定）選擇要新增至報表群組的選件。

   * 若要新增單一選件，請按一下選件的&#x200B;**[!UICONTROL 更多動作]**&#x200B;圖示（![更多動作圖示](/help/main/assets/icons/MoreSmall.svg) ），然後按一下&#x200B;**[!UICONTROL 報表群組]**。
   * 若要一次新增多個選件，請選取選件對應的核取方塊，然後按一下對話方塊底部的&#x200B;**[!UICONTROL 報表群組]**。

1. 將選取的選件指派至報表群組。

   * 若要將選件指派給現有的報表群組，請選取&#x200B;**[!UICONTROL 現有]**，從下拉式清單中選取報表群組，然後按一下&#x200B;**[!UICONTROL 確認]**。
   * 若要建立選件的報表群組，請選取「**[!UICONTROL 新增]**」，命名新的報表群組，然後按一下「**[!UICONTROL 確認]**」。

若要縮小選件清單的範圍，請使用&#x200B;**[!UICONTROL 位置]**&#x200B;清單來篩選選件，或使用&#x200B;**[!UICONTROL 報表群組]**&#x200B;清單來篩選報表群組。 **[!UICONTROL 報表群組]**&#x200B;清單也提供&#x200B;**[!UICONTROL 未指派的選件]**&#x200B;選項，該選項會顯示尚未屬於任何報表群組的選件，因此您可以將它們指派給一個報表群組。

如需將選件鎖定在特定對象的相關資訊，請參閱[Target **[!UICONTROL Automated Personalization]**&#x200B;選件](/help/main/c-activities/t-automated-personalization/ap-target-offers.md#set-up-targeting-rules)。

## 在報表群組中檢視選件

**[!UICONTROL 選件層級]**&#x200B;報告會依報告群組顯示活動選件的執行方式，以便您可以比較群組以及個別選件。

1. 按一下&#x200B;**[!UICONTROL 活動]**，按一下清單中的&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活動，然後按一下&#x200B;**[!UICONTROL 報表]**&#x200B;索引標籤以顯示[選件層級](/help/main/c-reports/personalization-reports/reports-ap.md)報表。

   如果您有許多活動，請按一下&#x200B;**[!UICONTROL 顯示篩選器]** (funnel)圖示，然後選取&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;核取方塊以僅顯示&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活動。

1. 按一下表格中的&#x200B;**[!UICONTROL Control]**&#x200B;或&#x200B;**[!UICONTROL Targeted]**，以顯示報表群組內的未分組優惠方案和優惠方案。

   ![優惠方案群組：控制與目標](/help/main/c-reports/assets/offer-groups.png)

如需使用&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;報告（包括&#x200B;**[!UICONTROL 選件層級]**&#x200B;報告）的相關資訊，請參閱[Automated Personalization摘要報告](/help/main/c-reports/personalization-reports/reports-ap.md)。
