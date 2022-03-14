---
keywords: 對象;對象規則;建立對象;建立對象;鎖定目標對象;報表對象;報表對象;區段;自訂設定檔參數;對象定義;對象清單
description: 瞭解如何在 [!DNL Adobe Target]。
title: 如何使用受眾清單？
feature: Audiences
exl-id: 7af7f101-f550-4fdc-bcd9-90e4107b0415
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1333'
ht-degree: 23%

---

# 建立對象

觀眾 [!DNL Adobe Target] 確定誰在目標活動中看到內容和體驗。

可使用鎖定目標之處皆可使用對象。當瞄準活動時，您有以下選項：

* 從 [!UICONTROL 觀眾] 清單
* [建立特定於活動的受眾](/help/main/c-target/creating-activity-only-audience.md) 瞄準它
* [合併多個受眾](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5) 建立臨時訪問群體

您還可以使用收集的受眾資料 [!DNL Adobe Analytics] 用於即時目標和個性化 [!DNL Target] 其他 [!DNL Adobe Experience Cloud] 應用程式。 請參閱 [Experience Cloud觀眾](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html??lang=zh-Hant) 的 *Experience Cloud中央介面元件* 的子菜單。

有兩類觀眾 [!DNL Target]:

* **針對受眾：** 用於向不同類型的訪問者提供不同的內容。
* **報告受眾：** 用於確定不同類型的訪問者對相同內容的響應方式，以便您可以分析test結果。

   在 [!DNL Target] 中，只有在使用 [!DNL Target] 作為報表來源時，才可設定報表對象。如果您使用 [ Adobe Analytics 作為報表來源](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T)，則必須在 [!DNL Analytics] 內設定報表對象。

## 使用 [!UICONTROL 觀眾] 清單 {#use-list}

若要存取[!UICONTROL 「對象」]清單，請按一下頂端功能表列中的&#x200B;**[!UICONTROL 「對象」]**:

![受眾清單](assets/audiences_list.png)

的 [!UICONTROL 觀眾] 清單包含您可以在活動中使用的受眾。 使用 [!UICONTROL 觀眾] 清單，以建立、編輯、複製、複製或組合受眾。 該清單還顯示建立受眾的源：

