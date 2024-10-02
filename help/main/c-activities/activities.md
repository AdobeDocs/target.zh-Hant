---
keywords: 活動清單；活動；活動型別；編輯活動；活動動作；活動屬性；活動清單篩選器；活動限制；個人化；個人化
description: 使用 [!DNL Adobe Target] 活動個人化特定對象的內容並測試頁面設計。
title: 如何使用 [!DNL Target]個人化內容及測試頁面設計？
feature: Activities
exl-id: 7e61525d-b2db-44f6-a7c2-df5a8d28eca2
source-git-commit: 2831d370d774ce389a8c3621fa5e4354223af993
workflow-type: tm+mt
source-wordcount: '2209'
ht-degree: 28%

---

# 活動概覽

使用[!DNL Adobe Target]活動針對特定對象個人化內容及測試頁面設計。

例如，您可以設計一個活動來測試兩個不同的登陸頁面，其中一個強調夏季女鞋的相關資訊，另一個登陸頁面以一般夏季服飾為主。活動會決定控制每個登入頁面顯示時間的條件，以及決定哪個頁面更成功的量度。 活動會設定為在符合特定條件時開始和結束，例如介於特定日期之間。 或者，您可以選擇在活動核準時開始，並在活動停用時結束。

設計活動時，您應該謹慎規劃。決定活動何時開始及持續時間多長。 然後，列出您的選件並將目標客群指派給每個選件。

## 活動清單 {#section_DE8E2DB30D534962A931EF8BB48240F5}

[!UICONTROL Activities]清單是您開啟[!DNL Target]時的預設檢視。 您可以從此頁面建立活動，並管理現有活動。

您也可以按一下[!DNL Target] UI頂端的[!UICONTROL Activities]索引標籤，以顯示[!UICONTROL Activities]清單。

![活動清單](/help/main/c-activities/assets/activities-list-new.png)

[!UICONTROL Activities]清單提供[!DNL Target]實作中所有活動的概觀，可讓您執行各種動作：

