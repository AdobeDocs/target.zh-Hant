---
keywords: 活動清單；活動；活動類型；編輯活動；活動動作；活動屬性；活動清單篩選器；活動限制；個人化；個人化
description: 了解活動在Adobe中的方式 [!DNL Target] 可讓您將內容個人化至特定對象，並測試頁面設計
title: 如何使用Target個人化內容及測試頁面設計？
feature: Activities
exl-id: 7e61525d-b2db-44f6-a7c2-df5a8d28eca2
source-git-commit: 2fc704a1779414a370ffd00ef5442fce36e7a5dd
workflow-type: tm+mt
source-wordcount: '2075'
ht-degree: 92%

---

# 活動

[!DNL Adobe Target] 中的活動可讓您將內容個人化給特定對象，並測試頁面設計。

例如，您可以設計一個活動來測試兩個不同的登陸頁面，其中一個強調夏季女鞋的相關資訊，另一個登陸頁面以一般夏季服飾為主。此活動會決定條件來控制各個登陸頁面何時出現，也會決定量度來判斷哪個頁面較成功。此活動設定在滿足特定條件時 (例如在特定日期之間) 開始或結束，或在核准活動後開始，並於停用時結束。

設計活動時，您應該謹慎規劃。決定活動何時開始及持續時間。然後，列出您的選件並將目標對象指派給每個選件。

## 活動類型

Target 包含數種活動類型。下表提供每種活動類型的概覽，以及可協助您深入瞭解的連結。為協助您更完善地選擇適用於您的用途的最佳活動類型，我們也建立了 [Adobe Target 活動指南](/help/main/c-activities/target-activities-guide.md)。

