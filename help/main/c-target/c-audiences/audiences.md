---
keywords: 對象;對象規則;建立對象;建立對象;鎖定目標對象;報表對象;報表對象;區段;自訂設定檔參數;對象定義;對象清單
description: 了解如何在 [!DNL Adobe Target].
title: 如何使用對象清單？
feature: Audiences
exl-id: 7af7f101-f550-4fdc-bcd9-90e4107b0415
source-git-commit: 24f445128aa76eb7e0af7d0f2c5de96f11b8d110
workflow-type: tm+mt
source-wordcount: '817'
ht-degree: 31%

---

# 建立對象

中的對象 [!DNL Adobe Target] 決定誰可以看到鎖定目標活動中的內容和體驗。

可使用鎖定目標之處皆可使用對象。定位活動時，您有下列選項：

* 從 [!UICONTROL 對象] 清單
* [建立活動專屬對象](/help/main/c-target/creating-activity-only-audience.md) 並將目標定位
* [合併多個對象](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5) 建立隨選對象

您也可以使用 [!DNL Adobe Analytics] ，以在 [!DNL Target] 其他 [!DNL Adobe Experience Cloud] 應用程式。 請參閱 [Experience Cloud對象](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html??lang=zh-Hant) 在 *Experience Cloud中心介面元件* 指南。

中有兩種對象 [!DNL Target]:

* **鎖定對象：** 用於傳送不同內容給不同類型的訪客。
* **報表對象：** 用來判斷不同類型的訪客如何回應相同內容，以便您分析測試結果。

   在 [!DNL Target] 中，只有在使用 [!DNL Target] 作為報表來源時，才可設定報表對象。如果您使用 [ Adobe Analytics 作為報表來源](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T)，則必須在 [!DNL Analytics] 內設定報表對象。

## 使用 [!UICONTROL 對象] 清單 {#use-list}

若要存取[!UICONTROL 「對象」]清單，請按一下頂端功能表列中的&#x200B;**[!UICONTROL 「對象」]**:

![受眾清單](assets/audiences_list.png)

此 [!UICONTROL 對象] 清單包含您可在活動中使用的對象。 使用 [!UICONTROL 對象] 清單來建立、編輯、複製、複製或結合對象。 清單也會顯示建立對象的來源：

