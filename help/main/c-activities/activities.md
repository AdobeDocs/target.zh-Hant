---
keywords: 活動清單；活動；活動型別；編輯活動；活動動作；活動屬性；活動清單篩選器；活動限制；個人化；個人化
description: 瞭解Adobe中的活動如何 [!DNL Target] 可讓您將內容個人化給特定對象，並測試頁面設計。
title: 如何使用個人化內容並測試頁面設計 [!DNL Target]？
feature: Activities
exl-id: 7e61525d-b2db-44f6-a7c2-df5a8d28eca2
source-git-commit: dba58f591b60ccfa1cdcd27d2704ebf28c40ba10
workflow-type: tm+mt
source-wordcount: '2467'
ht-degree: 45%

---

# 活動

[!DNL Adobe Target] 中的活動可讓您將內容個人化給特定對象，並測試頁面設計。

例如，您可以設計一個活動來測試兩個不同的登陸頁面，其中一個強調夏季女鞋的相關資訊，另一個登陸頁面以一般夏季服飾為主。此活動會決定條件來控制各個登陸頁面何時出現，也會決定量度來判斷哪個頁面較成功。此活動設定在滿足特定條件時 (例如在特定日期之間) 開始或結束，或在核准活動後開始，並於停用時結束。

設計活動時，您應該謹慎規劃。決定活動何時開始及持續時間多長。 然後，列出您的選件並將目標對象指派給每個選件。

## 活動清單 {#section_DE8E2DB30D534962A931EF8BB48240F5}

[!UICONTROL 活動]清單是您開啟 [!DNL Target] 時的預設檢視。您可以從此頁面建立活動，並管理現有活動。

您也可以按一下 [!DNL Target] UI 頂端的[!UICONTROL 活動]標籤，以顯示[!UICONTROL 活動]清單。

![活動清單](/help/main/c-activities/assets/activities-list-new.png)

此 [!UICONTROL 活動] 清單提供所有活動的概覽，可讓您執行各種動作：

