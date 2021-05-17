---
keywords: 實施；javascript library;js;atjs；裝置上決策；裝置上決策；at.js；裝置上；裝置上
description: 瞭解如何使用at.js程式庫執行裝置上決策
title: 裝置上決策如何與at.js JavaScript程式庫搭配運作？
feature: at.js
role: Developer
exl-id: 5ad6032b-9865-4c80-8800-705673657286
source-git-commit: 7f1db24e902c4b06c2035a94924abfe2d254bf25
workflow-type: tm+mt
source-wordcount: '3491'
ht-degree: 7%

---

# at.js的裝置上決策

從2.5.0版開始，at.js提供裝置上決策。 裝置上決策可讓您快取瀏覽器上的[A/B測試](/help/c-activities/t-test-ab/test-ab.md)和[體驗定位](/help/c-activities/t-experience-target/experience-target.md)(XT)活動，以執行記憶體內決策，而不需封鎖網路要求至[!DNL Adobe Target]邊緣網路。

[!DNL Target] 此外，還提供彈性，讓您透過即時伺服器呼叫，從實驗和機器學習驅動（ML驅動）個人化活動中提供最相關和最新的體驗。換言之，當效能最為重要時，您可以選擇使用裝置上的決策。 但是，當需要最相關、最新和ML導向的體驗時，可以改為呼叫伺服器。

## 裝置上決策的優點為何？

裝置上決策的優點包括：

* **提供快如閃電的決策與體驗。** 在記憶體中和瀏覽器上執行分組和決策，以避免封鎖網路要求。
* **增強應用程式效能。** 在不影響使用者體驗的情況下，進行實驗並為客戶和使用者提供個人化服務。
* **改善Google網站品質分數。** 在記憶體中進行決策時，提升線上業務的Google網站品質分數，讓消費者更容易發現。
* **從即時分析中學習。** 透過Analytics for Target [](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T)報告即時從您的活動效能獲得見解。A4T可讓您在關鍵時刻轉換策略。

## 支援的功能

Adobe TargetJS SDK讓客戶在決策時可選擇效能與新鮮的資料。 換言之，如果透過機器學習提供最相關、最吸引人的個人化內容對您而言最為重要，則應進行即時伺服器呼叫。 但是，當效能更為關鍵時，應該做出設備內和記憶體內決策。 若要在裝置上進行決策，請參閱支援的功能清單：

* 活動類型
* 目標受眾
* 分配方法

如需詳細資訊，請參閱[支援的裝置上決策功能](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/supported-features.md)。

## 裝置上的決策如何運作？

當您在啟用裝置上決策的情況下部署和初始化at.js時，會從離您訪客最近的Akamai CDN下載[規則物件](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/rule-artifact.md)，其中包含您對A/B和XT活動、觀眾和資產的裝置上決策，並快取至訪客的本機瀏覽器。 當從at.js提出擷取體驗的請求時，會根據快取規則物件中編碼的中繼資料，在記憶體中決定要傳回哪些體驗。

## 決策方法

在裝置上進行決策時，[!DNL Target]引入了稱為[!UICONTROL 決策方法]的新設定。 [!UICONTROL 決策方法]設定指定at.js如何提供您的體驗。 [!UICONTROL 決策方] 法有三個值：

* [!UICONTROL 僅限伺服器端]
* [!UICONTROL 僅限裝置上]
* [!UICONTROL 混合]

### 僅限伺服器端

[!UICONTROL 伺服器] 端僅是預設的決策方法，當at.js 2.5.0+實作並部署在您的Web屬性上時，就會立即設定。

使用[!UICONTROL 伺服器端僅]做為預設組態，表示所有決策都在[!DNL Target]邊緣網路上做出，這涉及封鎖伺服器呼叫。 此方法可引入遞增延遲，但也提供顯著的優點，例如可讓您套用Target的機器學習功能，包括[Recommendations](/help/c-recommendations/recommendations.md)、[Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md)(AP)和[自動目標](/help/c-activities/auto-target/auto-target-to-optimize.md)活動。

此外，使用Target的使用者個人檔案（跨作業和通道持續提供）來強化您的個人化體驗，可為您的業務提供強大的成果。