| 元素 | 說明 |
|--- |--- |
| 左側導覽邊欄 | 在您儲存或上線活動與失敗或[草稿活動](/help/main/c-activities/edit-activity.md)之間切換。 |
| [!UICONTROL Show filters]圖示<P>![顯示篩選器圖示](/help/main/assets/icons/Filter.svg) | 按一下清單頂端附近的&#x200B;**[!UICONTROL Show Filters]**&#x200B;圖示，即可存取篩選器，依[!UICONTROL Type]、[!UICONTROL Status]、[!UICONTROL Reporting Source]、[!UICONTROL Experience Composer]、[!UICONTROL Metrics Type]、[!UICONTROL Activity Source]和[!UICONTROL Properties]篩選活動。<P>如需詳細資訊，請參閱下面的[將篩選器套用至活動清單](#filters)。 |
| 搜尋欄位 | 快速尋找活動或減少[!UICONTROL Activity]清單中顯示的活動數目。 您可以依[!UICONTROL Activity Name]、[!UICONTROL URL]或[!UICONTROL ID]搜尋。 |
| [!UICONTROL Create Activity] | 建立活動。<P>如需建立各種活動型別的詳細資訊，請參閱： <ul><li>[建立[!UICONTROL A/B Test]活動](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)</li><li>[建立[!UICONTROL Auto-Allocate]活動](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md)</li><li>[建立[!UICONTROL Auto-Target]活動](/help/main/c-activities/auto-target/create-auto-target.md)</li><li>[建立[!UICONTROL Automated Personalization]活動](/help/main/c-activities/t-automated-personalization/create-ap-activity.md)</li><li>[建立[!UICONTROL Experience Targeting]活動](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md)</li><li>[建立活動](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md)</li><li>[建立[!UICONTROL Recommendations]活動](/help/main/c-recommendations/recommendations.md)</li></ul>如需每個型別的詳細資訊，請參閱下面的[活動型別](#types)。 |
| [!UICONTROL Create mobile preview link]<P>![其他動作功能表](/help/main/assets/icons/MoreVertical.svg) | 使用[行動裝置預覽連結](https://experienceleague.adobe.com/en/docs/target-dev/developer/mobile-apps/target-mobile-preview)為行動應用程式活動執行簡單的端對端QA。<P>按一下&#x200B;**更多選項**&#x200B;圖示，選取&#x200B;**建立行動裝置預覽連結**，然後選擇要在行動裝置上測試的活動。 |
| 自訂表格<P>![自訂表格圖示](/help/main/assets/icons/ColumnSetting.svg) | 按一下頁面右上角的&#x200B;**[!UICONTROL Customize Table]**&#x200B;圖示，然後選取或取消選取所要的欄，以變更哪些欄會顯示在[!UICONTROL Activity]清單中。<P>變更會套用至您的帳戶，並在您登出[!DNL Target]後仍會保持作用中。 |
| 大量作業核取方塊<P>![大量作業圖示](/help/main/assets/icons/Rectangle.svg) | 針對所有活動或選取的活動執行大量作業。<P>如需可用動作的清單（視您的許可權和活動狀態而定），請參閱下列[執行快速動作](#quick-actions)。 |
| [!UICONTROL Type] | 活動型別。 [!UICONTROL Type]欄可讓您依型別快速識別每個活動。 <ul><li>AB-M：手動[!UICONTROL A/B Test]</li><li>AB-AA： [!UICONTROL Auto-Allocate]</li><li>AB-AT： [!UICONTROL Auto-Target]</li><li>AP： [!UICONTROL Automated Personalization]</li><li>XT： [!UICONTROL Experience Targeting]</li><li>MVT： [!UICONTROL Multivariate Test]</li><li>記錄： [!UICONTROL Recommendations]</li></ul>如需每個型別的詳細資訊，請參閱下面的[活動型別](#types)。 |
| [!UICONTROL Name] | 活動的名稱。 按一下每個活動名稱旁的&#x200B;**[!UICONTROL Quick Info]**&#x200B;圖示（ ![快速資訊圖示](/help/main/assets/icons/InfoOutline.svg) ）可在快顯示卡片中檢視有關該活動的詳細資訊，包括[!UICONTROL Activity ID]、[!UICONTROL Activity Objective]、[!UICONTROL Activity Location]、[!UICONTROL Goal]和[!UICONTROL Status]。<P>按一下每個活動名稱旁的&#x200B;**[!UICONTROL More actions]**&#x200B;圖示（![更多動作圖示](/help/main/assets/icons/MoreSmallList.svg) ）以開啟功能表，讓您對活動執行快速動作。 下列動作可供使用（視您的許可權和活動狀態而定）： [!UICONTROL Edit]、[!UICONTROL Activate]、[!UICONTROL Deactivate]、[!UICONTROL Copy]、[!UICONTROL Delete]和[!UICONTROL Archive]。<P>如需每個動作的詳細資訊，請參閱下面的[執行快速動作](#quick-actions)。<P>按一下表格標題，依名稱的字母遞增或遞減順序排序清單。 |
| [!UICONTROL Status] | 活動可能有下列其中一種狀態:<ul><li>**[!UICONTROL Live]**：活動目前正在執行。</li><li>**[!UICONTROL Draft]**：活動設定已開始，但活動處於[草稿模式](/help/main/c-activities/edit-activity.md)，尚未準備好執行。</li><li>**[!UICONTROL Scheduled]**：活動已準備好在指定的開始日期和時間啟動。</li><li>**[!UICONTROL Inactive]**：活動已暫停或停用。</li><li>**[!UICONTROL Syncing]**：活動已儲存且正在同步至[!DNL Target]傳遞網路。</li><li>**[!UICONTROL Ended]**：已達活動的指定結束日期和時間，且已停止提供該活動。</li><li>**[!UICONTROL Archived]**：活動已封存。 您可以啟動已封存的活動以再次使用。</li></ul>**注意**：當您執行特定動作時，例如在[!DNL Target] UI外部使用API方法來啟動活動，更新最多可能需要10分鐘才會傳播至[!DNL Target] UI。 |
| [!UICONTROL Last Updated] | 活動上次更新的日期與時間，以及由誰更新。<P>按一下表格標題，依日期以遞增或遞減順序排序清單。 |
| [!UICONTROL Priority] | 活動的優先順序。<P>如果將多個活動指派至具有相同客群的相同位置，則會使用優先順序。如果將兩個以上活動指派至位置，則會顯示具有最高優先順序的活動。<P>根據您的[設定](/help/main/administrating-target/reporting.md)，[!UICONTROL Priority]的[!DNL Target] UI和選項會有所不同。 您可以使用[!UICONTROL Low]、[!UICONTROL Medium]或[!UICONTROL High]的舊版設定，也可以啟用0到999的精細優先順序。<P>如需優先順序設定的詳細資訊，請參閱&#x200B;*目標與設定*&#x200B;中&#x200B;*活動設定*&#x200B;下的[優先順序](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#section_DCBDC354261F420EBD4B43EA34947BAC)。 |
| [!UICONTROL Property] | 顯示活動的[屬性](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)。<P>企業使用者許可權是[Target Premium](/help/main/c-intro/intro.md#premium)功能。 |
| [!UICONTROL Estimated Lift in Revenue] | 如果 100% 的對象皆看到勝出體驗，則顯示預測收入增加。<P>使用下列公式計算:<P>`(<winning experience> - <control experience>)*<total number of visitors>`<P>如果縮短格式在小數前只有一位數，此數字會四捨五入到最多一位小數。例如: $1.6M、$60K、$900、$8.5K、$205K<P>如果活動沒有足夠資料來召開冠軍賽，或沒有成本預估，此欄會顯示 &quot;---&quot;。<P>請參閱[預估收入中的提升度](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md)以取得詳細資訊。 |
| [!UICONTROL Source] | 顯示建立活動的位置： [!DNL Adobe Target]、[Adobe Target API](https://experienceleague.adobe.com/en/docs/target-dev/developer/overview)、[Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html)、[Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-cloud-service.html)或[AdobeMobile Services](https://developer.adobe.com/client-sdks/documentation/)。 |
| [!UICONTROL Location] | 活動的 URL 可識別活動出現的位置。此欄可協助您快速識別活動，並判斷特定頁面上是否已有活動在執行。<P>如果活動在多個URL上執行，則連結會顯示還有使用多少個URL。 按一下連結以檢視該活動的完整 URL 清單。<P>您可以根據URL來搜尋。 使用搜尋方塊旁邊的下拉式清單，並選取[!UICONTROL URL]。 |
| 作者 | 建立活動的使用者名稱。 |
| [!UICONTROL Decisioning Method] | 每個活動中使用的決策方法： [伺服器端](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/on-device-decisioning/overview.html)或[使用者端](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/on-device-decisioning/on-device-decisioning.html)。 |

## 活動類型 {#types}

[!DNL Target]包含數個活動型別。 下表提供每種活動類型的概覽，以及可協助您深入瞭解的連結。若要協助您更好地選擇適用於您的用途的最佳活動型別，請使用[Adobe Target活動指南](/help/main/c-activities/target-activities-guide.md)。

| 活動類型 | 說明 |
|--- |--- |
| [[!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md) | A/B測試會比較兩個或更多版本的網站內容，以檢視哪個版本在預先指定的測試期間最能改善您的轉換。 |
| [[!UICONTROL Auto-Allocate]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | [!UICONTROL Auto-Allocate] （A/B測試型別）會從兩個或多個體驗中識別獲勝者，並自動重新分配更多流量給獲勝者以增加轉換，同時測試會繼續執行和學習。 |
| [[!UICONTROL Auto-Target]](/help/main/c-activities/auto-target/auto-target-to-optimize.md)<P>![Target Premium](/help/main/assets/premium.png) | 自動鎖定目標是一種A/B測試，可運用進階機器學習來識別多個市場行銷人員定義的高成效體驗，並根據個別客戶設定檔與具有類似設定檔之先前訪客的行為，提供針對每位訪客量身打造的最佳體驗，以便個人化內容並促進轉換。 |
| [[!UICONTROL Multivariate Test]](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) | [!UICONTROL Multivariate Testing] (MVT)會比較頁面上元素中選件的組合，以判斷哪個組合對特定對象執行時效果最佳，並識別哪個元素最能影響活動的成功。 |
| [[!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/experience-target.md) | [!UICONTROL Experience Targeting] (XT)會根據一組行銷人員定義的規則和條件將內容提供給特定對象。 |
| [[!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/automated-personalization.md)<P>![Target Premium](/help/main/assets/premium.png) | [!UICONTROL Automated Personalization] (AP)結合選件或訊息，並使用進階機器學習來根據訪客的個別客戶設定檔比對每位訪客的不同變數，以便個人化內容並促進轉換。 |
| [[!UICONTROL Recommendations]](/help/main/c-recommendations/recommendations.md)<P>![Target Premium](/help/main/assets/premium.png) | 建議會根據網站訪客在網站上的活動，決定如何向訪客建議產品。<P>例如，您可能鼓勵買背包的人考慮買登山鞋和登山杖。您可以利用「購買了此項目、也購買了其他項目的使用者」演算法建立建議，以顯示通常一起購買的商品。或者，您可能想要使用「瀏覽過此專案、也瀏覽了其他專案的使用者」演演算法，將類似的影片推薦給正在觀看的影片，以鼓勵訪客將更多時間花在您的媒體網站上。<P>**附註**：您也可以在[!UICONTROL A/B Test]、[!UICONTROL Auto-Allocate]、[!UICONTROL Auto-Target]和[!UICONTROL Experience Targeting] (XT)活動中包含建議。 如需詳細資訊，請參閱 [Recommendations 作為選件](/help/main/c-recommendations/recommendations-as-an-offer.md)。若要使用此功能，您必須具備 [Target Premium 授權](/help/main/c-intro/intro.md#premium)。 |

## 將篩選器套用至活動清單 {#filters}

按一下清單頂端附近的&#x200B;**[!UICONTROL Show Filters]**&#x200B;圖示（ ![顯示篩選器圖示](/help/main/assets/icons/Filter.svg) ）來存取篩選器。

功能表可讓您依下列屬性篩選活動：

| 屬性 | 詳細資料 |
| --- | --- |
| [!UICONTROL Type] | 依[活動型別](#types)篩選。 |
| [!UICONTROL Status] | 依活動狀態篩選。 |
| [!UICONTROL Reporting Source] | 依報表來源篩選。<ul><li>[[!DNL Analytics]](/help/main/c-integrating-target-with-mac/a4t/a4t.md)：顯示使用[!UICONTROL Analytics for Target] (A4T)作為報表來源的活動。</li><li>[[!DNL Target]](/help/main/c-reports/reports.md)：顯示使用[!DNL Target]作為報表來源的活動。</li><li>[[!DNL Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md)：顯示使用[!DNL Adobe Customer Analytics]作為報表來源的活動。</li></ul> |
| [!UICONTROL Experience Composer] | 活動建立期間使用體驗撰寫器的篩選：<ul><li>[Visual](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md)：顯示使用[!UICONTROL Visual Experience Composer] (VEC)建立的活動。</li><li>[表單式](/help/main/c-experiences/form-experience-composer.md)：顯示使用[!UICONTROL Form-Based Experience Composer]建立的活動。</li></ul> |
| [!UICONTROL Metrics Type] | 活動建立期間選擇[成功量度](/help/main/c-activities/r-success-metrics/success-metrics.md)的篩選器。<ul><li>[!UICONTROL Conversion]</li><li>[!UICONTROL Revenue]</li><li>[!UICONTROL Engagement]</li><li>[!UICONTROL Use an Analytics metric]</lI></ul> |
| [!UICONTROL Decisioning Method] | 依每個活動中使用的決策方法篩選。<ul><li>[伺服器端](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/on-device-decisioning/overview.html)：顯示使用伺服器端決策的活動。</li><li>[使用者端](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/on-device-decisioning/on-device-decisioning.html)：顯示使用使用者端決策的活動。</li></ul> |
| [!UICONTROL Activity Source] | 依用來建立每個活動的活動來源篩選。<ul><li>[!DNL Adobe Target]</li><li>[[!DNL Adobe Target] API](https://experienceleague.adobe.com/docs/target-dev/developer/overview.html)</li><li>[[!DNL Adobe Experience Platform]](https://experienceleague.adobe.com/docs/experience-platform.html)</li><li>[[!DNL Adobe Experience Manager]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service.html)</li><li>[[!DNL Adobe Mobile Services]](https://developer.adobe.com/client-sdks/home/)</li></ul> |
| [!UICONTROL Property] | 依建立活動所在的[屬性](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)篩選。 |

## 執行快速動作 {#quick-actions}

按一下每個活動名稱旁的&#x200B;**[!UICONTROL More actions]**&#x200B;圖示（ ![更多動作功能表](/help/main/assets/icons/MoreVertical.svg) ）以開啟功能表，讓您對活動執行快速動作。

下列動作可供使用（視您的許可權和活動狀態而定）：

| 動作 | 說明 |
| --- | --- |
| [!UICONTROL Edit] | 變更活動。任何活動皆可編輯。<P>如需各種活動編輯方式的詳細資訊，請參閱[編輯活動或另存為草稿](/help/main/c-activities/edit-activity.md)。 |
| [!UICONTROL Deactivate] | 停止已上線或排定的活動。已停用的活動可以重新啟動或封存。<P>如果您停用或封存活動，之後又重新啟動活動，若訪客在停用或封存活動前便位於活動中，則重新啟動後會繼續隸屬該活動。在兩個事件之間記錄的任何轉換指標不會歸於該活動。 |
| [!UICONTROL Activate] | 啟動非使用中活動或準備好要啟動的活動。 |
| [!UICONTROL Archive] | 將活動傳送至封存。依預設，已封存的活動不再出現在[!UICONTROL Activities]清單中。 將活動清單的篩選條件變更為包含已封存的活動，以看到這些活動。您可以啟動已封存的活動以再次使用。<P>如果您停用或封存活動，之後又重新啟動活動，若訪客在停用或封存活動前便位於活動中，則重新啟動後會繼續隸屬該活動。 在兩個事件之間記錄的任何轉換指標不會歸於該活動。 |
| [!UICONTROL Copy] | 複製活動。任何活動皆可複製。複製活動會以相同名稱建立新活動，後面加上「的複本」。例如，名稱為「瀏覽器選件」的測試會複製為「瀏覽器選件複本」。<P>可視化選件會隨活動一起複製。您可以在複本中放心編輯選件，不會影響原始活動。唯一的例外是「內容/資產」資料夾中儲存的選件和影像。 |
| [!UICONTROL Delete] | 刪除草稿或活動。<P>**注意**：已刪除的活動無法復原。 除非您確定您不會再需要此活動，否則請使用[!UICONTROL Archive]動作。 之後，您可以視需要重新啟用活動。 |

## 考量事項

請注意[!UICONTROL Activity]清單的下列詳細資料：

* 已封存和已結束的活動未出現在[!UICONTROL Activities]清單中。 若要檢視這些活動，請使用清單頂端的[篩選圖示](#filters) （ ![顯示篩選圖示](/help/main/assets/icons/Filter.svg) ）來篩選活動。
* 當原本於[!DNL Target Classic]中建立的活動停用或遭刪除時，該活動會從[!DNL Target Standard/Premium]中刪除。 已刪除原本於[!DNL Target Classic]中建立的活動未傳送至[!DNL Target Standard/Premium]中的[!UICONTROL Archive]資料夾。 封存資料夾功能僅適用於 [!DNL Target Standard/Premium]·￼·中建立的活動。
* [!UICONTROL Automated Personalization] (AP)、[!UICONTROL Auto-Allocate]和[!UICONTROL Auto-Target]以外的所有活動型別皆可讓您選擇使用[!DNL Target]或[!DNL Adobe Analytics]做為資料來源。 [!UICONTROL Automated Personalization]、[!UICONTROL Auto-Allocate]和[!UICONTROL Auto-Target] *一律*&#x200B;使用[!DNL Target]資料。
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
| 唯一的選取器 | 300如果選取器在不同的體驗中重複，則會計為一次。 但如果在相同體驗中重複，則再算一次。 |
| 每個體驗中的選件 | 350 |
| 量度中的點擊追蹤選取器 | 50 |
| 量度中的 Mbox | 50 |
| 對象和位置 | 50個對象和位置(mbox)組合不得超過50個。 |

如果您超過任何這些上限，則無法儲存活動。

增加活動中的這些專案數，也會增加跨[!DNL Target]同步活動所需的時間長度。

如需V[!UICONTROL Visual Experience Composer] VEC的其他限制，請參閱[視覺化體驗撰寫器限制](/help/main/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#section_F33C2EA27F2E417AA036BC199DD6C721)。

## 針對在[!DNL Target]外部更新的活動，將屬性匯入到[!DNL Target] {#section_802B0D174E6A44E1A96F404CA81AAE44}

如果從[!DNL Target]外部更新在[!DNL Target]中建立的活動（例如，透過API），則會將下列活動屬性匯入回[!DNL Target]： `thirdpartyId`、`startDate`、`endDate`、`status`、`priority`以及`marketingCloudMetadata(remoteModifiedBy)`。

此匯入工作會在活動頁面開啟時執行，最多延遲10分鐘。

