---
keywords: 對象;對象規則;合併對象;排除;新增排除項目;隨選對象
description: 了解如何合併多個對象(包括Adobe Experience Cloud對象和 [!DNL Target] 對象)即時建立隨選對象。
title: 我可以合併多個對象以建立新對象嗎？
feature: Audiences
exl-id: 1d9bff9c-f63b-4e15-9809-71b046158b71
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '960'
ht-degree: 64%

---

# 合併多個對象

合併多個對象(包括 [!DNL Adobe Experience Cloud], [!DNL Adobe Experience Platform]，和 [!DNL Target] 對象)即時建立隨選對象。 您也可以從規則建立排除規則和排除對象。

>[!NOTE]
>
>此 [!DNL Adobe Experience Platform] 來源可供所有使用 [!DNL Target] 客戶使用 [Adobe Experience Platform Web SDK](https://developer.adobe.com/target/implement/client-side/aep-web-sdk/){target=_blank}。 可用對象 [!DNL Adobe Experience Platform] 可依原樣使用，或與現有對象結合，如本主題所述。
>
>如需詳細資訊，請參閱 [使用來自Adobe Experience Platform的對象](/help/main/c-target/c-audiences/audiences.md#aep).

假設您有「新訪客」對象和「Chrome 使用者」對象。針對特定的活動，您可能想要合併這些現有對象，以鎖定使用 Chrome 瀏覽器的新訪客作為目標。您不需要建立第三個對象並儲存在[!UICONTROL 對象]資料庫中，僅需在建立活動或編輯現有活動時合併這兩個對象。

再舉一例，您可以鎖定所有忠誠客戶。 例如，您可以包含特定 [!DNL Audience Manager] 忠誠度狀態的對象，並與 [!DNL Target] 對象由在目前工作階段期間註冊參加您的忠誠計畫的人員組成。 結合這兩個對象比建立第三個永久對象容易。

您可以使用AND和OR運算子結合最多20個對象。

您可以在 [!DNL Target] UI 各處建立並使用合併的對象。

## 建立活動時建立合併的受眾 {#section_2F1CE9434CC04174B4BA2BFC89B85D77}

在三步驟引導式工作流程期間，您可以在活動的 [!UICONTROL Target] 頁面上建立隨選合併的對象。

1. 建立 [活動](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)，在 **[!UICONTROL 定位]** 頁面，按一下三個垂直的點，然後按一下 **[!UICONTROL 取代受眾]**.

   ![步驟結果](assets/edit_audience.png)

1. 在&#x200B;**[!UICONTROL 「選擇對象」]**&#x200B;頁面上，選取所需對象旁的核取方塊，以使用這些對象作為合併對象的建置區塊。

   使用 [!UICONTROL 搜尋對象] 方塊來縮小您對所需對象的搜尋範圍。

   ![步驟結果](assets/combine_multiple_audiences1.png)

1. 按一下 **[!UICONTROL 合併多個對象]** 在右上角。

   ![步驟結果](assets/combine_multiple_audiences2.png)

1. (條件式) 視需要編輯新的合併對象。

   此 [!UICONTROL 編輯對象] 對話方塊可讓您從左側拖放其他對象建置區塊至新的合併對象。 您也可以新增排除規則和排除對象。

   1. 使用拖放功能，將現有區段內的對象新增為第2層建置區塊。

      例如，假設在上一個範例中，您現在想要將 Safari 使用者納入合併對象中。搜尋「Safari 瀏覽器」受眾並拖曳到右邊的「Firefox 瀏覽器」方塊中 (如下列範例所示)。

      ![combine_multiple_audiences3影像](assets/combine_multiple_audiences3.png)

      請注意，兩個瀏覽器類型對象之間的運算子是 &quot;AND&quot;。選取 [!UICONTROL 和] 下拉式清單並變更為「OR」，為使用Firefox或Safari的新訪客建立新的合併對象。 請小心，避免建立規則來排除所有可能的對象成員。例如，某人無法同時使用 Firefox 與 Safari 來造訪頁面。

      >[!NOTE]
      >
      >合併對象時，運算子 (AND 或 OR) 必須保持相同。您不能混用 &amp; 比對運算子。

   1. 若要將排除項目新增至規則，請按一下 **[!UICONTROL 排除]**.

      ![combine_multiple_audiences3a影像](assets/combine_multiple_audiences3a.png)

      拖放對象。

      例如，若要從新訪客中排除美國訪客，您可以拖曳「市場」：美國觀眾進入盒子。

      此合併對象包含您的網站上所有使用 Safari 或 Firefox 的新訪客 (排除來自 San Francisco 的新訪客)。

   1. 若要從規則中排除對象，請按一下&#x200B;**[!UICONTROL 「排除項目」]** > **[!UICONTROL 「排除此對象」]**。

      例如，您可以建立合併的對象來包含網站的所有新訪客，但排除使用 Firefox 的新訪客。不需要建立合併的對象來明確包含多個瀏覽器 (Safari、Chrome 和 Internet Explorer)，但又不包含 Firefox，直接排除使用 Firefox 的訪客更輕鬆又快速。

1. 為合併的對象提供描述性名稱，然後按一下 **[!UICONTROL 完成]**.

## 建立合併的受眾以用於量度鎖定目標 {#section_A42E795AFCBD4575809C5942039910F0}

您可以在活動的[!UICONTROL 「目標與設定」]頁面上建立隨選合併對象，以用於量度鎖定目標。例如，若要使用合併的對象以根據轉換來建立鎖定目標，請執行下列動作:

1. 編輯或建立[活動](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)，在&#x200B;**[!UICONTROL 「目標與設定」]**&#x200B;頁面上，選取&#x200B;**[!UICONTROL 「轉換」]**&#x200B;作為成功量度，然後選取「已檢視 Mbox」**[!UICONTROL 作為動作。]**
1. 在&#x200B;**[!UICONTROL 「搜尋 Mbox」]**&#x200B;欄位中選取所需的 Mbox。

   ![combine_multiple_audiences4影像](assets/combine_multiple_audiences4.png)

1. 按一下齒輪圖示，然後按一下&#x200B;**[!UICONTROL 「新增對象鎖定目標」]**。
1. 按一下&#x200B;**[!UICONTROL 「新增對象/目標狀況」]**&#x200B;連結，以顯示[!UICONTROL 「選擇對象」]對話方塊。

   ![combine_multiple_audiences5影像](assets/combine_multiple_audiences5.png)

1. 繼續進行[步驟 2](/help/main/c-target/combining-multiple-audiences.md#section_2F1CE9434CC04174B4BA2BFC89B85D77)「在建立活動時建立結合的對象」以建立結合的對象。

## 建立合併的對象以用於報表 {#section_4682D342EFBB43C38E54B99B3A1E14CD}

您可以在活動的[!UICONTROL 「目標與設定」]頁面上建立隨選合併對象，以用於報表。

1. 編輯或建立[活動](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)，在&#x200B;**[!UICONTROL 「目標與設定」]**&#x200B;頁面上，按一下&#x200B;**[!UICONTROL 「報表對象」]**&#x200B;下的[!UICONTROL 「新增對象」]圖示，以顯示[!UICONTROL 「選擇對象」]頁面。

   ![combine_multiple_audiences6影像](assets/combine_multiple_audiences6.png)

1. 繼續進行[步驟 2](/help/main/c-target/combining-multiple-audiences.md#section_2F1CE9434CC04174B4BA2BFC89B85D77)「在建立活動時建立結合的對象」以建立結合的對象。

## 編輯活動時建立合併的受眾 {#section_364A12CE96E04B61B7C18113AA586C2C}

您可以在編輯現有活動時建立隨選合併對象。

1. 在[!UICONTROL 「活動」]頁面中，暫留在所需的活動上，然後按一下&#x200B;**[!UICONTROL 「編輯」]** 圖示。

   或

   按一下所需的活動以開啟，然後按一下&#x200B;**[!UICONTROL 「編輯活動」]**。

1. 按一下 **[!UICONTROL 設定]** > **[!UICONTROL 對象]** > **[!UICONTROL 多個對象]**.

   ![設定 > 受眾 > 多個受眾](assets/combine_multiple_audiences7.png)

1. 按一下活動目前對象旁的更多選項圖示 (垂直三個點)，然後按一下&#x200B;**[!UICONTROL 「變更對象」]**。

   ![變更對象](assets/combine_multiple_audiences8.png)

1. 繼續進行[步驟 2](/help/main/c-target/combining-multiple-audiences.md#section_2F1CE9434CC04174B4BA2BFC89B85D77)「在建立活動時建立結合的對象」以建立結合的對象。