最後，[!UICONTROL 伺服器端僅]可讓您使用Adobe Experience Cloud並微調可透過Audience Manager和Adobe Analytics區段針對的對象。

下圖說明您的訪客、瀏覽器、at.js 2.5.0+和Adobe Target邊緣網路之間的互動。 此流程圖會擷取新訪客和舊訪客。

![僅限伺服器端的流程圖](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/server-side-only.png)

以下清單與圖中的數字相對應：

| 步驟 | 說明 |
| --- | --- |
| 1 | 從[Adobe Experience Cloud身份服務](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=en)檢索[!DNL Experience Cloud Visitor ID]。 |
| 2 | at.js 程式庫會同步載入並隱藏文件本文。<br>   您也可以以非同步方式載入at.js程式庫，並在頁面上建置選擇性的預先隱藏程式碼片段。 |
| 3 | at.js程式庫會隱藏主體，以防止閃爍。 |
| 4 | 會提出包含所有已設定參數的頁面載入請求，例如（ECID、客戶ID、自訂參數、使用者設定檔等）。 |
| 5 | 設定檔指令碼執行，然後注入設定檔存放區。<br>「描述檔商店」會要求觀眾程式庫中的合格觀眾(例如，從 [!DNL Adobe Analytics]、 [!DNL Adobe Audience Manager]等共用的觀眾)。<br>客戶屬性會透過批次程序傳送至設定檔存放區。 |
| 6 | Profile Store用於受眾資格和分段以篩選活動。 |
| 7 | 從即時[!DNL Target]活動中判斷體驗後，就會選取產生的內容。 |
| 8 | at.js程式庫會隱藏頁面上與必須轉譯的體驗相關聯的對應元素。 |
| 9 | at.js程式庫會顯示內文，以便載入其餘的頁面以供訪客檢視。 |
| 10 | at.js程式庫會操控DOM，從Target Edge Network呈現體驗。 |
| 11 | 體驗會為訪客呈現。 |
| 12 | 載入整個網頁。 |
| 13 | [!DNL Analytics] 資料傳送至「資料收集」伺服器。 |
| 14 | 目標資料會透過SDID與[!DNL Analytics]資料相符，並處理至[!DNL Analytics]報表儲存區。 然後就可以在 [!DNL Analytics] 與 [!DNL Analytics] 中，透過 [!DNL Target] for Target[!UICONTROL  (A4T) 報表來檢視 ]Analytics 資料。 |

### 僅限裝置上

[!UICONTROL 裝置上決] 策只限裝置上決策方法，當裝置上決策只能用於整個網頁時，必須在at.js 2.5.0+中設定。

裝置上決策可以快如閃電的速度提供您的體驗和個人化活動，因為決策來自快取的規則物件，其中包含符合裝置上決策資格的所有活動。

若要進一步瞭解哪些活動符合裝置上決策的資格，請參閱[裝置上決策中支援的功能](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/supported-features.md)。

只有在需要[!DNL Target]決策的所有頁面上都有高效能時，才應使用此決策方法。 此外，請記住，當選取此決策方法時，您不符合裝置上決策資格的[!DNL Target]活動將不會傳送或執行。 at.js程式庫2.5.0+設定為僅尋找快取的規則物件以做出決策。

下圖說明您的訪客、瀏覽器、at.js 2.5.0+和Akamai CDN之間的互動。 Akamai CDN會快取訪客首次瀏覽的規則物件。 對於新訪客的首次頁面瀏覽，JSON規則對象必須從Akamai CDN下載，才能在訪客的瀏覽器上快取至本機。 下載JSON規則工件後，立即做出決定，而不需封鎖網路呼叫。 以下流程圖會擷取新訪客。

![僅限裝置的流程圖](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-only.png)

以下清單與圖中的數字相對應：

>[!NOTE]
>
>[!DNL Adobe Target] 管理伺服器會符合您所有符合裝置上決策資格的活動的資格、產生JSON規則物件，並將它傳播至Akamai CDN。系統會持續監控您的活動，以取得更新，以輸出要傳播至Akamai CDN的新JSON規則物件。

