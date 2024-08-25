---
keywords: 客群;客群規則;合併客群;排除;新增排除項目;隨選客群
description: 瞭解如何立即結合多個對象(包括Adobe Experience Cloud對象和 [!DNL Target] 對象)以建立隨選對象。
title: 我可以合併多個對象以建立新對象嗎？
feature: Audiences
exl-id: 1d9bff9c-f63b-4e15-9809-71b046158b71
source-git-commit: fe1e97710e7692ba7724103853ed7438c3f361b1
workflow-type: tm+mt
source-wordcount: '886'
ht-degree: 38%

---

# 合併多個客群

即時合併多個對象（包括[!DNL Adobe Experience Cloud]、[!DNL Adobe Experience Platform]和[!DNL Target]對象）以建立隨選對象。 您也可以從規則建立排除規則和排除對象。

>[!NOTE]
>
>[!DNL Adobe Experience Platform]來源可供所有使用[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=en){target=_blank}的[!DNL Target]客戶使用。 [!DNL Adobe Experience Platform]中可用的對象可以如原樣使用，或如本主題中所述，與現有對象結合。
>
>如需詳細資訊，請參閱[使用來自Adobe Experience Platform的對象](/help/main/c-target/c-audiences/audiences.md#aep)。

假設您有「新訪客」對象和「Chrome 使用者」對象。針對特定的活動，您可能想要合併這些現有對象，以鎖定使用 Chrome 瀏覽器的新訪客作為目標。您可以在活動建立期間或編輯現有活動時，結合這兩個對象，而不需要建立第三個對象並將其儲存在[!UICONTROL Audiences]資料庫中。

再舉一例，您可以鎖定所有忠誠客戶。 例如，您可以包含特定的[!DNL Audience Manager]對象來加入忠誠度狀態，並將其與目前工作階段中加入忠誠度計畫的人員所組成的[!DNL Target]對象結合。 結合這兩個對象比建立第三個永久對象容易。

您可以使用AND和OR運運算元來合併最多20個對象。

您可以在 [!DNL Target] UI 各處建立並使用合併的客群。

## 建立活動時建立合併的受眾 {#section_2F1CE9434CC04174B4BA2BFC89B85D77}

在三步驟引導式工作流程期間，您可以在活動的[!UICONTROL Target]頁面上建立隨選合併的對象。

1. 建立[活動](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)時，請在&#x200B;**[!UICONTROL Targeting]**&#x200B;頁面上按一下三個垂直的點，然後按一下&#x200B;**[!UICONTROL Replace Audience]**。

   ![步驟結果](assets/edit_audience.png)

1. 在&#x200B;**[!UICONTROL Choose Audience]**&#x200B;頁面上，選取所需對象旁的核取方塊，以使用這些對象作為合併對象的建置區塊。

   使用[!UICONTROL Search Audiences]方塊來縮小所需對象的搜尋範圍。

   ![步驟結果](assets/combine_multiple_audiences1.png)

1. 按一下右上角的&#x200B;**[!UICONTROL Combine Multiple Audiences]**。

   ![步驟結果](assets/combine_multiple_audiences2.png)

1. (條件式) 視需要編輯新的合併對象。

   [!UICONTROL Edit Audience]對話方塊可讓您從左側將其他對象建置區塊拖放至新的合併對象中。 您也可以新增排除規則和排除對象。

   1. 使用拖放功能，將現有區段中的對象新增為第2層建置區塊。

      例如，假設在上一個範例中，您現在想要將 Safari 使用者納入合併客群中。搜尋「Safari 瀏覽器」客群並拖曳到右邊的「Firefox 瀏覽器」方塊中 (如下列範例所示)。

      ![combine_multiple_audiences3圖片](assets/combine_multiple_audiences3.png)

      請注意，兩個瀏覽器類型客群之間的運算子是 &quot;AND&quot;。選取[!UICONTROL And]下拉式清單並變更為「或」，即可針對使用Firefox或Safari的新訪客建立新的合併對象。 請小心，避免建立規則來排除所有可能的客群成員。例如，某人無法同時使用 Firefox 與 Safari 來造訪頁面。

      >[!NOTE]
      >
      >合併客群時，運算子 (AND 或 OR) 必須保持相同。您不能混用 &amp; 比對運算子。

   1. 若要將排除專案新增至規則，請按一下&#x200B;**[!UICONTROL Exclude]**。

      ![combine_multiple_audiences3a影像](assets/combine_multiple_audiences3a.png)

      拖放對象。

      例如，若要從新訪客中排除美國訪客，您可以將「市場：美國」受眾拖曳至方塊中。

      此合併客群包含您的網站上所有使用 Safari 或 Firefox 的新訪客 (排除來自 San Francisco 的新訪客)。

   1. 若要從規則中排除對象，請按一下「**[!UICONTROL Exclusion]** > **[!UICONTROL Exclude this Audience.]**」。

      例如，您可以建立合併的對象來包含網站的所有新訪客，但排除使用 Firefox 的新訪客。不需要建立合併的對象來明確包含多個瀏覽器 (Safari、Chrome 和 Internet Explorer)，但又不包含 Firefox，直接排除使用 Firefox 的訪客更輕鬆又快速。

1. 提供已合併對象的描述性名稱，然後按一下&#x200B;**[!UICONTROL Done]**。

## 建立合併的對象以用於量度鎖定目標 {#section_A42E795AFCBD4575809C5942039910F0}

您可以在活動的[!UICONTROL Goals & Settings]頁面上建立隨選合併的對象，以用於量度鎖定目標。 例如，若要使用合併的對象以根據轉換來建立鎖定目標，請執行下列動作:

1. 編輯或建立[活動](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)時，請在&#x200B;**[!UICONTROL Goals & Settings]**&#x200B;頁面上選取&#x200B;**[!UICONTROL Conversion]**&#x200B;作為成功量度，然後選取&#x200B;**[!UICONTROL Viewed an Mbox]**&#x200B;作為動作。
1. 在&#x200B;**[!UICONTROL Search mbox]**&#x200B;欄位中選取所需的mbox。

   ![combine_multiple_audiences4影像](assets/combine_multiple_audiences4.png)

1. 按一下齒輪圖示，然後按一下&#x200B;**[!UICONTROL Add Audience Targeting]**。
1. 按一下&#x200B;**[!UICONTROL Add Audience/Targeting Condition]**&#x200B;連結以顯示[!UICONTROL Choose Audience]對話方塊。

   ![combine_multiple_audiences5圖片](assets/combine_multiple_audiences5.png)

1. 繼續進行[步驟 2](/help/main/c-target/combining-multiple-audiences.md#section_2F1CE9434CC04174B4BA2BFC89B85D77)「在建立活動時建立結合的客群」以建立結合的客群。

## 建立合併的對象以用於報表 {#section_4682D342EFBB43C38E54B99B3A1E14CD}

您可以在活動的[!UICONTROL Goals & Settings]頁面上建立隨選合併的對象，以用於報表。

1. 編輯或建立[活動](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)時，請在&#x200B;**[!UICONTROL Goals & Settings]**&#x200B;頁面上按一下[!UICONTROL Audiences for Reporting]下方的&#x200B;**[!UICONTROL Add Audience]**&#x200B;圖示以顯示[!UICONTROL Choose Audience]頁面。

   ![combine_multiple_audiences6圖片](assets/combine_multiple_audiences6.png)

1. 繼續進行[步驟 2](/help/main/c-target/combining-multiple-audiences.md#section_2F1CE9434CC04174B4BA2BFC89B85D77)「在建立活動時建立結合的客群」以建立結合的客群。

## 編輯活動時建立合併的受眾 {#section_364A12CE96E04B61B7C18113AA586C2C}

您可以在編輯現有活動時建立隨選合併客群。

1. 從[!UICONTROL Activities]頁面，暫留在所需的活動上，然後按一下&#x200B;**[!UICONTROL Edit]**&#x200B;圖示。

   或

   按一下所需的活動以開啟，然後按一下&#x200B;**[!UICONTROL Edit Activity]**。

1. 按一下&#x200B;**[!UICONTROL Configure]** > **[!UICONTROL Audiences]** > **[!UICONTROL Multiple Audiences]**。

   ![設定 > 客群 > 多個客群](assets/combine_multiple_audiences7.png)

1. 按一下活動目前對象旁的更多選項圖示（三個垂直的點），然後按一下&#x200B;**[!UICONTROL Change Audience]**。

   ![變更客群](assets/combine_multiple_audiences8.png)

1. 繼續進行[步驟 2](/help/main/c-target/combining-multiple-audiences.md#section_2F1CE9434CC04174B4BA2BFC89B85D77)「在建立活動時建立結合的客群」以建立結合的客群。
