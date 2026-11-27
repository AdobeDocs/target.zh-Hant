---
keywords: 促銷活動；前端促銷活動；後端促銷活動；促銷活動型別；專案清單；依屬性促銷；促銷集合
description: 瞭解如何新增提升的專案並控制其在您的Adobe [!DNL Target] Recommendations設計中的放置位置。 您可以新增靜態和動態促銷活動。
title: 如何在Recommendations設計中新增促銷活動？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="檢視Target Premium包含的內容。"
feature: Recommendations
exl-id: bd5e5e12-a712-4c4c-9cf8-6b0f4834067b
TQID: 'https://experienceleague.adobe.com/tAfKOzwjnUJgypDh-4LdVukNlTVwMS4UkvcNmCaCV0E'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '695'
ht-degree: 3%
---
# 新增促銷活動 {#add-promotions}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解如何將提升的專案新增至[!DNL Recommendations]設計，以及如何決定其排序順序。

>[!ENDSHADEBOX]

除了條件所建議的專案之外，促銷活動還會在[!DNL Recommendations]設計中放置特定專案。 它們在設計中使用可用的位置，並優先於條件結果和備份建議。 例如，如果某個設計有六個位置，其中兩個用於促銷活動，則根據條件推薦的專案將保留四個位置。

促銷活動會根據活動條件所建議的專案刪除重複專案，因此在單一建議匣中，指定專案不會顯示兩次。

![變更促銷活動對話方塊，其中前端促銷活動和後端促銷活動已關閉](assets/add_promotion_toggles.png)

>[!NOTE]
>
>使用促銷活動會變更CSV結構和輸出。 這些變更可能會影響任何涉及CSV的外部程式，例如電子郵件。

## 新增促銷活動 {#add-promotion}

促銷活動會定義促銷哪些專案、其使用多少設計版塊，以及顯示的時段。

1. 在&#x200B;**[!UICONTROL 選項]**&#x200B;頁面上，按一下&#x200B;**[!UICONTROL 前端促銷活動]**&#x200B;或&#x200B;**[!UICONTROL 後端促銷活動]**&#x200B;切換。

   下圖顯示處於「開啟」位置的&#x200B;**[!UICONTROL 前端促銷活動]**&#x200B;切換按鈕。 促銷活動可在條件結果之前和之後插入。

   ![變更促銷活動對話方塊，並開啟前端促銷活動切換按鈕，顯示「設計位置數量」、「排程」和「促銷活動型別」選項](/help/main/c-recommendations/t-create-recs-activity/assets/add_promotion_front.png)

1. 設定要用於促銷專案的設計位置數量&#x200B;**[!UICONTROL 數量]**。

   視[!DNL Recommendations]設計而定，最多可使用20個位置。 根據條件傳回的建議無法使用所使用的每個位置。

1. 為升級的專案設定&#x200B;**開始**&#x200B;日期和&#x200B;**結束**&#x200B;日期。

   若未設定開始日期，則促銷活動會立即開始。 如果未設定結束日期，則促銷活動會無限期地執行。

1. Select a **[!UICONTROL 促銷活動型別]**：

   * **[!UICONTROL 專案清單]**：輸入要促銷的專案的`entity.id`個值（以逗號分隔）。
   * **[!UICONTROL 依屬性促銷]**：新增規則以定義要促銷的專案的屬性。 此選項可透過靜態和動態包含規則進行動態比對。 如需詳細資訊、範例和使用案例，請參閱[使用動態和靜態包含規則](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#inclusion-rules)。
   * **[!UICONTROL 促銷一個集合]**：選擇要促銷的專案集合。 可以為促銷活動建立新的集合。 請參閱[建立集合](/help/main/c-recommendations/c-products/collections.md#task_1256DFF6842141FCAADD9E1428EF7F08)。

   促銷活動型別也會決定促銷專案的排序順序。 檢視[促銷活動型別和排序順序](#promotion-sort-order)。

   ![使用反白顯示的「促銷活動型別」選項變更促銷活動對話方塊：專案清單、依屬性促銷活動以及促銷集合](/help/main/c-recommendations/t-create-recs-activity/assets/promotion_type.png)

1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

促銷活動會套用至活動中的所有體驗。

## 促銷活動型別與排序順序 {#promotion-sort-order}

推進專案的排序順序取決於推進型別，如下表所示。

| 促銷活動型別 | 預設排序 | 備份排序 | 動態篩選選項 |
| --- | --- | --- | --- |
| **[!UICONTROL 專案清單]** | 在[!DNL Target] UI或API中輸入的順序 | 隨機（透過UI或API選取時） | 否 |
| **[!UICONTROL 依屬性促銷]** | `entity.value` （遞減順序） | 無隨機化 | 是 |
| **[!UICONTROL 提升集合]** | `entity.value` （遞減順序） | 無隨機化 | 否 |

* **[!UICONTROL 專案清單]**：預設的排序順序是在[!DNL Target] UI或API中輸入的順序。 **[!UICONTROL 隨機專案順序]**&#x200B;核取方塊適用於此型別。 當清單包含的專案多於為促銷活動設定的位置數量時，此選項會隨機化設計中顯示的促銷專案。 在每個點選上，[!DNL Target]會從整個促銷活動集中隨機選取範本中啟用促銷活動的專案。
* **[!UICONTROL 依屬性升級]**&#x200B;和&#x200B;**[!UICONTROL 升級集合]**：預設順序是以`entity.value`屬性為基礎，以遞減數字順序。 隨機排列順序不適用。

如果實體沒有`entity.value`屬性（例如，企業不銷售產品），則發佈日期等數值可傳入`entity.value`屬性。 接著會以遞減順序依最近發佈日期來排序促銷專案。 `entity.value`屬性為double型別，不接受字串。
