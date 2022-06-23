---
keywords: 實現；javascript library;js;atjs；設備上決策；設備上決策；at.js；設備上；設備上
description: 瞭解如何使用at.js庫執行設備上決策
title: 設備上決策如何與at.js JavaScript庫一起使用？
feature: at.js
role: Developer
exl-id: 5ad6032b-9865-4c80-8800-705673657286
source-git-commit: b1e8ea2370fc15f4bfcd960ab2960cafe2db92b8
workflow-type: tm+mt
source-wordcount: '3546'
ht-degree: 7%

---

# at.js的設備上確定

從2.5.0版開始， at.js提供設備上的決策。 設備上決策允許您快取 [A/BTest](/help/main/c-activities/t-test-ab/test-ab.md) 和 [體驗目標](/help/main/c-activities/t-experience-target/experience-target.md) (XT)瀏覽器上的活動，以執行記憶體中的決定，而無需向 [!DNL Adobe Target] 邊緣網路。

[!DNL Target] 此外，還通過即時伺服器呼叫，提供從您的實驗和機器學習驅動（ML驅動）個性化活動中提供最相關和最新體驗的靈活性。 換句話說，當效能最重要時，您可以選擇使用設備上的決策。 但是，當需要最相關、最新和ML驅動的體驗時，可以調用伺服器。

## 設備上決策的好處是什麼？

設備上決策的好處包括：

* **提供超快的決策和體驗。** 在記憶體中和瀏覽器上執行分段和決策以避免阻塞網路請求。
* **增強應用程式效能。** 運行實驗，為您的客戶和用戶提供個性化服務，而不影響最終用戶體驗。
* **提高Google網站質量分數。** 通過在記憶體中進行決策，提高您線上業務的Google站點質量分數，使消費者更容易發現。
* **從即時分析學習。** 通過 [目標分析](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T)報告。 A4T允許您在關鍵時刻將策略透視。

## 支援的功能

Adobe TargetJS SDK使客戶能夠靈活地在決策資料的效能和新鮮度之間做出選擇。 換句話說，如果通過機器學習交付最相關和最吸引人的個性化內容對您來說最為重要，則應進行即時伺服器呼叫。 但是，當效能更為關鍵時，應該做出設備內和記憶體內決策。 要確定設備上的功能，請參閱支援的功能清單：

* 活動類型
* 目標受眾
* 分配方法