| 步驟 | 說明 |
| --- | --- |
| 1 | 從[Adobe Experience Cloud身份服務](https://experienceleague.adobe.com/docs/id-service/using/home.html)檢索[!DNL Experience Cloud Visitor ID]。 |
| 2 | at.js 程式庫會同步載入並隱藏文件本文。<br>您也可以以非同步方式載入at.js程式庫，並在頁面上建置選擇性的預先隱藏程式碼片段。 |
| 1 | at.js程式庫會隱藏主體，以防止閃爍。 |
| 4 | at.js程式庫會要求從離訪客最近的Akamai CDN擷取JSON規則對象。 |
| 5 | Akamai CDN會以JSON規則對象回應。 |
| 6 | JSON規則物件會在訪客的瀏覽器上快取至本機。 |
| 7 | at.js程式庫會解譯JSON規則工件，並執行擷取體驗和隱藏已測試元素的決定。 |
| 8 | at.js程式庫會顯示內文，以便載入其餘的頁面以供訪客檢視。 |
| 9 | at.js程式庫會處理DOM，以從快取的JSON規則物件轉譯體驗。 |
| 10 | 體驗會為訪客呈現。 |
| 11 | 載入整個網頁。 |
| 12 | [!DNL Analytics] 資料傳送至「資料收集」伺服器。目標資料會透過SDID與[!DNL Analytics]資料相符，並處理至[!DNL Analytics]報表儲存區。 然後就可以在 與 中，透過 for Target (A4T) 報表來檢視 [!DNL Analytics][!DNL Analytics]Analytics 資料。[!DNL Target] |

下圖說明訪客、瀏覽器at.js 2.5.0+與訪客後續頁面點擊或返回瀏覽的快取JSON規則物件之間的互動。 由於JSON規則工件已快取且可在瀏覽器上使用，因此會立即做出決定，而不需要封鎖網路呼叫。 此流程圖會擷取後續頁面導覽或舊訪客。

![後續頁面導覽和重複造訪的僅限裝置上流程圖](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-only-subsequent.png)

以下清單與圖中的數字相對應：

>[!NOTE]
>
>[!DNL Adobe Target] 管理伺服器會符合您所有符合裝置上決策資格的活動的資格、產生JSON規則物件，並將它傳播至Akamai CDN。系統會持續監控您的活動，以取得更新，以輸出要傳播至Akamai CDN的新JSON規則物件。

| 步驟 | 說明 |
| --- | --- |
| 3 | 從[Adobe Experience Cloud身份服務](https://experienceleague.adobe.com/docs/id-service/using/home.html)檢索[!DNL Experience Cloud Visitor ID]。 |
| 2 | at.js 程式庫會同步載入並隱藏文件本文。<br>您也可以以非同步方式載入at.js程式庫，並在頁面上建置選擇性的預先隱藏程式碼片段。 |
| 1 | at.js程式庫會隱藏主體，以防止閃爍。 |
| 4 | at.js程式庫會解譯JSON規則工件，並執行記憶體中的擷取體驗決定。 |
| 5 | 已測試的元素會隱藏。 |
| 6 | at.js程式庫會顯示內文，以便載入其餘的頁面以供訪客檢視。 |
| 7 | at.js程式庫會處理DOM，以從快取的JSON規則物件轉譯體驗。 |
| 8 | 體驗會為訪客呈現。 |
| 9 | 載入整個網頁。 |
| 10 | [!DNL Analytics] 資料傳送至「資料收集」伺服器。目標資料會透過SDID與[!DNL Analytics]資料相符，並處理至[!DNL Analytics]報表儲存區。 然後就可以在 [!DNL Analytics] 與 [!DNL Analytics] 中，透過 [!DNL Target] for Target[!UICONTROL  (A4T) 報表來檢視 ]Analytics 資料。 |

### 混合

[!UICONTROL 混合] 在必須同時執行裝置上決策和需要對Adobe Target邊緣網路進行網路呼叫的活動時，必須在at.js 2.5.0+中設定的決策方法。

當您同時管理裝置上的決策活動和伺服器端活動時，在思考如何在頁面上部署和布建[!DNL Target]時，可能會有些複雜和麻煩。 [!DNL Target]採用混合決策方法，可得知何時必須對Adobe Target邊緣網路進行伺服器呼叫，以處理需要伺服器端執行的活動，以及何時只執行裝置上的決策。

JSON規則工件包含中繼資料，以通知at.jsmbox是否有執行中的伺服器端活動或裝置上的決策活動。 此決策方法可確保您想要快速傳遞的活動透過裝置上決策完成，對於需要更強大的ML導向個人化的活動，這些活動則透過Adobe Target邊緣網路完成。

下圖說明首次瀏覽您頁面的新訪客的訪客、瀏覽器、at.js 2.5.0+、Akamai CDN和Adobe Target邊緣網路之間的互動。 此圖表的優點是，JSON規則工件會以非同步方式下載，而決策則是透過Adobe Target邊緣網路進行。

此方法可確保對象的大小（可包含許多活動）不會對決策的延遲產生負面影響。 同步下載JSON規則工件並在之後做出決策也可能會對延遲產生不利影響，而且可能不一致。 因此，混合決策方法是最佳實務建議，可針對新訪客的決策一律進行伺服器端呼叫，並在並行快取JSON規則工件時進行。 對於任何後續的頁面瀏覽和回訪，會透過JSON規則工件，從快取和記憶體中做出決策。

![首次訪客的混合流程圖](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/hybrid-first-time-visitor.png)

以下清單與圖中的數字相對應：

>[!NOTE]
>
>[!DNL Adobe Target] 管理伺服器會符合您所有符合裝置上決策資格的活動的資格、產生JSON規則物件，並將它傳播至Akamai CDN。系統會持續監控您的活動，以取得更新，以輸出要傳播至Akamai CDN的新JSON規則物件。

| 步驟 | 說明 |
| --- | --- |
| 1 | 從[Adobe Experience Cloud身份服務](https://experienceleague.adobe.com/docs/id-service/using/home.html)檢索[!DNL Experience Cloud Visitor ID]。 |
| 2 | at.js 程式庫會同步載入並隱藏文件本文。<br>您也可以以非同步方式載入at.js程式庫，並在頁面上建置選擇性的預先隱藏程式碼片段。 |
| 3 | at.js程式庫會隱藏主體，以防止閃爍。 |
| 4 | 系統會向Adobe Target邊緣網路提出頁面載入要求，包括所有已設定的參數，例如（ECID、客戶ID、自訂參數、使用者設定檔等）。 |
| 5 | 同時，at.js會要求從離訪客最近的Akamai CDN擷取JSON規則對象。 |
| 6 | (Adobe Target邊緣網路)描述檔指令碼會執行，然後饋送至描述檔商店。 Profile Store會從觀眾程式庫要求合格的觀眾（例如，從[!DNL Adobe Analytics]、[!DNL Adobe Audience Manager]等共用的觀眾）。 |
| 7 | Akamai CDN會以JSON規則對象回應。 |
| 8 | Profile Store用於受眾資格和分段以篩選活動。 |
| 9 | 從即時[!DNL Target]活動中判斷體驗後，就會選取產生的內容。 |
| 10 | at.js程式庫會隱藏頁面上與必須轉譯的體驗相關聯的對應元素。 |
| 11 | at.js程式庫會顯示內文，以便載入其餘的頁面以供訪客檢視。 |
| 12 | at.js程式庫會操控DOM，從Target Edge Network呈現體驗。 |
| 13 | 體驗會為訪客呈現。 |
| 14 | 載入整個網頁。 |
| 15 | [!DNL Analytics] 資料傳送至「資料收集」伺服器。目標資料會透過SDID與[!DNL Analytics]資料相符，並處理至[!DNL Analytics]報表儲存區。 然後就可以在 [!DNL Analytics] 與 [!DNL Analytics] 中，透過 [!DNL Target] for Target[!UICONTROL  (A4T) 報表來檢視 ]Analytics 資料。 |

下圖說明您的訪客、瀏覽器、at.js 2.5.0+和快取的JSON規則物件之間，在後續頁面導覽或回訪時的互動。 在此圖中，請只關注裝置上決定後續頁面導覽或回訪的使用案例。 請記住，根據特定頁面上的活動，可進行伺服器端呼叫以執行伺服器端決策。

![用於後續頁面導覽和重複瀏覽的混合流程圖](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/hybrid-subsequent.png)

以下清單與圖中的數字相對應：

>[!NOTE]
>
>[!DNL Adobe Target] 管理伺服器會符合您所有符合裝置上決策資格的活動的資格、產生JSON規則物件，並將它傳播至Akamai CDN。系統會持續監控您的活動，以取得更新，以輸出要傳播至Akamai CDN的新JSON規則物件。

| 步驟 | 說明 |
| --- | --- |
| 1 | 從[Adobe Experience Cloud身份服務](https://experienceleague.adobe.com/docs/id-service/using/home.html)檢索[!DNL Experience Cloud Visitor ID]。 |
| 2 | at.js 程式庫會同步載入並隱藏文件本文。<br>您也可以以非同步方式載入at.js程式庫，並在頁面上建置選擇性的預先隱藏程式碼片段。 |
| 1 | at.js程式庫會隱藏主體，以防止閃爍。 |
| 4 | 會提出要求以擷取體驗。 |
| 5 | at.js程式庫會確認JSON規則物件已快取，並執行記憶體中的擷取體驗決定。 |
| 6 | 已測試的元素會隱藏。 |
| 7 | at.js程式庫會顯示內文，以便載入其餘的頁面以供訪客檢視。 |
| 8 | at.js程式庫會處理DOM，以從快取的JSON規則物件轉譯體驗。 |
| 9 | 體驗會為訪客呈現。 |
| 10 | 載入整個網頁。 |
| 11 | [!DNL Analytics] 資料傳送至「資料收集」伺服器。目標資料會透過SDID與[!DNL Analytics]資料相符，並處理至[!DNL Analytics]報表儲存區。 然後就可以在 [!DNL Analytics] 與 [!DNL Analytics] 中，透過 [!DNL Target] for Target[!UICONTROL  (A4T) 報表來檢視 ]Analytics 資料。 |

## 我要如何啟用裝置上的決策？

裝置上決策適用於所有使用At.js 2.5.0+的[!DNL Target]客戶。

若要啟用裝置上決策：

>[!NOTE]
>
>您必須擁有[!UICONTROL 管理員]或[!UICONTROL 審批者] [使用者角色](/help/administrating-target/c-user-management/user-management.md)才能啟用或停用裝置上決策切換。

1. 按一下「**[!UICONTROL 管理]** > **[!UICONTROL 實施]** > **[!UICONTROL 帳戶詳細資訊]**」。
1. 在「**[!UICONTROL Account Details]**」下，滑動「**[!UICONTROL On-Device Decisioning]**」切換至「on」位置。

   ![裝置上決策切換](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-decisioning-toggle.png)

   如果您啟用設備上決策，會顯示「[!UICONTROL 在對象]中包含所有現有的設備上決策限定活動」選項。
1. （條件性）如果您想要將符合裝置上決策資格的所有即時Target活動自動包含在對象中，請將切換至「開啟」位置滑動。

   關閉此切換表示您必須重新建立並啟動任何裝置上決策活動，才能將其納入產生的規則物件中。 換言之，在開啟[!UICONTROL 裝置上決策]切換之前，任何處於即時狀態的活動都不會包含在規則物件中。

在啟用[!UICONTROL 裝置上決策]切換後，[!DNL Target]開始為您的客戶產生並傳播[規則對象](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/rule-artifact.md)。

>[!IMPORTANT]
>
>請務必在初始化Adobe TargetSDK之前啟用切換，以使用裝置上的決策。 規則不自然物首先需要產生並傳播至Akamai CDN，才能在裝置上進行決策。 傳播可能需要5到10分鐘，第一個規則對象才會產生並傳播至Akamai CDN。

## 如何設定at.js 2.5.0+以使用裝置上決策？

1. 按一下「**[!UICONTROL 管理]** > **[!UICONTROL 實施]** > **[!UICONTROL 帳戶詳細資訊]**」。
1. 在「實作方法」(**[!UICONTROL Implementation Methods)]** > 「主要實作方法」(**[!UICONTROL Main Implementation Method)]**&#x200B;下，按一下您at.js版本（必須為at.js 2.5.0或更新版本）旁的「編輯」(**[!UICONTROL )。]**

   ![編輯主要實作方法設定](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/main-implementation-method.png)

   >[!IMPORTANT]
   >
   >在變更這些預設設定之前，請洽詢Client Care，以免影響您目前的實作。

1. 選擇所需的決策方法：

   * [!UICONTROL 僅限伺服器端]
   * [!UICONTROL 僅限裝置上]
   * [!UICONTROL 混合]

   ![編輯at.js設定面板](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/global-settings.png)

### 全域設定

您可以為所有[!DNL Target]決策配置預設[!UICONTROL 決策方法]。 各種決策方法為：[!UICONTROL 僅伺服器端]、[!UICONTROL 僅設備上]和[!UICONTROL Hybrid]。 在Target UI中選取的決策方法是在`decisioningMethod`欄位下方的`window.targetGlobalSettings`中設定。 進一步瞭解[targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md)中的`decisioningMethod`。

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

### 自訂設定

如果您在`window.targetGlobalSettings`中設定`decisioningMethod`，但想要根據您的使用案例覆寫每個Adobe Target決定的`decisioningMethod`，則可在At.js2.5.0+的[getOffers()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md)呼叫中指定`decisioningMethod`來執行此程式。

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
>若要在getOffers()呼叫中使用&quot;on-device&quot;或&quot;hybrid&quot;做為決策方法，請確定全域設定的`decisioningMethod`為&quot;on-device&quot;或&quot;hybrid&quot;。 at.js程式庫2.5.0+必須知道是否在載入頁面後立即下載並快取JSON規則物件。 如果全域設定的決策方法設為「伺服器端」，而「裝置上」或「混合」決策方法傳入getOffers()呼叫中，at.js 2.5.0+將不會快取JSON規則物件，以執行裝置上的決策。

### 對象快取TTL

[!DNL Target] 代表符合裝置上決策資格的活動，此活動包含中繼資料、規則和條件。此物件會快取在Akamai CDN上。 在使用者的首次瀏覽期間，使用者的瀏覽器會下載並快取代表您裝置上決策活動的物件。

在您網站的後續瀏覽中，瀏覽器會自動檢查是否必須下載較新版本的工件。 此檢查會增加延遲。 對象快取TTL定義了自上次成功下載以來您不希望瀏覽器檢查更新對象的分鐘數。 時間範圍越長，效能越好。 時間範圍越短，資料新鮮度就越高，但會增加延遲。

## 我要如何得知裝置上的活動符合決策資格？

在您建立符合裝置上決策資格的活動後，會在活動的[!UICONTROL 概述]頁面中顯示讀取[!UICONTROL 裝置上決策符合資格]的標籤。

![裝置上決策活動「概述」頁面上的合格標籤。](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-decisioning-eligible-label.png)

此標籤並不表示活動將一律透過裝置上的決策傳送。 只有當at.js 2.5.0+設定為使用裝置上決策時，此活動才會在裝置上執行。 如果at.js 2.5.0+未設定為使用裝置上，則此活動仍會透過at.js的伺服器呼叫傳送。

您可以透過[!UICONTROL 裝置上決策符合]篩選條件，篩選符合[!UICONTROL 活動]頁面上裝置上決策的所有活動。

![「活動」頁面上的裝置上決策合格篩選。](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-decisioning-filter.png)

>[!NOTE]
>
>建立並啟動符合裝置上決策資格的活動後，可能需要5到10分鐘的時間，才能將其加入產生並傳播至Akamai CDN簡報點的規則物件中。

## 確保我的裝置上決策活動可透過At.js 2.5.0+傳送的步驟摘要？

1. 存取Adobe TargetUI並導覽至「**[!UICONTROL 管理]** > **[!UICONTROL 實施]** > **[!DNL Account Details]**」，以啟用「裝置上決策&#x200B;]**」切換。**[!UICONTROL 
1. 啟用&#x200B;**&quot;[!UICONTROL 在對象]&quot;**&#x200B;中切換「包括所有現有的設備上決策限定活動」。

   產生第一個JSON規則對象最多需要10分鐘。

1. 建立並啟用裝置上決策](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/supported-features.md)支援的[活動類型，並確認裝置上決策符合資格。
1. 透過at.js設定UI，將&#x200B;**[!UICONTROL 決策方法]**&#x200B;設為&#x200B;**[!UICONTROL &quot;Hybrid&quot;]**&#x200B;或&#x200B;**[!UICONTROL &quot;僅限裝置上&quot;]**。
1. 下載並部署At.js 2.5.0+至您的頁面。