* [!DNL Adobe Target]
* [!DNL Adobe Target Classic]
* [!DNL Experience Cloud]
* [!DNL Adobe Experience Platform]

   >[!NOTE]
   >
   >此 [!DNL Adobe Experience Platform] 來源可供所有使用 [!DNL Target] 客戶使用 [Adobe Experience Platform Web SDK](https://developer.adobe.com/target/implement/client-side/aep-web-sdk/){target=_blank}. 可用對象 [!DNL Adobe Experience Platform] 可原樣使用或 [結合現有對象](/help/main/c-target/combining-multiple-audiences.md).
   >
   >使用者必須 [!UICONTROL 核准者] 或高於狀態 [!DNL Target] 設定 [!DNL Target] [!UICONTROL 目的地] AEP/RTCDP中的卡([!DNL Real-time Customer Data Platform])。
   >
   >如需詳細資訊，請參閱 [使用來自Adobe Experience Platform的對象](#aep).

預先定義的對象，例如「[!UICONTROL 新訪客]&quot;和&quot;[!UICONTROL 再度訪問的訪客]「 」無法重新命名。

使用原本於 [!DNL Experience Cloud] 或 [!DNL Adobe Experience Platform], [!DNL Target] 如果您參考 [!DNL Target] 稍後在 [!DNL Experience Cloud] 或 [!DNL Adobe Experience Platform].

* 如果對象已在 [!DNL Experience Cloud] 或 [!DNL Adobe Experience Platform]，此時 [!UICONTROL 對象] 清單和對象選擇器隨即顯示。 中的工具提示 [!DNL Target] UI也指出閱聽眾已刪除於 [!DNL Experience Cloud] 或 [!DNL Adobe Experience Platform].
* 若嘗試將多個對象與已刪除的對象合併，或嘗試儲存參考已刪除對象的活動，系統會顯示警告訊息。

您也可以鎖定自訂設定檔參數和 `user.` 參數。建立對象時，將您要用來定位活動的屬性拖曳至對象產生器視窗中。 如果未顯示所需的屬性，則mbox尚未觸發屬性。 在[!UICONTROL 「自訂參數」]下拉式清單中可取得其他自訂 mbox 參數。

使用 [!UICONTROL 篩選器] 按鈕來篩選 [!UICONTROL 對象] 按源列出： [!DNL Adobe Target], [!DNL Adobe Target Classic], [!DNL Experience Cloud]，和 [!DNL Adobe Experience Platform].

![篩選器選項 [!UICONTROL 對象] 清單](assets/filters.png)

使用 [!UICONTROL 搜尋對象] 框中 [!UICONTROL 對象] 清單。 您可以搜尋對象名稱的任何部分，或您可以將特定字串放在引號內。

您可以依對象名稱或上次修改日期來排序[!UICONTROL 「對象」]清單。若要依名稱排序，請按一下欄標題，然後選擇依遞增或遞減順序來顯示對象。

## 檢視受眾定義 {#section_11B9C4A777E14D36BA1E925021945780}

您可以在 [!DNL Target] UI而不開啟對象。 此功能適用於中建立的對象 [!DNL Target Standard/Premium] 從 [!DNL Target Classic] 或透過API建立。

例如，您可按一下 [!UICONTROL 檢視詳細資料] 圖示以取得。

![活動 > 受眾定義](assets/audience_definition_list.png)

按一下 [!UICONTROL 檢視詳細資料] 活動的圖示 [!UICONTROL 概述] 頁面：

![活動 > 受眾定義](assets/view-details-activity-overview.png)

受眾定義卡片會顯示受眾的類型、來源和屬性。 按一下 **[!UICONTROL 查看完整詳細資訊]** 查看參考該對象的其他活動（若適用）。 如果您從活動的 [!UICONTROL 概述] 頁面，按一下 **[!UICONTROL 受眾使用情形]**.

受眾使用資訊可協助您避免在編輯受眾時對其他活動造成意外影響。 資訊包括 [!UICONTROL 即時活動], [!UICONTROL 非作用中活動], [!UICONTROL 封存的活動]，和 [!UICONTROL 同步活動]. 此功能適用於所有對象(資料庫對象和 [僅限於此活動的對象](/help/main/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483))。

如果對象為 [結合至其他對象](/help/main/c-target/combining-multiple-audiences.md) 而合併的對象會用來建立活動，即兩個對象的使用資訊會列出新建立的活動。

![audience_definition_list_usage影像](assets/audience_definition_list_usage.png)

<!--The following audience definition card is for an audience imported from the Adobe Experience Cloud. In this instance, the audience was imported from Adobe Audience Manager (AAM).

![Usage tab on Audience Definition card](assets/audience_definition_mc.png)

The following details are available for these imported audience types:

| Audience Type | Details |
|--- |--- |
|Mobile audience|Marketing Name, Vendor, and Model.<br>The `matches | does not match` operator displays instead of `equals | does not equal`<br>![Imported Mobile Audience](/help/main/c-target/c-audiences/assets/imported_mobile_audience.png).|
|Visitor-behavior audience|**user.categoryAffinity:** `categoryAffinity` with `FAVORITE` parameter.<br>![Imported Category Affinity](/help/main/c-target/c-audiences/assets/imported_category_affinity.png)<br>**Monitoring:** Monitoring service equals true.<br>**No Monitoring Service:** Monitoring service equals false.<br>![Imported Monitoring](/help/main/c-target/c-audiences/assets/imported_monitoring.png)|
|Audiences using the NOT operator|**Single Rule:** Target displays the audience in the format `[All Visitor AND [NOT [rule]`. Single NOT rule displays with AND with `AllVisitor` audience.<br>![Imported Not Audience](/help/main/c-target/c-audiences/assets/imported_not_audience.png)|

Keep the following points in mind as you work with imported audiences:

* Expression target audiences are no longer supported in Target Standard/Premium. 
* Target Standard/Premium does not support some deprecated audiences or has improved operators for ease of use. Because of this, the definition of an imported audience, although working as per definition, does not mean that same is now available for creation in the Standard/Premium interface. For example, Social Audiences are visible with their rules but Target Standard/Premium does not allow social audiences to be created.-->

## 使用對象來自 [!DNL Adobe Experience Platform] {#aep}

使用在 [!DNL Adobe Experience Platform] 中建立的對象可提供更豐富的客戶資料，從而帶來更具影響力的個人化。

如需詳細資訊，請參閱 [使用對象來自 [!DNL Adobe Experience Platform]](/help/main/c-integrating-target-with-mac/integrating-with-rtcdp.md#aep).

## 訓練影片：使用對象 ![教學課程徽章](/help/main/assets/tutorial.png)

此影片包括關於使用對象的資訊。

* 說明詞語「對象」
* 說明將對象用於最佳化的兩個方式
* 在對象清單中尋找對象
* 將活動鎖定至對象
* 對活動中的被動報表使用對象

>[!VIDEO](https://video.tv.adobe.com/v/17398)
