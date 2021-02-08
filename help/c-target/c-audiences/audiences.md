---
keywords: 對象;對象規則;建立對象;建立對象;鎖定目標對象;報表對象;報表對象;區段;自訂設定檔參數;對象定義;對象清單
description: 瞭解如何使用Adobe Target中的「觀眾」頁面，以及如何檢視包含觀眾詳細資料和使用資訊的「觀眾定義」卡片。
title: 如何使用對象清單？
feature: Audiences
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '911'
ht-degree: 92%

---


# 建立對象{#create-audiences}

Adobe Target 中的受眾會決定將看見已鎖定目標活動中內容和體驗的人。

可使用鎖定目標之處皆可使用對象。鎖定目標活動時，您可以從[!UICONTROL 受眾]清單選取可重複使用的受眾、[建立活動專屬受眾](/help/c-target/creating-activity-only-audience.md)，以及將其鎖定目標，或[合併多個受眾](/help/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)以建立隨選受眾。

您也可以使用 [!DNL Analytics] 收集的對象資料，以用於 [!DNL Adobe Target] 和 [!DNL Experience Cloud] 解決方案中即時鎖定目標和個人化。請參閱&#x200B;*核心服務使用指南*&#x200B;中的[觀眾](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html)。

[!DNL Target] 定義兩種對象:

* **鎖定目標對象:**&#x200B;用於傳送不同內容給不同類型的訪客。
* **報表對象:**&#x200B;用於決定不同類型的訪客如何回應相同內容，以利於您分析測試結果。

   在 [!DNL Target] 中，只有在使用 [!DNL Target] 作為報表來源時，才可設定報表對象。如果您使用 [ Adobe Analytics 作為報表來源](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T)，則必須在 [!DNL Analytics] 內設定報表對象。

## 使用受眾清單

若要存取[!UICONTROL 「對象」]清單，請按一下頂端功能表列中的&#x200B;**[!UICONTROL 「對象」]**:

![受眾清單](assets/audiences_list.png)

[!UICONTROL 「對象」]清單包含您可用於活動中的所有對象。使用[!UICONTROL 「對象」]清單來建立、編輯、刪除、複製或合併 對象。此清單也顯示原本建立對象的來源 ([!DNL Target]、[!DNL Target Classic]、[!DNL Adobe Audience Manager (AAM),]、[!DNL Experience Cloud] 等)。無法重新命名預先定義的對象，例如「新訪客」和「再度訪問的訪客」。

使用原本在 AAM 中建立的對象時，若您參考稍後已在 AAM 中刪除的 Target 活動對象，Target 會對您發出警告。

* 若對象已在 AAM 中刪除，[!UICONTROL 「對象」]清單和對象選擇器中皆會顯示警告圖示。UI 中的工具提示也表示對象已在 AAM 中刪除。
* 若嘗試將多個對象與已刪除的對象合併，或嘗試儲存參考已刪除對象的活動，系統會顯示警告訊息。

您也可以鎖定自訂設定檔參數和 `user.` 參數。新增對象時，按一下「新增規則&#x200B;**[!UICONTROL > >**[!UICONTROL &#x200B;訪客資料&#x200B;]**」，然後選擇您要用來定位活動的參數。]**&#x200B;如果需要的參數並未出現，表示參數尚未由 mbox 觸發。在[!UICONTROL 「自訂參數」]下拉式清單中可取得其他自訂 mbox 參數。

使用搜尋方塊來搜尋您的[!UICONTROL 對象]清單。您可以搜尋對象名稱的任何部分，或您可以將特定字串放在引號內。

您可以依對象名稱或上次修改日期來排序[!UICONTROL 「對象」]清單。若要依名稱排序，請按一下欄標題，然後選擇依遞增或遞減順序來顯示對象。

## 檢視受眾定義 {#section_11B9C4A777E14D36BA1E925021945780}

在 Target UI 各處，您可以在快顯卡上檢視對象定義詳細資料，而不必開啟對象。此功能適用於 Target Standard/Premium 中建立的對象，以及從 Target Classic 匯入或透過 API 建立的對象。

例如，暫留在「對象清單」上的對象，然後按一下「檢視」圖示，即可存取下列對象定義卡:

![活動 > 受眾定義](assets/audience_definition_list.png)

在活動的「概覽」頁面按一下「檢視」圖示，即可存取下列對象定義卡:

![活動 > 受眾定義](assets/audience_definition_list.png)

按一下[!UICONTROL 「對象使用狀況」]標籤，以查看參照該對象的其他活動 (如適用)。這樣可讓您在編輯對象時，避免不慎影響其他活動。資訊包括已上線活動、非使用中的活動、已封存的活動，以及同步活動。此功能適用於所有對象 (資料庫對象和[僅限於此活動的對象](/help/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483))。

如果一個對象結合另一個對象，而合併的對象用來建立活動，則兩個對象的使用狀況資訊會列出新建立的活動。

![](assets/audience_definition_list_usage.png)

下列對象定義卡是屬於從 Adobe Experience Cloud 匯入的對象。在此情況中，對象是從 Adobe Audience Manager (AAM) 匯入。

![受眾定義卡片上的使用情形標籤](assets/audience_definition_mc.png)

這些匯入的對象類型會有下列詳細資料:

| 對象類型 | 詳細資料 |
|--- |--- |
| 行動裝置對象 | 行銷名稱、廠商和型號<br>`matches | does not match` 運算子會出現，而非 `equals | does not equal`<br>![匯入的行動裝置對象](/help/c-target/c-audiences/assets/imported_mobile_audience.png)。 |
| 訪客-行為對象 | **user.categoryAffinity:** `categoryAffinity` 搭配 `FAVORITE` 參數。<br>![匯入的類別相關性&#x200B;](/help/c-target/c-audiences/assets/imported_category_affinity.png)<br>**監控:** 監控服務等於 true。<br>**無監控服務:**&#x200B;監控服務等於 false。<br>![匯入的監控](/help/c-target/c-audiences/assets/imported_monitoring.png) |
| 使用 NOT 運算子的對象 | **單一規則:** Target 會以 `[All Visitor AND [NOT [rule]` 格式顯示對象。單一 NOT 規則搭配 AND 與 `AllVisitor` 來顯示對象。<br>![匯入的 Not 對象](/help/c-target/c-audiences/assets/imported_not_audience.png) |

使用匯入的對象時，請記住下列重點:

* Target Standard/Premium 中不再支援運算式目標對象。
* Target Standard/Premium 不支援一些過時的對象，或已改善運算子，變得更容易使用。因此，定義匯入的對象 (雖然可依定義而運作) 不表示現在同樣可以在 Standard/Premium 中建立。例如，社交對象連同其規則皆可見，但 Target Standard/Premium 不允許建立社交對象。

## 訓練影片: 使用對象  ![教學課程徽章](/help/assets/tutorial.png)

此影片包括關於使用對象的資訊。

* 說明詞語「對象」
* 說明將對象用於最佳化的兩個方式
* 在對象清單中尋找對象
* 將活動鎖定至對象
* 對活動中的被動報表使用對象

>[!VIDEO](https://video.tv.adobe.com/v/17398)