| 活動類型 | 說明 |
|--- |--- |
| [A/B 測試](/help/main/c-activities/t-test-ab/test-ab.md) | A/B 測試會比較兩個或更多版本的網站內容，以查看哪個版本在預先指定的測試持續時間最能改善您的轉換。<br>**注意：** 您現在可以[在 A/B 測試活動中包含 Recommendations](/help/main/c-recommendations/recommendations-as-an-offer.md)。若要使用此功能，您必須具備 [Target Premium 授權](/help/main/c-intro/intro.md#premium)。 |
| [自動分配](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | 自動分配會從兩個或多個體驗中識別獲勝者，並自動重新分配更多流量給獲勝者以增加轉換，同時測試會繼續執行和學習。<br>**注意：** 您現在可以[在自動分配活動中包含 Recommendations](/help/main/c-recommendations/recommendations-as-an-offer.md)。若要使用此功能，您必須具備 [Target Premium 授權](/help/main/c-intro/intro.md#premium)。 |
| [自動鎖定目標](/help/main/c-activities/auto-target/auto-target-to-optimize.md)<br>![Target Premium](/help/main/assets/premium.png) | 自動鎖定目標使用進階機器學習來識別多個高效能之市場行銷人員定義的體驗，並根據訪客的個別客戶設定檔與具有類似設定檔之先前訪客的行為，提供每位訪客量身打造的最佳體驗，以便個人化內容並促進轉換。<br>**注意：** 您現在可以[在自動鎖定目標活動中包含 Recommendations](/help/main/c-recommendations/recommendations-as-an-offer.md)。若要使用此功能，您必須具備 [Target Premium 授權](/help/main/c-intro/intro.md#premium)。 |
| [使用 Analytics 資料](/help/main/c-activities/t-test-ab/t-test-create-ab/create-a4t.md) (A4T) | 您可以將活動設為使用 [!DNL Adobe Analytics] 作為報表來源。此活動類型需要您將 [!DNL Adobe Experience Cloud] 帳戶與 [!DNL Analytics] 和 [!DNL Target] 連結在一起。 |
| [多變數測試](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) | 多變數測試 (MVT) 會比較頁面上元素中選件的組合，以判斷哪個組合對特定對象執行時效果最佳，並識別哪個元素最能影響活動的成功。 |
| [體驗鎖定目標](/help/main/c-activities/t-experience-target/experience-target.md) | 體驗鎖定目標 (XT) 會根據一組市場行銷人員定義的規則和條件為特定對象提供內容。<br>**注意：** 您現在可以[在體驗鎖定活動中包含 Recommendations](/help/main/c-recommendations/recommendations-as-an-offer.md)。若要使用此功能，您必須具備 [Target Premium 授權](/help/main/c-intro/intro.md#premium)。 |
| [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md)<br>![Target Premium](/help/main/assets/premium.png) | Automated Personalization (AP) 結合選件或訊息，並使用進階機器學習來根據訪客的個別客戶設定檔比對每位訪客的不同變數，以便個人化內容並促進轉換。 |
| [Recommendations](/help/main/c-recommendations/recommendations.md)<br>![Target Premium](/help/main/assets/premium.png) | 建議會根據網站使用者在網站上的活動，決定如何向使用者建議產品。<br>例如，您可能鼓勵買背包的人考慮買登山鞋和登山杖。您可以利用「購買了此項目、也購買了其他項目的使用者」演算法建立建議，以顯示通常一起購買的商品。或者，您可以鼓勵訪客多花一些時間在您的媒體網站上，並利用「瀏覽過此項目、也瀏覽了其他項目的使用者」演算法，根據他們正在看的影片來建議類似的影片。<br>**附註：** 您現在可以在 A/B 測試 (包括自動分配和自動鎖定目標) 與體驗鎖定 (XT) 活動中加入推薦。請參閱[以選件方式使用 Recommendations](/help/main/c-recommendations/recommendations-as-an-offer.md)。 |

## 活動清單 {#section_DE8E2DB30D534962A931EF8BB48240F5}

[!UICONTROL 活動]清單是您開啟 [!DNL Target] 時的預設檢視。您可以從此頁面建立新活動，並管理現有活動。

您也可以按一下 [!DNL Target] UI 頂端的[!UICONTROL 活動]標籤，以顯示[!UICONTROL 活動]清單。

![活動清單](/help/main/c-activities/assets/activities-list.png)

活動清單提供活動的概覽:

| 元素 | 說明 |
|--- |--- |
| 類型 | 活動類型，例如 A/B 或 MVT。 |
| 名稱 | 活動名稱。 |
| URL | URL 以淡色文字出現在名稱下方。<br>活動的 URL 可識別活動出現的位置。這協助您快速識別活動，並判斷特定頁面上是否已有測試在執行。<br>如果測試在多個 URL 上執行，則連結會顯示還有使用多少個 URL。按一下連結以檢視該活動的完整 URL 清單。<br>您可以依據 URL 來排序或搜尋。從搜尋方塊旁邊的下拉式清單中選擇[!UICONTROL 「搜尋 URL」]。 |
| 狀態 | 活動可能有下列其中一種狀態:<ul><li>**已上線**: 活動目前執行中。</li><li>**草稿**: 活動設定已開始，但活動尚未準備好執行。</li><li>**已排程**: 活動已準備好在指定的開始日期和時間啟動。</li><li>**非使用中**: 活動已暫停或停用。</li><li>**同步中**: 活動已儲存且正在同步至 Target 傳送網路。</li><li>**已結束**: 已達活動的指定結束日期和時間，且已停止提供該活動。</li><li>**已封存**: 活動已封存。您可以啟動已封存的活動以再次使用。</li></ul>**注意:** 執行特定動作時，例如在 UI 外部使用 API 方法來啟動活動，更新最多可能需要 10 分鐘才會傳播至 UI。 |
| 來源 | 顯示活動在何處建立:<ul><li>Adobe Target</li><li>Adobe Target Classic</li><li>Adobe Experience Manager (AEM)</li><li>Adobe Mobile Services (AMS)</li></ul> |
| 符合裝置上決策資格 | 建立符合裝置決策資格的活動後，會在活動的「概觀」頁面中顯示讀取符合裝置決策資格的標籤。<br>此標籤並不表示活動將一律透過裝置上的決策傳送。 只有在at.js 2.5.0+設定為使用裝置上決策時，此活動才會在裝置上執行。 如果at.js 2.5.0+未設定為使用裝置上，則此活動仍會透過由at.js發出的伺服器呼叫傳送。<br>請參閱 [裝置上決策](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/on-device-decisioning/on-device-decisioning.html){target=_blank}. |
| 屬性 | 顯示活動的[屬性](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)。 |
| 預估收入成長 | 如果 100% 的對象皆看到勝出體驗，則顯示預測收入增加。<br>使用下列公式計算:<br>`(<winning experience> - <control experience>)*<total number of visitors>`<br>如果縮短格式在小數前只有一位數，則此數字會四捨五入到最多一位小數。例如: $1.6M、$60K、$900、$8.5K、$205K<br>如果活動沒有足夠資料來召開冠軍賽，或沒有成本預估，此欄會顯示「---」。請參閱<br>[預估收入中的提升度](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md)以取得詳細資訊。 |
| 最近更新 | 活動的上次更新日期及更新者。 |

將滑鼠移至活動上以顯示可用的動作.

![活動清單暫留動作](/help/main/c-activities/assets/activities_list_hover.png)

以下是可用的動作 (視您的權限而定):

| 動作 | 說明 |
| --- | --- |
| 編輯   | 變更活動。任何活動皆可編輯。<br>如需活動的各種編輯方式的詳細資訊，請參閱[編輯活動或另存為草稿](/help/main/c-activities/edit-activity.md)。 |
| 停用 | 停止已上線或排定的活動。已停用的行銷活動可以重新啟動或封存<br>如果您停用或封存活動，之後又重新啟動活動，若訪客在停用或封存活動前便位於活動中，則重新啟動後會繼續參與該活動。在兩個事件之間記錄的任何轉換指標不會歸於該活動。 |
| 啟動 | 啟動非使用中或已就緒的活動。 |
| 封存 | 將活動傳送至封存。依預設，已封存的活動不再出現在「活動」清單中。將活動清單的篩選條件變更為包含已封存的活動，以看到這些活動。您可以啟動已封存的活動以再次使用。<br>如果您停用或封存活動，之後又重新啟動活動，若訪客在停用或封存活動前便位於活動中，則重新啟動後會繼續隸屬該活動。在兩個事件之間記錄的任何轉換指標不會歸於該活動。 |
| 複製 | 複製活動。任何活動皆可複製。複製活動會以相同名稱建立新活動，後面加上「的複本」。例如，名稱為「瀏覽器選件」的測試會複製為「瀏覽器選件複本」。<br>可視化選件會隨活動一起複製。您可以在複本中放心編輯選件，不會影響原始活動。唯一的例外是「內容/資產」資料夾中儲存的選件和影像。 |
| 刪除 | 刪除草稿或活動。<BR>**注意**: 已刪除的活動無法復原。除非您非常確定您不會再需要此活動，否則請使用[!UICONTROL 封存]動作。然後，您可以視需要重新啟用活動。 |

請注意下列關於活動清單的詳細資料:

* 已封存和結束的活動不會出現在[!UICONTROL 「活動」]清單中。若要檢視這些活動，請利用左欄的進階篩選設定來篩選活動。
* 原本於 [!DNL Target Classic] 中建立的活動一旦停用或刪除，就會立即從 [!DNL Target Standard/Premium] 中刪除。原本於 [!DNL Target Classic] 中建立的活動在刪除後，不會傳送至  中的[!DNL Target Standard/Premium]封存資料夾。封存資料夾功能僅適用於 [!DNL Target Standard/Premium]·￼·中建立的活動。
* [!UICONTROL 自動個人化] (AP)、[!UICONTROL 自動分配]和[!UICONTROL 自動鎖定目標]以外的所有活動類型皆可讓您選擇使用 [!DNL Target] 或 [!DNL Adobe Analytics] 作為資料來源。[!UICONTROL AP]、[!UICONTROL 自動分配]和[!UICONTROL 自動鎖定目標] *一律*&#x200B;使用 [!DNL Target] 資料。
* 活動可供許多通路使用:

   * Web 和行動版網站
   * 連上網際網路的螢幕和裝置，包括資訊站和 ATM。
   * 電子郵件和其他取得通路或夥伴網站
   * 行動應用程式
   * 任何其他可傳送標記內容的地方

## 排序和篩選活動清單 {#section_41DAD479FFF740E2BB67BF4825955670}

依預設，清單會依活動的上次修改日期排序，頂端是最新活動。不過，有幾個篩選選項可協助您自訂清單，以顯示您想要看見的活動。

### 搜尋 {#search-heading}

使用搜尋欄位來搜尋符合搜尋條件的活動。

![活動搜尋](/help/main/c-activities/assets/activities_search_new.png)

搜尋欄位包含下拉式功能表，可讓您指定下列其中一個搜尋篩選條件，以縮小搜尋範圍:[!UICONTROL 活動名稱]和 [!UICONTROL URL]。

### 活動清單篩選器

您可以取清單篩選條件，以決定「活動」清單中出現的活動。

![依類型篩選活動](/help/main/c-activities/assets/activities_filters_new.png)

您可以依下列選項來篩選。在每個類別中，如果什麼皆沒選，則預設為「全部」。

| 篩選類別 | 篩選 |
|--- |--- |
| 類型 | A/B 測試: [手動](/help/main/c-activities/t-test-ab/test-ab.md)、[自動分配](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)及[自動鎖定目標](/help/main/c-activities/auto-target/auto-target-to-optimize.md)。<br>[自動個人化](/help/main/c-activities/t-automated-personalization/automated-personalization.md)<br>[體驗鎖定目標](/help/main/c-activities/t-experience-target/experience-target.md)<br>[多變數測試](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)<br>[Recommendations](/help/main/c-recommendations/recommendations.md) |
| 狀態  | 已上線<br>草稿<br>已排程<br>非使用中<br>同步中<br>已結束<br>已封存 |
| 符合裝置上決策資格 | 是<br>否 |
| 報表來源 | Target<br>Analytics |
| 體驗撰寫器 | 視覺<br>表單式 |
| 量度類型 | 轉換<br>收入<br>參與 |
| 活動來源 | Adobe Target<br>Adobe Target Classic<br>Adobe Experience Manager<br>Adobe Mobile Services |

### 依活動屬性排序

按下列其中一個標題，將活動切換為根據所選標題以遞增或遞減順序列出。

* 類型
* 名稱

![活動清單遞增順序](/help/main/c-activities/assets/activities_list_ascending.png)

![停用今日秘訣](/help/main/c-activities/assets/tip-disable-new.png)

## 限制 {#section_049D4684403A4E07B998067EB8E9BE56}

每個 Target 活動皆有下列內容限制:

| 項目 | 限制 |
|--- |--- |
| 唯一的選取器 | 300  如果一個選取器在不同體驗中重複，則計算一次。但如果在相同體驗中重複，則再算一次。 |
| 每個體驗中的選件 | 350 |
| 量度中的點擊追蹤選取器 | 50 |
| 量度中的 Mbox | 50 |
| 對象和位置 | 50 對象和位置 (Mbox) 組合不得超過 50 個。 |

如果您超過任何這些上限，則無法儲存活動。

在活動中增加這些項目的數目也會造成活動在 Target 內同步化的時間更久。

關於可視化體驗撰寫器的其他限制，請參閱[可視化體驗撰寫器限制](/help/main/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#section_F33C2EA27F2E417AA036BC199DD6C721)。

## 導入到的屬性 [!DNL Target] 針對在 [!DNL Target] {#section_802B0D174E6A44E1A96F404CA81AAE44}

如果從 [!DNL Target] 外部 (例如，透過 Adobe I/O) 更新在 [!DNL Target] 中建立的活動，則會將下列活動屬性匯入回 [!DNL Target]:

`thirdpartyId`

`startDate`

`endDate`

`status`

`priority`

`marketingCloudMetadata(remoteModifiedBy)`

此匯入工作將在活動頁面開啟時執行，最多延遲十分鐘。(KB-1526)

## 培訓影片 {#section_BE80D13A2E81460C885F902010E1AD87}

以下影片含有本文章探討之概念的詳細資訊。

### 活動類型 (9:03)![Overview badge](/help/main/assets/overview.png)

此影片說明 [!DNL Target Standard/Premium] 中的可用活動類型。

* 說明 [!DNL Adobe Target] 中包括的活動類型
* 選取達成目標的適當活動類型
* 說明適用所有活動類型的三個步驟引導工作流程

>[!VIDEO](https://video.tv.adobe.com/v/17386)