| 元素 | 說明 |
|--- |--- |
| 左側導覽邊欄 | 在您儲存或上線活動與失敗的或之間切換 [草稿活動](/help/main/c-activities/edit-activity.md). |
| [!UICONTROL 顯示篩選器] 圖示<P>![顯示篩選器圖示](/help/main/c-activities/assets/show-filters-icon.png) | 若要存取篩選器，請按一下 **[!UICONTROL 顯示篩選器]** 圖示在清單頂端附近。<P>如需詳細資訊，請參閱 [將篩選器套用至活動清單](#filters) 底下。 |
| 搜尋方塊 | 快速尋找活動或減少 [!UICONTROL 活動] 清單。 搜尋依據 [!UICONTROL 名稱]， [!UICONTROL URL]，或 [!UICONTROL ID]. |
| [!UICONTROL 建立活動] | 建立活動. 如需建立各種活動型別的詳細資訊，請參閱： <ul><li>[建立 A/B 測試](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)</li><li>建立[自動分配](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md)活動</li><li>[建立自動鎖定目標活動](/help/main/c-activities/auto-target/create-auto-target.md)</li><li>[建立 Automated Personalization 活動](/help/main/c-activities/t-automated-personalization/create-ap-activity.md)</li><li>[建立體驗鎖定目標活動](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md)</li><li>[建立多變數測試](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md)</li><li>[建立 Recommendations 活動](/help/main/c-recommendations/recommendations.md)</li></ul>如需每種型別的詳細資訊，請參閱 [活動型別](#types) 底下。 |
| [!UICONTROL 建立行動裝置預覽連結]<P>![更多動作功能表](/help/main/c-activities/assets/icon-create-mobile-link.png) | 使用 [行動裝置預覽連結](https://experienceleague.adobe.com/docs/target-dev/developer/mobile-apps/target-mobile-preview.html) 為行動應用程式活動執行簡單的端對端QA。<P>按一下 **更多選項** 圖示（垂直省略符號），選取 **建立行動裝置預覽連結**，然後選擇要在mobile上測試的活動。 |
| 自訂表格<P>![自訂表格圖示](/help/main/c-activities/assets/icon-customize-table.png) | 變更哪些欄會顯示在 [!UICONTROL 活動] 按一下 **[!UICONTROL 自訂表格]** 圖示加以選取，然後選取或取消選取所需的欄。<P>變更會套用至您的帳戶，並在您登出後仍會保持作用中 [!DNL Target]. |
| 大量作業核取方塊 | 針對所有活動或選取的活動執行大量作業。<P>如需可用動作的清單（視您的許可權和活動狀態而定），請參閱 [執行快速動作](#quick-actions) 底下。 |
| [!UICONTROL 類型] | 活動型別。 此 [!UICONTROL 型別] 欄可讓您依型別快速識別每個活動。 <ul><li>ab-M：手動 [!UICONTROL A/B測試]</li><li>AB-AA： [!UICONTROL 自動分配]</li><li>AB-AT： [!UICONTROL 自動鎖定目標]</li><li>AP： [!UICONTROL Automated Personalization]</li><li>XT： [!UICONTROL 體驗鎖定]</li><li>MVT： [!UICONTROL 多變數測試]</li><li>記錄： [!UICONTROL Recommendations]</li></ul>如需每種型別的詳細資訊，請參閱 [活動型別](#types) 底下。 |
| [!UICONTROL 名稱] | 活動名稱。按一下活動名稱以顯示該活動的 [!UICONTROL 概觀] 頁面。 <P>按一下 **[!UICONTROL 快速資訊]** 圖示加以存取，即可在快顯示卡片中檢視該活動的詳細資訊。<p>按一下 **[!UICONTROL 更多動作]** 圖示（水準省略符號）來開啟功能表，讓您對活動執行快速動作。 下列動作可供使用（視您的許可權和活動狀態而定）： [!UICONTROL 編輯]， [!UICONTROL 啟動]， [!UICONTROL 停用]， [!UICONTROL 複製]， [!UICONTROL 刪除]、和 [!UICONTROL 封存]. 如需每個動作的詳細資訊，請參閱 [執行快速動作](#quick-actions) 底下。<P>按一下表格標題，依名稱的字母遞增或遞減順序排序清單。 |
| [!UICONTROL 狀態 ] | 活動可能有下列其中一種狀態:<ul><li>**已上線**: 活動目前執行中。</li><li>**草稿**：活動設定已開始，但活動仍在中 [草稿模式](/help/main/c-activities/edit-activity.md) 而且尚未準備好執行。</li><li>**已排程**: 活動已準備好在指定的開始日期和時間啟動。</li><li>**非使用中**: 活動已暫停或停用。</li><li>**同步中**[!DNL Target]: 活動已儲存且正在同步至 傳送網路。</li><li>**已結束**：已達活動的指定結束日期和時間，且已停止提供該活動。</li><li>**已封存**: 活動已封存。您可以啟動已封存的活動以再次使用。</li></ul>**注意:**[!DNL Target] 執行特定動作時，例如在 UI 外部使用 API 方法來啟動活動，更新最多可能需要 10 分鐘才會傳播至 UI。[!DNL Target] |
| [!UICONTROL 最近更新] | 活動上次更新的日期與時間，以及由誰更新。<P>按一下表格標題，依日期以遞增或遞減順序排序清單。 |
| [!UICONTROL 優先順序] | 活動的優先順序。<P>如果將多個活動指派至具有相同對象的相同位置，則會使用優先順序。如果將兩個以上活動指派至位置，則會顯示具有最高優先順序的活動。<P>根據您的 [設定](/help/main/administrating-target/reporting.md)，則 [!DNL Target] 的UI和選項 [!UICONTROL 優先順序] 視情況而定。 您可以使用低、中或高的舊版設定，或是您可以從 0 到 999 啟用微調優先順序。 |
| [!UICONTROL 屬性] | 顯示活動的[屬性](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)。<P>企業使用者許可權為 [Target Premium](/help/main/c-intro/intro.md#premium) 功能。 |
| [!UICONTROL 預估收入成長] | 如果 100% 的對象皆看到勝出體驗，則顯示預測收入增加。<P>使用下列公式計算:<P>`(<winning experience> - <control experience>)*<total number of visitors>`<P>如果縮短格式在小數前只有一位數，此數字會四捨五入到最多一位小數。例如: $1.6M、$60K、$900、$8.5K、$205K<P>如果活動沒有足夠資料來召開冠軍賽，或沒有成本預估，此欄會顯示 &quot;---&quot;。<P>請參閱[預估收入中的提升度](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md)以取得詳細資訊。 |
| [!UICONTROL 來源] | 顯示活動的建立位置： [!DNL Adobe Target]， [ADOBE TARGET API](https://experienceleague.adobe.com/docs/target-dev/developer/overview.html)， [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html)， [Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-cloud-service.html)，或 [Adobe行動服務](https://developer.adobe.com/client-sdks/documentation/). |
| [!UICONTROL 位置] | 活動的 URL 可識別活動出現的位置。此欄可協助您快速識別活動，並判斷特定頁面上是否已有活動在執行。<P>如果活動在多個URL上執行，則連結會顯示還有使用多少個URL。 按一下連結以檢視該活動的完整 URL 清單。<P>您可以依據 URL 來排序或搜尋。使用搜尋方塊旁的下拉式清單，然後選取 [!UICONTROL URL]. |
| 作者 | 建立活動的使用者名稱。 |
| [!UICONTROL 決策方法] | 每個活動中使用的決策方法： [伺服器端](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/on-device-decisioning/overview.html) 或 [使用者端](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/on-device-decisioning/on-device-decisioning.html). |

## 活動類型 {#types}

[!DNL Target] 包含數種活動型別。 下表提供每種活動類型的概覽，以及可協助您深入瞭解的連結。為協助您更完善地選擇適用於您的用途的最佳活動類型，我們也建立了 [Adobe Target 活動指南](/help/main/c-activities/target-activities-guide.md)。

| 活動類型 | 說明 |
|--- |--- |
| [A/B 測試](/help/main/c-activities/t-test-ab/test-ab.md) | A/B測試會比較兩個或更多版本的網站內容，以檢視哪個版本在預先指定的測試期間最能改善您的轉換。 |
| [自動分配](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | [!UICONTROL 自動分配]（一種A/B測試），會從兩個或多個體驗中識別獲勝者，並自動重新分配更多流量給獲勝者以增加轉換，同時測試會繼續執行和學習。 |
| [自動鎖定目標](/help/main/c-activities/auto-target/auto-target-to-optimize.md)<P>![Target Premium](/help/main/assets/premium.png) | 自動鎖定目標是一種A/B測試，可運用進階機器學習來識別多個市場行銷人員定義的高成效體驗，並根據個別客戶設定檔與具有類似設定檔之先前訪客的行為，提供針對每位訪客量身打造的最佳體驗，以便個人化內容並促進轉換。 |
| [多變數測試](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) | [!UICONTROL Multivariate Testing] (MVT)會比較頁面上元素中選件的組合，以判斷哪個組合對特定對象執行時效果最佳，並識別哪個元素最能影響活動的成功。 |
| [體驗鎖定目標](/help/main/c-activities/t-experience-target/experience-target.md) | [!UICONTROL Experience Targeting] (XT) 會根據一組行銷人員定義的規則和條件將內容提供給特定對象。 |
| [自動個人化](/help/main/c-activities/t-automated-personalization/automated-personalization.md)<P>![Target Premium](/help/main/assets/premium.png) | [!UICONTROL Automated Personalization] (AP)結合選件或訊息，並使用進階機器學習來根據訪客的個別客戶設定檔比對每位訪客的不同變數，以便個人化內容並促進轉換。 |
| [Recommendations](/help/main/c-recommendations/recommendations.md)<P>![Target Premium](/help/main/assets/premium.png) | 建議會根據網站訪客在網站上的活動，決定如何向訪客建議產品。<P>例如，您可能鼓勵買背包的人考慮買登山鞋和登山杖。您可以利用「購買了此項目、也購買了其他項目的使用者」演算法建立建議，以顯示通常一起購買的商品。或者，您可能想要使用「瀏覽過此專案、也瀏覽了其他專案的使用者」演演算法，將類似的影片推薦給正在觀看的影片，以鼓勵訪客將更多時間花在您的媒體網站上。<P>**注意**：您也可以在內包含建議 [!UICONTROL A/B測試]， [!UICONTROL 自動分配]， [!UICONTROL 自動鎖定目標]、和 [!UICONTROL 體驗鎖定] (XT)活動。 如需詳細資訊，請參閱 [Recommendations 作為選件](/help/main/c-recommendations/recommendations-as-an-offer.md)。若要使用此功能，您必須具備 [Target Premium 授權](/help/main/c-intro/intro.md#premium)。 |

## 將篩選器套用至活動清單 {#filters}

若要存取篩選器，請按一下 **[!UICONTROL 顯示篩選器]** 圖示在清單頂端附近。

![篩選器選項](/help/main/c-activities/assets/show-filters-options.png)

功能表可讓您依下列屬性篩選活動： |屬性|詳細資料| | — | — | |[!UICONTROL 型別]|篩選依據 [活動型別](#types).| |[!UICONTROL 狀態]|依活動狀態篩選。| |[!UICONTROL 報表來源]|依報表來源篩選。<ul><li>[Analytics](/help/main/c-integrating-target-with-mac/a4t/a4t.md)：顯示使用的活動 [!UICONTROL 目標分析] (A4T)做為報表來源。</li><li>[Target](/help/main/c-reports/reports.md)：顯示使用的活動 [!DNL Target] 作為報表來源。</li></ul>| |[!UICONTROL 體驗撰寫器]|篩選在活動建立期間使用體驗撰寫器的條件：<ul><li>[視覺](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md)：顯示使用建立的活動 [!UICONTROL 視覺化體驗撰寫器] (VEC)。</li><li>[表單式](/help/main/c-experiences/form-experience-composer.md)：顯示使用建立的活動 [!UICONTROL 表單式體驗撰寫器].</li></ul>| |[!UICONTROL 量度型別]|篩選依據 [成功量度](/help/main/c-activities/r-success-metrics/success-metrics.md) 是在活動建立期間選擇。<ul><li>轉換</li><li>收入</li><li>參與</li></ul>| |[!UICONTROL 決策方法]|依每個活動中使用的決策方法篩選<ul><li>[伺服器端](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/on-device-decisioning/overview.html)：顯示使用伺服器端決策的活動。</li><li>[使用者端](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/on-device-decisioning/on-device-decisioning.html)：顯示使用使用者端決策的活動。</li></ul>| |[!UICONTROL 活動來源]|依用來建立每個活動的活動來源篩選。<ul><li>[!DNL Adobe Target]</li><li>[ADOBE TARGET API](https://experienceleague.adobe.com/docs/target-dev/developer/overview.html)</li><li>[Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html)</li><li>[Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-cloud-service.html)</li><li>[Adobe Mobile 服務](https://developer.adobe.com/client-sdks/documentation/)</li></ul>| |[!UICONTROL 屬性]|篩選依據 [屬性](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) 建立活動的位置。|

## 執行快速動作 {#quick-actions}

按一下 **[!UICONTROL 更多動作]** 圖示（水準省略符號）來開啟功能表，讓您對活動執行快速動作。

![快速動作選項](/help/main/c-activities/assets/quick-actions.png)

下列動作可供使用（視您的許可權和活動狀態而定）：

| 動作 | 說明 |
| --- | --- |
| [!UICONTROL 編輯] | 變更活動。任何活動皆可編輯。<P>如需活動的各種編輯方式的詳細資訊，請參閱[編輯活動或另存為草稿](/help/main/c-activities/edit-activity.md)。 |
| [!UICONTROL 停用] | 停止已上線或排定的活動。已停用的活動可以重新啟動或封存。<P>如果您停用或封存活動，之後又重新啟動活動，若訪客在停用或封存活動前便位於活動中，則重新啟動後會繼續隸屬該活動。在兩個事件之間記錄的任何轉換指標不會歸於該活動。 |
| [!UICONTROL 啟動] | 啟動非使用中活動或準備好要啟動的活動。 |
| [!UICONTROL 封存] | 將活動傳送至封存。依預設，已封存的活動不再出現在 [!UICONTROL 活動] 清單。 將活動清單的篩選條件變更為包含已封存的活動，以看到這些活動。您可以啟動已封存的活動以再次使用。<P>如果您停用或封存活動，之後又重新啟動活動，若訪客在停用或封存活動前便位於活動中，則重新啟動後會繼續隸屬該活動。 在兩個事件之間記錄的任何轉換指標不會歸於該活動。 |
| [!UICONTROL 複製] | 複製活動。任何活動皆可複製。複製活動會以相同名稱建立新活動，後面加上「的複本」。例如，名稱為「瀏覽器選件」的測試會複製為「瀏覽器選件複本」。<P>可視化選件會隨活動一起複製。您可以在複本中放心編輯選件，不會影響原始活動。唯一的例外是「內容/資產」資料夾中儲存的選件和影像。 |
| [!UICONTROL 刪除] | 刪除草稿或活動。<P>**注意**: 已刪除的活動無法復原。除非您確定您不會再需要此活動，否則請使用 [!UICONTROL 封存] 動作。 之後，您可以視需要重新啟用活動。 |

## 考量事項

請注意以下關於 [!UICONTROL 活動] 清單：

* 已封存和結束的活動不會出現在[!UICONTROL 「活動」]清單中。若要檢視這些活動，請使用 [篩選器圖示](#filters) 在清單頂端。
* 當活動最初建立於 [!DNL Target Classic] 已停用或已刪除，將會從中刪除 [!DNL Target Standard/Premium]. 原本於 [!DNL Target Classic] 中建立的活動在刪除後，不會傳送至  中的[!DNL Target Standard/Premium]封存資料夾。封存資料夾功能僅適用於 [!DNL Target Standard/Premium]·￼·中建立的活動。
* [!UICONTROL 自動個人化] (AP)、[!UICONTROL 自動分配]和[!UICONTROL 自動鎖定目標]以外的所有活動類型皆可讓您選擇使用 [!DNL Target] 或 [!DNL Adobe Analytics] 作為資料來源。[!UICONTROL AP]、[!UICONTROL 自動分配]和[!UICONTROL 自動鎖定目標] *一律*&#x200B;使用 [!DNL Target] 資料。
* 活動可供許多通路使用:

   * Web 和行動版網站
   * 連上網際網路的螢幕和裝置，包括資訊站和 ATM。
   * 電子郵件和其他取得通路或夥伴網站
   * 行動應用程式
   * 任何其他可傳送標記內容的地方

## 限制 {#section_049D4684403A4E07B998067EB8E9BE56}

每個 Target 活動皆有下列內容限制:

| 項目 | 限制 |
|--- |--- |
| 唯一的選取器 | 300  如果一個選取器在不同體驗中重複，則計算一次。但如果在相同體驗中重複，則再算一次。 |
| 每個體驗中的選件 | 350 |
| 量度中的點擊追蹤選取器 | 50 |
| 量度中的 Mbox | 50 |
| 對象和位置 | 50 對象和位置(mbox)組合不得超過50個。 |

如果您超過任何這些上限，則無法儲存活動。

增加活動中的這些專案數，也會增加同步化活動所需的時間長度 [!DNL Target].

針對V的其他限制[!UICONTROL 視覺體驗撰寫器] VEC，請參閱 [視覺化體驗撰寫器限制](/help/main/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#section_F33C2EA27F2E417AA036BC199DD6C721).

## 屬性已匯入至 [!DNL Target] 針對在外部更新的活動 [!DNL Target] {#section_802B0D174E6A44E1A96F404CA81AAE44}

如果在中建立的活動 [!DNL Target] 從外部更新 [!DNL Target] （例如，透過API），下列活動屬性會匯入回 [!DNL Target]： `thirdpartyId`， `startDate`， `endDate`， `status`， `priority`、和 `marketingCloudMetadata(remoteModifiedBy)`.

此匯入工作會在活動頁面開啟時執行，最多延遲10分鐘。

## 培訓影片 {#section_BE80D13A2E81460C885F902010E1AD87}

以下影片包含本文章探討之概念的詳細資訊。

### 活動類型 (9:03)

此影片說明 [!DNL Target Standard/Premium] 中的可用活動類型。

* 說明 [!DNL Adobe Target] 中包括的活動類型
* 選取達成目標的適當活動類型
* 說明適用所有活動類型的三個步驟引導工作流程

>[!VIDEO](https://video.tv.adobe.com/v/17386)

