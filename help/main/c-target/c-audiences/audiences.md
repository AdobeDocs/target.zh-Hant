---
keywords: 對象;對象規則;建立對象;建立對象;鎖定目標對象;報表對象;報表對象;區段;自訂設定檔參數;對象定義;對象清單
description: 了解如何在 [!DNL Adobe Target].
title: 如何使用對象清單？
feature: Audiences
exl-id: 7af7f101-f550-4fdc-bcd9-90e4107b0415
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '1505'
ht-degree: 21%

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
   >此 [!DNL Adobe Experience Platform] 來源可供所有使用 [!DNL Target] 客戶使用 [Adobe Experience Platform Web SDK](https://developer.adobe.com/target/implement/client-side/aep-web-sdk/){target=_blank}。 可用對象 [!DNL Adobe Experience Platform] 可原樣使用或 [結合現有對象](/help/main/c-target/combining-multiple-audiences.md).
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

使用在 [!DNL Adobe Experience Platform] 中建立的對象可提供更豐富的客戶資料，從而帶來更具影響力的個人化。此 [Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=zh-Hant){target=_blank}(RTCDP)，內建於 [!DNL Adobe Experience Platform]，可協助公司匯集來自多個企業來源的已知和匿名資料。 此程式可讓您建立客戶設定檔，以用於即時提供跨所有管道和裝置的個人化客戶體驗。
+通過連接 [!DNL Target] 到 [!DNL Real-time Customer Data Platform]，客戶可借由解鎖先前可能無法存取的新區段，來擴充其網路個人化 [!DNL Target] 以在客戶網站造訪的第一頁上啟用即時毫秒個人化。 使用中建立的對象和設定檔屬性 [!DNL Adobe Experience Platform] 可讓您展開可用的資料點，以便更豐富的個人化。

此整合可解鎖Real-time CDP的主要使用案例：

* 同頁/下次點擊個人化
* 首次/未知使用者個人化

主要功能包括：

* 與Real-time CDP/整合的直接Target[!DNL Adobe Experience Platform] 在邊上(移除 [!DNL Audience Core services] - AAM)
* [!UICONTROL Target Edge Destinations卡] 與治理和政策執行
* Real-time CDP Segments和共用配置檔案屬性

Real-time CDP Profile Attributes功能限制和考量事項：

* 指定選件內的屬性必須來自相同的AEP沙箱。 （換言之，選件不能包含來自不同AEP沙箱的屬性。）
* 指定選件中的屬性可能來自不同來源；即Target設定檔和AEP設定檔。（換言之，無論屬性來自Target或AEP設定檔，您都可以結合屬性。）
* 定義選件時，如果屬性沒有明確值，您可以為即時CDP設定檔屬性指派預設值。 例如，如果同意或控管原則封鎖了個人化服務中使用的屬性，則可改用預設值。
* 共用時，自動鎖定目標和Automated Personalization的人工智慧/機器學習個人化模型會使用即時CDP設定檔屬性。

>[!NOTE]
>
>Beta中目前提供即時CDP設定檔屬性功能，供HTML選件和 [JSON選件](/help/main/c-experiences/c-manage-content/create-json-offer.md).


如需詳細資訊，請參閱下列主題:

* [目的地發行說明](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=en#destinations){target=_blank}，位於 *Adobe Experience Platform發行說明*
* [為同一頁面和下一頁個人化設定個人化目的地](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html){target=_blank}，位於 *目的地概觀* 指南。
* [自訂個人化連線](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/personalization/custom-personalization.html){target=_blank}，位於 *目的地概觀* 指南
* [Adobe Target連線](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/personalization/adobe-target-connection.html){target=_blank}，位於 *目的地概觀* 指南
* [針對相同頁面和下一頁個人化使用案例設定個人化目的地](https://www.adobe.com/go/destinations-edge-personalization-en){target=_blank}，位於 *目的地概觀* 指南

### 其他資訊

使用對象時，請考量下列資訊 [!DNL Adobe Experience Platform]:

#### Personalization 使用案例

下表顯示使用 [!DNL Adobe Experience Platform Web SDK] 與使用at.js:

| 實施 | 啟用解決方案/使用案例 |
| --- | --- |
| at.js  | **解決方案**:<ul><li>[!DNL Adobe Audience Manager] (AAM)和 [!DNL Target]</li><li>[!DNL RTCDP] （Premium或Ultimate）和 [!DNL Target]</li><li>[!DNL RTCDP] （任何SKU）、 [!DNL AAM]，和 [!DNL Target]</li></ul>**使用案例**:<ul><li>下一工作階段個人化</li></ul> |
| [!DNL Platform Web SDK]或 [!DNL AEP Server-Side API] | **解決方案**:<ul><li>[!DNL RTCDP] （任何SKU）和 [!DNL Target]</li></ul>**使用案例**:<ul><li>下一工作階段個人化</li><li>透過Edge提供同頁個人化</li><li>共用區段時強制執行控管</li></ul>**解決方案**:<ul><li>[!DNL RTCDP] （任何SKU）、 [!DNL AAM]，和 [!DNL Target]</li></ul>**使用案例**:<ul><li>下一工作階段個人化</li><ul><li>[!DNL AAM] 區段</li><li>透過 [!DNL AAM]</li></ul><li>透過Edge提供同頁個人化</li><ul><li>[!DNL RTCDP] 區段</li><li>共用區段時強制執行控管</li></ul> |
| 混合 [!UICONTROL at.js] 和 [!DNL Platform Web SDK] | **解決方案**:<ul><li>[!DNL RTCDP] （任何SKU）和 [!DNL Target]</li></ul>**使用案例**:<ul><li>下一工作階段個人化</li><ul><li>對於具有 [!UICONTROL at.js]</li></ul><li>同頁個人化</li><ul><li>對於具有 [!DNL Platform Web SDK]</li></ul></ul>**解決方案**:<ul><li>[!DNL RTCDP] （任何SKU）、 [!DNL AAM]，和 [!DNL Target]</li></ul>**使用案例**:<ul><li>下一工作階段個人化</li><ul><li>對於具有 [!UICONTROL at.js]</li><li>[!DNL AAM] 區段</li><li>透過 [!DNL AAM]</li></ul> |

#### 區段評估時間

下表顯示來自不同實施案例之事件的區段評估時間：

| 藍本 | 邊緣段（毫秒評估） | 串流區段（分鐘評估） | 批次區段評估 |
| --- | --- | --- | --- |
| 事件/資料來源 [!DNL Adobe Experience Platform] SDK | 是 | 是 | 不適用 |
| 來自 [!UICONTROL at.js] | 無 | 是 | 不適用 |
| 來自 [!DNL Target Mobile] SDK | 無 | 是 | 不適用 |
| 批次上傳的事件 | 無 | 無 | 是 |
| 來自離線資料（資料流）的事件 | 無 | 是 | 是 |

### 影片：使用即時CDP進行下次點擊的個人化，以及 [!DNL Adobe Target]{#RTCDP}

了解如何使用個人化下次點擊 [!DNL Real-time Customer Data Platform] 和 [!DNL Adobe Target]. 此 [!DNL Adobe Target] 目的地 [!DNL Real-time CDP] 可讓您使用 [!DNL Experience Platform] 區段 [!DNL Adobe Target] 提供控管和隱私權支援的相同頁面和下一頁個人化。

如需詳細資訊，請參閱 [使用即時CDP和Adobe Target進行下一次點擊的個人化](https://experienceleague.adobe.com/docs/platform-learn/tutorials/experience-cloud/next-hit-personalization.html){target=_blank}，位於 *平台Tutorials* 指南。

>[!VIDEO](https://video.tv.adobe.com/v/340091?quality=12&learn=on)

### Adobe Target部落格和影片：

[[!DNL Adobe] announces Same Page Enhanced Personalization with [!DNL Adobe Target] 和 [!DNL Real-time Customer Data Platform]](https://blog.adobe.com/en/publish/2021/10/05/adobe-announces-same-page-enhanced-personalization-with-adobe-target-real-time-customer-data-platform){target=_blank}

## 訓練影片：使用對象 ![教學課程徽章](/help/main/assets/tutorial.png)

此影片包括關於使用對象的資訊。

* 說明詞語「對象」
* 說明將對象用於最佳化的兩個方式
* 在對象清單中尋找對象
* 將活動鎖定至對象
* 對活動中的被動報表使用對象

>[!VIDEO](https://video.tv.adobe.com/v/17398)