* [!DNL Adobe Target]
* [!DNL Adobe Target Classic]
* [!DNL Experience Cloud]
* [!DNL Adobe Experience Platform]

   >[!NOTE]
   >
   >的 [!DNL Adobe Experience Platform] 源可供所有人使用 [!DNL Target] 客戶使用 [Adobe Experience PlatformWeb SDK](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md)。 從 [!DNL Adobe Experience Platform] 可以按原樣或 [結合現有觀眾](/help/main/c-target/combining-multiple-audiences.md)。
   >
   >用戶必須 [!UICONTROL 批准者] 或高於 [!DNL Target] 配置 [!DNL Target] [!UICONTROL 目標] AEP/RTCDP中的卡([!DNL Real-time Customer Data Platform])。
   >
   >有關詳細資訊，請參閱 [使用來自Adobe Experience Platform的觀眾](#aep)。

預定義的受眾，如「」[!UICONTROL 新訪問者]&quot;和&quot;[!UICONTROL 返回訪問者]，無法更名。

使用最初建立於 [!DNL Experience Cloud] 或 [!DNL Adobe Experience Platform]。 [!DNL Target] 如果您引用了 [!DNL Target] 後來刪除的活動 [!DNL Experience Cloud] 或 [!DNL Adobe Experience Platform]。

* 如果在 [!DNL Experience Cloud] 或 [!DNL Adobe Experience Platform]中，顯示警告表徵圖 [!UICONTROL 觀眾] 清單和訪問群體選取器。 中的刀尖 [!DNL Target] UI還指示訪問群體已在 [!DNL Experience Cloud] 或 [!DNL Adobe Experience Platform]。
* 若嘗試將多個對象與已刪除的對象合併，或嘗試儲存參考已刪除對象的活動，系統會顯示警告訊息。

您也可以鎖定自訂設定檔參數和 `user.` 參數。在建立受眾時，將要用於目標活動的屬性拖動到受眾生成器窗口中。 如果不顯示所需的屬性，則該屬性未被mbox激發。 在[!UICONTROL 「自訂參數」]下拉式清單中可取得其他自訂 mbox 參數。

使用 [!UICONTROL 篩選器] 按鈕 [!UICONTROL 觀眾] 按源列出： [!DNL Adobe Target]。 [!DNL Adobe Target Classic]。 [!DNL Experience Cloud], [!DNL Adobe Experience Platform]。

![中的篩選器選項 [!UICONTROL 觀眾] 清單](assets/filters.png)

使用 [!UICONTROL 搜索受眾] 框 [!UICONTROL 觀眾] 清單框。 您可以搜尋對象名稱的任何部分，或您可以將特定字串放在引號內。

您可以依對象名稱或上次修改日期來排序[!UICONTROL 「對象」]清單。若要依名稱排序，請按一下欄標題，然後選擇依遞增或遞減順序來顯示對象。

## 檢視受眾定義 {#section_11B9C4A777E14D36BA1E925021945780}

您可以在中的不同位置查看彈出式卡上的受眾定義詳細資訊 [!DNL Target] UI而不開啟觀眾。 此功能適用於在 [!DNL Target Standard/Premium] 和從 [!DNL Target Classic] 或通過API建立。

例如，通過按一下 [!UICONTROL 查看詳細資訊] 表徵圖：

![活動 > 受眾定義](assets/audience_definition_list.png)

通過按一下 [!UICONTROL 查看詳細資訊] 表徵圖 [!UICONTROL 概述] 頁：

![活動 > 受眾定義](assets/view-details-activity-overview.png)

受眾定義卡顯示他們的受眾類型、來源和屬性。 按一下 **[!UICONTROL 查看完整詳細資訊]** 查看引用該受眾的其他活動（如果適用）。 如果從活動查看受眾定義卡 [!UICONTROL 概述] 的 **[!UICONTROL 受眾使用情況]**。

受眾使用資訊可幫助您避免在編輯受眾時對其他活動產生意外影響。 資訊包括 [!UICONTROL 即時活動]。 [!UICONTROL 非活動活動]。 [!UICONTROL 存檔活動], [!UICONTROL 同步活動]。 此功能適用於所有觀眾(庫觀眾和 [僅活動受眾](/help/main/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483))。

如果觀眾 [與另一個觀眾](/help/main/c-target/combining-multiple-audiences.md) 組合的受眾用於建立活動，兩個受眾的使用資訊列出了新建立的活動。

![](assets/audience_definition_list_usage.png)

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

## 使用來自 [!DNL Adobe Experience Platform] {#aep}

使用在 [!DNL Adobe Experience Platform] 中建立的對象可提供更豐富的客戶資料，從而帶來更具影響力的個人化。的 [Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=zh-Hant){target=_blank}(RTCDP)，構建於 [!DNL Adobe Experience Platform]，幫助公司將來自多個企業來源的已知和匿名資料匯集在一起。 此流程允許您建立客戶配置檔案，這些配置檔案可用於即時提供跨所有渠道和設備的個性化客戶體驗。

通過連接 [!DNL Target] 到 [!DNL Real-time Customer Data Platform]，客戶可以通過解鎖以前可能無法訪問的新段來豐富其Web個性化 [!DNL Target] 在客戶訪問的第一頁上實現即時毫秒個性化。 使用在 [!DNL Adobe Experience Platform] 允許您擴展可用的資料點，以便更加個性化。

此整合可解鎖RTCDP的關鍵使用情形：

* 同頁/下一次點擊個性化
* 首次/未知用戶個性化

主要功能包括：

* 直接目標與RTCDP/[!DNL Adobe Experience Platform] 在邊上（刪除依賴項） [!DNL Audience Core services] - AAM
* [!UICONTROL 目標邊緣目標卡] 與治理強制
* 基於統一輪廓的邊緣分割和邊緣輪廓

如需詳細資訊，請參閱下列主題:

* [目標發佈說明](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=en#destinations){target=_blank} *Adobe Experience Platform發佈說明*
* [配置同頁和下一頁個性化的個性化目標](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html){target=_blank} *目標概述* 的子菜單。
* [自定義個性化連接](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/personalization/custom-personalization.html){target=_blank} *目標概述* 引導
* [Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/personalization/adobe-target-connection.html){target=_blank} *目標概述* 引導
* [為同一頁和下一頁個性化使用案例配置個性化目標](https://www.adobe.com/go/destinations-edge-personalization-en){target=_blank} *目標概述* 引導

### 其他資訊

使用來自 [!DNL Adobe Experience Platform]:

#### 個人化使用案例

下表顯示了使用 [!DNL Adobe Experience Platform Web SDK] 與使用at.js:

| 實施 | 已啟用解決方案/使用案例 |
| --- | --- |
| at.js  | **解決方案**:<ul><li>[!DNL Adobe Audience Manager] (AAM和) [!DNL Target]</li><li>[!DNL RTCDP] （高級或最終） [!DNL Target]</li><li>[!DNL RTCDP] （任何SKU）, [!DNL AAM], [!DNL Target]</li></ul>**使用案例**:<ul><li>下一會話個性化</li></ul> |
| [!DNL Platform Web SDK]或 [!DNL AEP Server-Side API] | **解決方案**:<ul><li>[!DNL RTCDP] （任何SKU）和 [!DNL Target]</li></ul>**用例**:<ul><li>下一會話個性化</li><li>通過邊緣實現同頁個性化</li><li>共用段時強制實施治理</li></ul>**解決方案**:<ul><li>[!DNL RTCDP] （任何SKU）, [!DNL AAM], [!DNL Target]</li></ul>**用例**:<ul><li>下一會話個性化</li><ul><li>[!DNL AAM] 區段</li><li>第3方網段(通過 [!DNL AAM]</li></ul><li>通過邊緣實現同頁個性化</li><ul><li>[!DNL RTCDP] 區段</li><li>共用段時強制實施治理</li></ul> |
| 混合 [!UICONTROL at.js] 和 [!DNL Platform Web SDK] | **解決方案**:<ul><li>[!DNL RTCDP] （任何SKU）和 [!DNL Target]</li></ul>**用例**:<ul><li>下一會話個性化</li><ul><li>對於具有 [!UICONTROL at.js]</li></ul><li>同頁個性化</li><ul><li>對於具有 [!DNL Platform Web SDK]</li></ul></ul>**解決方案**:<ul><li>[!DNL RTCDP] （任何SKU）, [!DNL AAM], [!DNL Target]</li></ul>**用例**:<ul><li>下一會話個性化</li><ul><li>對於具有 [!UICONTROL at.js]</li><li>[!DNL AAM] 區段</li><li>第3方網段(通過 [!DNL AAM]</li></ul> |

#### 段評估時間

下表顯示了來自不同實施方案的事件的段評估時間：

| 藍本 | 邊緣段（毫秒計算） | 流段（分鐘評估） | 批處理段評估 |
| --- | --- | --- | --- |
| 事件/資料來自 [!DNL Adobe Experience Platform] SDK | 是 | 是 | 不適用 |
| 事件來源 [!UICONTROL at.js] | 無 | 是 | 不適用 |
| 事件來源 [!DNL Target Mobile] SDK | 無 | 是 | 不適用 |
| 批處理上載中的事件 | 無 | 無 | 是 |
| 離線資料（流）中的事件 | 無 | 是 | 是 |

### 視頻：通過即時CDP和 [!DNL Adobe Target]{#RTCDP}

瞭解如何在下一次點擊時個性化 [!DNL Real-time Customer Data Platform] 和 [!DNL Adobe Target]。 的 [!DNL Adobe Target] 目標 [!DNL Real-time CDP] 允許您使用 [!DNL Experience Platform] 分部 [!DNL Adobe Target] 用於同一頁面和下一頁個性化，並支援治理和隱私。

有關詳細資訊，請參見 [通過即時CDP和Adobe Target實現下一次的個性化](https://experienceleague.adobe.com/docs/platform-learn/tutorials/experience-cloud/next-hit-personalization.html){target=_blank} *平台Tutorials* 的子菜單。

>[!VIDEO](https://video.tv.adobe.com/v/340091?quality=12&learn=on)

### Adobe Target部落格和視頻：

[[!DNL Adobe] announces Same Page Enhanced Personalization with [!DNL Adobe Target] 和 [!DNL Real-time Customer Data Platform]](https://blog.adobe.com/en/publish/2021/10/05/adobe-announces-same-page-enhanced-personalization-with-adobe-target-real-time-customer-data-platform){target=_blank}

## 培訓視頻：使用受眾 ![教程徽章](/help/main/assets/tutorial.png)

此影片包括關於使用對象的資訊。

* 說明詞語「對象」
* 說明將對象用於最佳化的兩個方式
* 在對象清單中尋找對象
* 將活動鎖定至對象
* 對活動中的被動報表使用對象

>[!VIDEO](https://video.tv.adobe.com/v/17398)