有關詳細資訊，請參見 [支援的設備上決策功能](https://developer.adobe.com/target/implement/client-side/atjs/on-device-decisioning/supported-features/)。

## 設備上的決策如何工作？

在啟用設備上決策時部署和初始化at.js時， [規則對象](https://developer.adobe.com/target/implement/client-side/atjs/on-device-decisioning/rule-artifact/) 包括您對A/B和XT活動、受眾和資產的設備上決策，可從您訪問者最近的Akamai CDN下載，並在訪問者瀏覽器上本地快取。 當從at.js請求檢索經驗時，基於在快取的規則對象中編碼的元資料，在記憶體中做出關於要返回哪些經驗的決定。

## 判定方法

在設備上進行決策， [!DNL Target] 引入了新的設定 [!UICONTROL 決策方法]。 的 [!UICONTROL 決策方法] 設定將指示at.js如何提供您的體驗。 [!UICONTROL 決策方法] 有三個值：

* [!UICONTROL 僅伺服器端]
* [!UICONTROL 僅限設備上]
* [!UICONTROL 混合]

### 僅伺服器端

[!UICONTROL 僅伺服器端] 是當在Web屬性上實現和部署at.js 2.5.0+時從框中設定的預設決策方法。

使用 [!UICONTROL 僅伺服器端] 預設配置表示對 [!DNL Target] 邊緣網路，涉及阻塞伺服器呼叫。 此方法可以引入增量延遲，但也提供了顯著的優勢，例如讓您能夠應用Target的機器學習功能，包括 [Recommendations](/help/main/c-recommendations/recommendations.md)。 [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) （美聯社） [自動目標](/help/main/c-activities/auto-target/auto-target-to-optimize.md) 活動。

此外，使用Target的用戶配置檔案增強您的個性化體驗，可為您的業務提供強大的結果。

最後， [!UICONTROL 僅伺服器端] 讓您使用Adobe Experience Cloud和通過Audience Manager和Adobe Analytics段可以針對的微調觀眾。

下圖說明了訪問者、瀏覽器at.js 2.5.0+和Adobe Target邊緣網路之間的交互。 此流程圖可捕獲新訪問者和返回訪問者。

![僅伺服器端流程圖](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/server-side-only.png)

以下清單與圖中的數字相對應：

| 步驟 | 說明 |
| --- | --- |
| 1 | 的 [!DNL Experience Cloud Visitor ID] 從 [Adobe Experience Cloud身份服務](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=en)。 |
| 2 | at.js 程式庫會同步載入並隱藏文件本文。<br>   還可以非同步載入at.js庫，並在頁面上實現一個可選的預隱藏代碼段。 |
| 3 | at.js庫隱藏主體以防止閃爍。 |
| 4 | 發出包含所有已配置參數（如ECID、客戶ID、自定義參數、用戶配置檔案等）的頁面載入請求。 |
| 5 | 個人資料指令碼執行，然後注入個人資料存放區。<br>配置檔案儲存從受眾庫請求合格的受眾(例如，從 [!DNL Adobe Analytics]。 [!DNL Adobe Audience Manager]等等。<br>客戶屬性會透過批次程序傳送至個人資料存放區。 |
| 6 | 配置檔案儲存用於觀眾資格和分段篩選活動。 |
| 7 | 在從現場確定體驗後選擇所得內容 [!DNL Target] 活動。 |
| 8 | at.js庫隱藏頁面上與必須呈現的體驗相關聯的相應元素。 |
| 9 | at.js庫顯示正文，以便可以載入頁面的其餘部分供訪問者查看。 |
| 10 | at.js庫操作DOM以從目標邊緣網路呈現體驗。 |
| 11 | 參觀者會體驗到這種體驗。 |
| 12 | 載入整個網頁。 |
| 13 | [!DNL Analytics] 資料傳送至「資料收集」伺服器。 |
| 14 | 目標資料與 [!DNL Analytics] 通過SDID處理資料，並 [!DNL Analytics] 報告儲存。 然後就可以在 [!DNL Analytics] 與 [!DNL Analytics] 中，透過 [!DNL Target] for Target[!UICONTROL  (A4T) 報表來檢視 ]Analytics 資料。 |

### 僅限設備上

[!UICONTROL 僅限設備上] 是必須在at.js 2.5.0+中設定的決策方法，當設備上的決策只應在整個網頁中使用時。

設備上決策可以以超快的速度提供您的體驗和個性化活動，因為決策來自快取的規則項目，其中包含符合設備上決策資格的所有活動。

要瞭解哪些活動符合設備上決策的條件，請參閱 [設備上決策支援的功能](https://developer.adobe.com/target/implement/client-side/atjs/on-device-decisioning/supported-features/)。

僅當效能在所有需要決策的頁面中都非常關鍵時，才應使用此決策方法 [!DNL Target]。 此外，請記住，當選擇此判定方法時， [!DNL Target] 不符合設備上決策資格的活動將不會交付或執行。 at.js庫2.5.0+配置為僅查找快取的規則項目以做出決策。

下圖說明了訪問者、瀏覽器at.js 2.5.0+和Akamai CDN之間的交互。 Akamai CDN快取訪問者首次訪問的規則項目。 對於新訪問者的首次頁面訪問，必須從Akamai CDN下載JSON規則項目，以便在訪問者瀏覽器上本地快取。 下載JSON規則項目後，立即做出該決定，而不會進行阻塞網路調用。 下面的流程圖將捕獲新的訪問者。

![僅限設備上的流程圖](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-only.png)

以下清單與圖中的數字相對應：

>[!NOTE]
>
>[!DNL Adobe Target] 管理伺服器將符合設備上決策條件的所有活動都限定為合格，生成JSON規則項目，並將其傳播到Akamai CDN。 您的活動會持續受到監視，以便更新以輸出要傳播到Akamai CDN的新JSON規則項目。

| 步驟 | 說明 |
| --- | --- |
| 1 | 的 [!DNL Experience Cloud Visitor ID] 從 [Adobe Experience Cloud身份服務](https://experienceleague.adobe.com/docs/id-service/using/home.html)。 |
| 2 | at.js 程式庫會同步載入並隱藏文件本文。<br>還可以非同步載入at.js庫，並在頁面上實現一個可選的預隱藏代碼段。 |
| 3 | at.js庫隱藏主體以防止閃爍。 |
| 4 | at.js庫請求從訪問者最近的Akamai CDN檢索JSON規則項目。 |
| 5 | Akamai CDN使用JSON規則項目響應。 |
| 6 | JSON規則項目在訪問者瀏覽器上本地快取。 |
| 7 | at.js庫解釋JSON規則項目並執行檢索體驗和隱藏已測試元素的決定。 |
| 8 | at.js庫顯示正文，以便可以載入頁面的其餘部分供訪問者查看。 |
| 9 | at.js庫操作DOM以從快取的JSON規則對象中呈現體驗。 |
| 10 | 參觀者會體驗到這種體驗。 |
| 11 | 載入整個網頁。 |
| 12 | [!DNL Analytics] 資料傳送至「資料收集」伺服器。目標資料與 [!DNL Analytics] 通過SDID處理資料，並 [!DNL Analytics] 報告儲存。 然後就可以在 與 中，透過 for Target (A4T) 報表來檢視 [!DNL Analytics][!DNL Analytics]Analytics 資料。[!DNL Target] |

下圖說明了訪問者、瀏覽器at.js 2.5.0+和訪問者後續頁面點擊或返回訪問時快取的JSON規則對象之間的交互。 由於JSON規則項目已快取，並且在瀏覽器上可用，因此立即做出決定，而無需阻塞網路調用。 此流程圖可捕獲後續頁面導航或返回訪問者。

![用於後續頁面導航和重複訪問的僅設備上流程圖](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-only-subsequent.png)

以下清單與圖中的數字相對應：

>[!NOTE]
>
>[!DNL Adobe Target] 管理伺服器將符合設備上決策條件的所有活動都限定為合格，生成JSON規則項目，並將其傳播到Akamai CDN。 您的活動會持續受到監視，以便更新以輸出要傳播到Akamai CDN的新JSON規則項目。

| 步驟 | 說明 |
| --- | --- |
| 1 | 的 [!DNL Experience Cloud Visitor ID] 從 [Adobe Experience Cloud身份服務](https://experienceleague.adobe.com/docs/id-service/using/home.html)。 |
| 2 | at.js 程式庫會同步載入並隱藏文件本文。<br>還可以非同步載入at.js庫，並在頁面上實現一個可選的預隱藏代碼段。 |
| 3 | at.js庫隱藏主體以防止閃爍。 |
| 4 | at.js庫解釋JSON規則項目並執行記憶體中的決定以檢索體驗。 |
| 5 | 已測試元素被隱藏。 |
| 6 | at.js庫顯示正文，以便可以載入頁面的其餘部分供訪問者查看。 |
| 7 | at.js庫操作DOM以從快取的JSON規則對象中呈現體驗。 |
| 8 | 參觀者會體驗到這種體驗。 |
| 9 | 載入整個網頁。 |
| 10 | [!DNL Analytics] 資料傳送至「資料收集」伺服器。目標資料與 [!DNL Analytics] 通過SDID處理資料，並 [!DNL Analytics] 報告儲存。 然後就可以在 [!DNL Analytics] 與 [!DNL Analytics] 中，透過 [!DNL Target] for Target[!UICONTROL  (A4T) 報表來檢視 ]Analytics 資料。 |

### 混合

[!UICONTROL 混合] 是在必須同時執行設備上決策和需要對Adobe Target邊緣網路進行網路呼叫的活動時，必須在at.js 2.5.0+中設定的決策方法。

在管理設備上決策活動和伺服器端活動時，在思考如何部署和調配時可能會有些複雜和繁瑣 [!DNL Target] 在你的網頁上。 以混合作為判定方法， [!DNL Target] 知道何時必須為需要伺服器端執行的活動向Adobe Target邊緣網路進行伺服器呼叫，以及何時只執行設備上的決定。

JSON規則項目包括元資料，用於通知at.js框是否具有正在運行的伺服器端活動或設備上的決策活動。 此決策方法可確保您想要快速交付的活動通過設備決策完成，對於需要更強大的ML驅動個性化的活動，這些活動通過Adobe Target邊緣網路完成。

下圖說明了首次訪問您頁面的新訪問者的訪問者、瀏覽器at.js 2.5.0+、Akamai CDN和Adobe Target邊緣網路之間的交互。 從此圖中可以看出，JSON規則項目是通過Adobe Target邊緣網路進行決策時非同步下載的。

此方法確保對象的大小不會對決策的延遲產生負面影響。 同步下載JSON規則項目並隨後做出決策也可能對延遲產生不利影響，並且可能不一致。 因此，混合決策方法是一種最佳實踐推薦，它總是為新訪問者進行伺服器端調用決策，並且當JSON規則項目被並行快取時。 對於任何後續的頁面訪問和回訪，決策都通過JSON規則項目從快取和記憶體中做出。

![第一次訪問者的混合流圖](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/hybrid-first-time-visitor.png)

以下清單與圖中的數字相對應：

>[!NOTE]
>
>[!DNL Adobe Target] 管理伺服器將符合設備上決策條件的所有活動都限定為合格，生成JSON規則項目，並將其傳播到Akamai CDN。 您的活動會持續受到監視，以便更新以輸出要傳播到Akamai CDN的新JSON規則項目。

| 步驟 | 說明 |
| --- | --- |
| 1 | 的 [!DNL Experience Cloud Visitor ID] 從 [Adobe Experience Cloud身份服務](https://experienceleague.adobe.com/docs/id-service/using/home.html)。 |
| 2 | at.js 程式庫會同步載入並隱藏文件本文。<br>還可以非同步載入at.js庫，並在頁面上實現一個可選的預隱藏代碼段。 |
| 3 | at.js庫隱藏主體以防止閃爍。 |
| 4 | 向Adobe Target邊緣網路發出頁面載入請求，包括所有已配置的參數，如（ECID、客戶ID、自定義參數、用戶配置檔案等）。 |
| 5 | 並行地， at.js發出請求，請求從最近的Akamai CDN中檢索JSON規則對象給訪問者。 |
| 6 | (Adobe Target邊緣網路)配置檔案指令碼執行並饋送到配置檔案儲存。 配置檔案儲存從受眾庫請求合格的受眾(例如，從 [!DNL Adobe Analytics]。 [!DNL Adobe Audience Manager]等等。 |
| 7 | Akamai CDN使用JSON規則項目響應。 |
| 8 | 配置檔案儲存用於觀眾資格和分段篩選活動。 |
| 9 | 在從現場確定體驗後選擇所得內容 [!DNL Target] 活動。 |
| 10 | at.js庫隱藏頁面上與必須呈現的體驗相關聯的相應元素。 |
| 11 | at.js庫顯示正文，以便可以載入頁面的其餘部分供訪問者查看。 |
| 12 | at.js庫操作DOM以從目標邊緣網路呈現體驗。 |
| 13 | 參觀者會體驗到這種體驗。 |
| 14 | 載入整個網頁。 |
| 15 | [!DNL Analytics] 資料傳送至「資料收集」伺服器。目標資料與 [!DNL Analytics] 通過SDID處理資料，並 [!DNL Analytics] 報告儲存。 然後就可以在 [!DNL Analytics] 與 [!DNL Analytics] 中，透過 [!DNL Target] for Target[!UICONTROL  (A4T) 報表來檢視 ]Analytics 資料。 |

下圖說明了訪問者、瀏覽器at.js 2.5.0+和快取的JSON規則項目之間的交互，用於後續頁面導航或返回訪問。 在此圖中，只關注為後續頁面導航或返回訪問做出設備上決策的使用情形。 請記住，根據特定頁面的活動，可以進行伺服器端呼叫以執行伺服器端決策。

![用於後續頁面導航和重複訪問的混合流圖](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/hybrid-subsequent.png)

以下清單與圖中的數字相對應：

>[!NOTE]
>
>[!DNL Adobe Target] 管理伺服器將符合設備上決策條件的所有活動都限定為合格，生成JSON規則項目，並將其傳播到Akamai CDN。 您的活動會持續受到監視，以便更新以輸出要傳播到Akamai CDN的新JSON規則項目。

| 步驟 | 說明 |
| --- | --- |
| 1 | 的 [!DNL Experience Cloud Visitor ID] 從 [Adobe Experience Cloud身份服務](https://experienceleague.adobe.com/docs/id-service/using/home.html)。 |
| 2 | at.js 程式庫會同步載入並隱藏文件本文。<br>還可以非同步載入at.js庫，並在頁面上實現一個可選的預隱藏代碼段。 |
| 3 | at.js庫隱藏主體以防止閃爍。 |
| 4 | 請求檢索體驗。 |
| 5 | at.js庫確認已快取JSON規則項目，並執行記憶體中用於檢索體驗的決定。 |
| 6 | 已測試元素被隱藏。 |
| 7 | at.js庫顯示正文，以便可以載入頁面的其餘部分供訪問者查看。 |
| 8 | at.js庫操作DOM以從快取的JSON規則對象中呈現體驗。 |
| 9 | 參觀者會體驗到這種體驗。 |
| 10 | 載入整個網頁。 |
| 11 | [!DNL Analytics] 資料傳送至「資料收集」伺服器。目標資料與 [!DNL Analytics] 通過SDID處理資料，並 [!DNL Analytics] 報告儲存。 然後就可以在 [!DNL Analytics] 與 [!DNL Analytics] 中，透過 [!DNL Target] for Target[!UICONTROL  (A4T) 報表來檢視 ]Analytics 資料。 |

## 如何啟用設備上決策？

設備上決策適用於所有 [!DNL Target] 使用At.js 2.5.0+的客戶。

要啟用設備上決策：

>[!NOTE]
>
>您必須 [!UICONTROL 管理] 或 [!UICONTROL 批准者] [用戶角色](/help/main/administrating-target/c-user-management/user-management.md) 啟用或禁用設備上的「On-Device Desitioning（設備上決定）」切換。

1. 按一下 **[!UICONTROL 管理]** > **[!UICONTROL 實施]** > **[!UICONTROL 帳戶詳細資訊]**。
1. 下 **[!UICONTROL 帳戶詳細資訊]**，滑動 **[!UICONTROL 設備上決策]** 切換到「開啟」位置。

   ![設備上決策切換](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-decisioning-toggle.png)

   「」[!UICONTROL 在項目中包括所有現有的設備上決策合格活動]「 」選項在啟用設備上決策時顯示。
1. （條件）如果希望所有符合設備上決策條件的活動自動包括在對象中，請將切換滑至「開啟」位置。

   關閉此切換意味著必須重新建立並激活任何設備上決策活動，以便將這些活動包括在生成的規則項目中。 換句話說，在開啟 [!UICONTROL 設備上決策] toggle不包括在規則對象中。

啟用 [!UICONTROL 設備上決策] 切換， [!DNL Target] 開始生成和傳播 [規則對象](https://developer.adobe.com/target/implement/client-side/atjs/on-device-decisioning/rule-artifact/) 為你的當事人。

>[!IMPORTANT]
>
>確保在初始化Adobe TargetSDK之前啟用切換，以使用設備上決策。 規則對象首先需要生成並傳播到Akamai CDN，以便設備上的決定工作。 傳播可能需要5到10分鐘，第一個規則項目才能生成並傳播到Akamai CDN。

## 如何配置at.js 2.5.0+以使用設備上的決策？

1. 按一下 **[!UICONTROL 管理]** > **[!UICONTROL 實施]** > **[!UICONTROL 帳戶詳細資訊]**。
1. 下 **[!UICONTROL 實現方法]** > **[!UICONTROL 主要實現方法]**&#x200B;按一下 **[!UICONTROL 編輯]** 位於at.js版本旁邊(必須是at.js 2.5.0或更高版本)。

   ![編輯主實現方法設定](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/main-implementation-method.png)

   >[!IMPORTANT]
   >
   >在更改這些預設設定之前，請咨詢「Client Care（客戶端保護）」，以便不影響當前實施。

1. 選擇所需的決策方法：

   * [!UICONTROL 僅伺服器端]
   * [!UICONTROL 僅限設備上]
   * [!UICONTROL 混合]

   ![編輯at.js設定面板](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/global-settings.png)

### 全局設定

可以配置預設 [!UICONTROL 決策方法] 全部 [!DNL Target] 決定。 各種判定方法 [!UICONTROL 僅伺服器端]。 [!UICONTROL 僅限設備上], [!UICONTROL 混合]。 在目標UI中選擇的判定方法在中配置 `window.targetGlobalSettings` 下 `decisioningMethod` 的子菜單。 瞭解有關 `decisioningMethod` 在 [targetGlobalSettings()](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/)。

```javascript
<head> 
    <script type="text/javascript">

        window.targetGlobalSettings = { 
            clientCode: "yourClientCodeHere", 
            imsOrgId: "imsOrgId@AdobeOrg", 
            decisioningMethod: "on-device"

        }; 
    </script>

    <script type="text/javascript" src="at.js"></script> 
</head>
```

### 自定義設定

如果您設定 `decisioningMethod` 在 `window.targetGlobalSettings`，但是要改寫 `decisioningMethod` 根據您的使用案例，您可以通過指定 `decisioningMethod` 在At.js2.5.0+中 [getOffires()](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-getoffers-atjs-2/) 呼叫。

```javascript
adobe.target.getOffers({ 

  decisioningMethod:"on-device", 
  request: { 
    execute: { 
      mboxes: [ 
        { 
          index: 0, 
          name: "homepage" 
        } 
      ] 
    } 
 } 
});
```

>[!NOTE]
>
>為了在getOffires()調用中將「設備上」或「混合」用作決策方法，請確保全局設定具有 `decisioningMethod` 「在設備上」或「混合」。 at.js庫2.5.0+必須知道是否在載入到頁面後立即下載和快取JSON規則項目。 如果全局設定的判定方法設定為「伺服器端」，並且「設備上」或「混合」判定方法被傳遞到getOffers()調用中，則at.js 2.5.0+將不會快取JSON規則項目以執行設備上的決策。

### 項目快取TTL

[!DNL Target] 表示符合設備上決策資格的活動，該活動由元資料、規則和條件組成。 此項目已快取到Akamai CDN上。 在用戶首次訪問期間，用戶的瀏覽器下載並快取表示設備上決策活動的項目。

在隨後訪問您的站點時，瀏覽器會自動檢查是否必須下載較新版本的項目。 此檢查會增加延遲。 Artifact Cache TTL定義了自上次成功下載以來，您不希望瀏覽器檢查更新的項目的分鐘數。 時間越長，效能越好。 時間幀越短，資料新鮮度越好，但代價是增加了延遲。

## 如何知道某個活動符合設備上決策條件？

建立符合設備上決策條件的活動後，將顯示一個標籤 [!UICONTROL 設備上決策合格]，在活動中可見 [!UICONTROL 概述] 的子菜單。

![活動的「概述」頁上的「設備上決定合格」標籤。](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-decisioning-eligible-label.png)

此標籤並不表示活動將始終通過設備上的決策提供。 僅當at.js 2.5.0+配置為使用設備上決策時，才會在設備上執行此活動。 如果未將at.js 2.5.0+配置為使用設備上，則此活動仍將通過at.js中的伺服器調用傳遞。

您可以篩選符合以下條件的所有設備上決策活動 [!UICONTROL 活動] 頁面 [!UICONTROL 設備上決策合格] 的子菜單。

![「活動」頁上的設備上決策合格篩選器。](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-decisioning-filter.png)

>[!NOTE]
>
>建立並激活符合設備上決策條件的活動後，可能需要5到10分鐘時間，才能將其包含在生成並傳播到Akamai CDN呈現點的規則對象中。

## 確保通過At.js 2.5.0+提供設備上決策活動的步驟摘要？

1. 訪問Adobe TargetUI並導航到 **[!UICONTROL 管理]** > **[!UICONTROL 實施]** > **[!DNL Account Details]** 啟用 **[!UICONTROL 設備上決策]** 切換。
1. 啟用 **&quot;[!UICONTROL 在項目中包括所有現有的設備上決策合格活動]&quot;** 切換。

   第一個JSON規則項目生成最多需要10分鐘。

1. 建立並激活 [設備上決策支援的活動類型](https://developer.adobe.com/target/implement/client-side/atjs/on-device-decisioning/supported-features/)，並驗證其是否符合設備上決策條件。
1. 設定 **[!UICONTROL 決策方法]** 或 **[!UICONTROL &quot;混合&quot;]** 或 **[!UICONTROL &quot;僅設備上&quot;]** 通過at.js設定UI。
1. 將At.js 2.5.0+下載並部署到您的頁面。
