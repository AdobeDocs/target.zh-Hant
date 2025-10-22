---
keywords: 發行說明；新功能；發行；更新；更新；發行；增強功能；增強功能；修正；錯誤修正；更新；目前更新
description: 了解  [!DNL Adobe Target] 目前版本包含的新功能、加強功能和錯誤修正，其中包括 SDK、API 和 JavaScript 程式庫。
landing-page-description: 深入了解  [!DNL Adobe Target] 目前版本所包含的新功能、增強功能和修正。
short-description: 深入了解  [!DNL Target] 目前版本所包含的新功能、增強功能和修正。
title: 目前發行的版本包含哪些內容？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 7d73870275c266055825c2fce90489ef82825fca
workflow-type: tm+mt
source-wordcount: '1700'
ht-degree: 17%

---

# [!DNL Target] 發行說明 (最新)

探索[!DNL Adobe Target]的最新功能、增強功能和修正。 這些發行說明也涵蓋了[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js和其他平台元件（如適用）的更新。

(括號內的問題編號供 [!DNL Adobe] 內部使用。)

## 您需要瞭解的時間性更新 {#time-sensitive}

[!BADGE 重要]{type=Informative}

針對與[!DNL Adobe Target]和您的實作相關的時效性更新，[!DNL Adobe]會透過[!UICONTROL Experience League]提供詳細的發行說明和檔案。 以下是和您的實作相關的一些重點專案：

### [!DNL Target] UI版本切換為棄用

如需詳細資訊，請參閱[[!DNL Target] UI更新常見問題](/help/main/c-intro/updated-ui-faq.md)。

## [!DNL Target Standard/Premium] 25.10.1 （2025年10月22日）

此版本包含下列更新和修正：

**活動**

+++ 檢視詳細資料
* **已解決更新的UI中的可用性問題**。 [!UICONTROL Observers]現在可以使用[!UICONTROL View Activity]選項預覽活動，就像在舊版UI中一樣。 (TGT-51741)
* **[!UICONTROL Observer]使用者現在可以在更新的UI中檢視活動內容。**&#x200B;已還原已更新活動UI中觀察者角色使用者的可見性。 以前，觀察者無法檢視舊版UI中可用的修改、選件和內容變更。 (TGT-53785)
* **[!UICONTROL Approver]個使用者現在可以編輯活動目標，而不會發生編輯器許可權錯誤。**&#x200B;已解決「活動建立」UI中阻止核准者層級使用者儲存進階目標設定之變更的許可權問題。 受影響的使用者收到`403 Forbidden.Resource`錯誤，需要編輯器許可權，儘管具有足夠的存取許可權。 (TGT-53819)

+++

**客群**

+++檢視詳細資料
* **已在「僅限此活動」報表中還原多個對象選擇。**&#x200B;已解決活動建立UI中，造成使用者無法在[!UICONTROL This activity only]的[!UICONTROL Goals & Settings]區段下選取多個對象的問題。 (TGT-53283)
* **以對象為基礎的報表圖表現在可正確顯示轉換資料。**&#x200B;解決[!UICONTROL Reports]標籤中造成圖表在選取非預設對象時失敗的問題。 雖然可以使用資料和信賴度量度，但視覺化圖表只顯示實線，導致分析困難。 (TGT-53769)
* **[!UICONTROL Targeting] UI現在會清楚指出排除的對象規則。**&#x200B;已解決在活動建立UI的[!UICONTROL Targeting]區段中，設定為[!UICONTROL Exclude]的對象規則未明確顯示的問題。 這會導致檢閱目標定位邏輯時發生混淆，尤其是排除特定URL的受眾。 (TGT-53809)
* **對象定義值現在可以在[!UICONTROL Targeting]索引標籤中選取及複製。**&#x200B;解決「活動建立」介面中造成使用者無法選取及複製「[!UICONTROL Targeting]」索引標籤中對象規則值的問題。 舊版UI提供了此功能，但更新版UI中缺少此功能。 (TGT-53856)

+++

**本地化**

+++檢視詳細資料
* **修正zh_CN頁面編輯器內容中「引號」的誤譯。**&#x200B;更正了zh_CN地區設定中的內容翻譯錯誤，其中術語「quote」被不準確地翻譯為「报价」，這表示有商業報價。 在「印刷樣式>標題樣式>區塊引號」區段中，意指格式元素（引號區塊）而非定價。 (TGT-53841)
* **已修正zh_CN頁面編輯器內容中「已移除引號」的錯誤翻譯。**&#x200B;更正了zh_CN地區設定中，「quote removed」未正確轉譯為「移除了报价」的翻譯錯誤，這表示有商業報價。 在「印刷樣式>標題樣式>區塊引號」區段中，術語是指格式元素（引號區塊）而非定價。 (TGT-53843)
* **已修正zh_CN頁面編輯器內容中「重新排列引號」的錯誤翻譯。**&#x200B;更正了zh_CN地區設定中的內容翻譯錯誤，其中「quote reorized」被不準確地翻譯為「重新排列了报价」，這表示有商業報價。 在「印刷樣式>標題樣式>區塊引號」區段中，術語是指格式元素（引號區塊）而非定價。 (TGT-53844)
* **已修正zh_CN頁面編輯器內容中「已變更引號」的錯誤翻譯。**&#x200B;更正了zh_CN地區設定中，「quote changed」未正確轉譯為「更改了报价」的翻譯錯誤，建議使用商業報價。 在「印刷樣式>標題樣式>區塊引號」區段中，術語是指格式元素（引號區塊）而非定價。 (TGT-53845)

+++

**推薦**

+++檢視詳細資料
* **Recommendations的CSS選取器變更現在可正確儲存。**&#x200B;解決活動建立UI中，使用者無法更新建議位置的CSS選取器的問題。 變更在儲存後恢復，封鎖目標容器的更新。 (TGT-53835)
* **頁面載入事件選擇現在會在建議修改中持續存在。**&#x200B;解決在活動建立UI中，將推薦的事件型別從[!UICONTROL View]切換到[!UICONTROL Page Load]時，使用者無法儲存變更的問題。 雖然選取範圍看起來成功，但在導覽離開後恢復，封鎖活動發佈。 (TGT-53957)

+++

**報表**

+++檢視詳細資料
* **「[!UICONTROL Export order details to CSV]」現在下載完整資料。**&#x200B;已解決在更新的[!UICONTROL Overview] UI中導致&quot;[!UICONTROL Export Order details to CSV]&quot;選項下載空白檔案的問題，即使存在有效的報表資料亦然。 (TGT-53787)

+++

**安全性**

+++檢視詳細資料
* 已新增&#x200B;**IMS預先篩選來保護GQL端點免於跨組織資料暴露。**&#x200B;解決Admin標籤中影響licenseGroups和targetProperties GraphQL端點的安全性弱點。 該問題源自於搭配管理員使用者端權杖使用JIL API，而該權杖可被利用來存取跨組織產品資料。 (TGT-53837)

+++

**可視化體驗撰寫器 (VEC)**

+++檢視詳細資料
* **在活動建立UI中還原編寫穩定性。**&#x200B;解決VEC UI中導致編寫失敗和連結意外變成可點按的間歇性問題，將使用者從頁面重新導向。 (TGT-53153)
* **在活動建立UI中編輯已儲存活動的已還原。**&#x200B;已解決導致使用者在儲存修改後無法編輯活動的問題。 受影響的活動在&quot;[!UICONTROL Applying initial modifications]&quot;中持續卡住，封鎖進一步的更新並隱藏[!UICONTROL Cancel]按鈕。 (TGT-53631)
* **VEC不再於「[!UICONTROL Applying initial modifications]」上停頓。**&#x200B;解決VEC中的效能問題，此問題在載入有大量修改的體驗時造成長時間延遲。 受影響的使用者看到UI卡在&quot;[!UICONTROL Applying initial modifications]&quot;上達數分鐘，尤其是在體驗B案例中。 (TGT-53727)
* **VEC現在會載入修改內容，但不含根元素。**
解決VEC中載入缺少明確根元素的修改時，導致體驗停滯的問題。 這些修改先前導致UI在「A[!UICONTROL pplying initial modifications]」上無限期擱置。 (TGT-53799)
* **在活動中儲存變更現在可如預期般運作。**&#x200B;解決在新的建立UI中許可權相關的問題，此問題阻止使用者在編輯活動中的目標和進階設定時儲存變更。 受影響的使用者看到紅色錯誤色帶和「Forbidden.Resource」訊息，儘管擁有適當的存取權。 (TGT-53816)
* **VEC UI現在會保留所有檢視中的體驗修改。**&#x200B;已解決更新VEC中影響體驗開發的多個問題。 修改無法正確持續存在，尤其是使用HTML選件或在檢視之間切換時。 (TGT-53825)
* **現在當修改跨越多個體驗時，所有檢視都會正確顯示。**&#x200B;解決在活動建立UI中，當修改套用至多個檢視時只顯示一個檢視的問題。 即使已正確套用修改，暫留工具提示仍無法列出所有關聯的檢視。 (TGT-53827)
* **VEC不再在「[!UICONTROL Applying initial modifications]」上間歇性停頓。**&#x200B;解決VEC中體驗無法載入並停留在「[!UICONTROL Applying initial modifications]」上的間歇性問題。 此行為不一致，有時會觸發重新導向回圈或需要手動清除快取。 (TGT-53916)
* 無法重新產生&#x200B;**VEC載入問題。**&#x200B;我們已調查一個回報問題，此問題導致VEC在編輯現有活動時停留在「[!UICONTROL Applying initial modifications]」上。 此行為疑似與缺少上層元素的HTML內容有關。 我們將繼續監視復發，並建議對HTML選件使用結構化容器來確保穩定性。 (TGT-53972)
* VEC中的&#x200B;**[!UICONTROL Design]模式不再像[!UICONTROL Browse]模式一樣間歇性地運作。**&#x200B;已解決UI中，[!UICONTROL Design]模式間歇性地表現為[!UICONTROL Browse]模式的問題，可允許可點按的`<a>`連結並防止選取元素。 這會導致暫留方塊消失並封鎖修改工作流程。 (TGT-53136)
* 在&#x200B;**模式下的[!UICONTROL Composer]按鈕點選不再觸發頁面重新導向。**&#x200B;解決在更新的VEC UI中按一下[!UICONTROL Composer]模式中的按鈕時，導致未預期的重新導向至按鈕的目標URL的問題。 這會防止使用者編輯call-to-action (CTA)元素，並中斷編寫工作流程。 (TGT-53137)
* **自動個人化活動中的選件代碼更新現在可順利儲存。**&#x200B;已解決「新建立」UI中在[!UICONTROL Invalid user input]活動中更新優惠方案代碼時導致「[!UICONTROL Automated Personalization]」錯誤的問題。 即使輸入有效，該錯誤也會阻止使用者儲存變更。 (TGT-53586)
* VEC中的&#x200B;**[!UICONTROL Design]模式現在會封鎖可編輯元件的連結導覽。**&#x200B;已解決更新VEC中可點按元素（例如按鈕和連結）即使在[!UICONTROL Design]模式中也會觸發頁面重新導向的問題。 此行為模擬[!UICONTROL Browse]模式，並阻止使用者修改關鍵元件。 (TGT-53696)
* **「[!UICONTROL Clicked an element]」量度現在無重新導向或錯誤地運作。**&#x200B;解決在新的建立UI中，選擇&quot;[!UICONTROL Clicked an element]&quot;轉換量度時導致非預期重新導向和空白畫面的問題。 安裝程式期間按一下按鈕會觸發導覽，而非註冊元素，引發&quot;[!UICONTROL element not found]&quot;錯誤。 (TGT-53817)
* **編輯期間現有活動不再卡在無限載入回圈中。**&#x200B;解決在新的建立UI中編輯VEC中的現有活動導致頁面停留在無限載入回圈中的問題。 此問題不會影響新建立的活動，且是由頁面上預先存在的修改所觸發。 (TGT-53913)
* **含有修改的現有活動頁面現在會在VEC中正確載入。**&#x200B;已解決在更新的VEC中，使用已儲存的修改編輯現有活動時，造成頁面停滯在載入階段的問題。 新活動已順利載入，但先前設定的活動無法呈現。 (TGT-53967)

+++

## 額外的發行說明和版本詳細資料

| 資源 | 詳細資料 |
|--- |--- |
| [發行說明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hant) | 有關 Platform Web SDK 各版本變更的詳細資料。 |
| [at.js 版本詳細資料](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=zh-Hant){target=_blank} | 有關 [!DNL Adobe Target] at.js JavaScript 程式庫每個版本中的變更的詳細資料。 |

## 文件變更、過去的發行說明和 Experience Cloud 發行說明

除了每次發行的說明，下列資源也提供額外資訊:

| 資源 | 詳細資料 |
|--- |--- |
| [文件變更](/help/main/r-release-notes/doc-change.md) | 檢視本指南未包含在這些發行說明中的更新詳細資訊。 |
| [舊版發行說明](/help/main/r-release-notes/release-notes-for-previous-releases.md)。 | 檢視舊版 Target Standard 和 Target Premium 中新功能和增強功能的詳細資訊。 |
| [Adobe Experience Cloud發行說明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hant){target=_blank} | 檢視 Adobe Experience Cloud 解決方案的最新發行說明。 |

## 搶鮮版版本資訊 {#section_5D588F0415A2435B851A4D0113ACA3A0}

以下資源告訴您下個 Target 版本將推出哪些功能。

| 資源 | 詳細資料 |
|--- |--- |
| [Adobe 優先產品更新](https://www.adobe.com/tw/subscription/priority-product-update.html){target=_blank} | 收到對 [!DNL Target] 以及其他 [!DNL Adobe Experience Cloud] 解決方案未來產品增強功能的提前通知。 |
| [Target 發行說明 - 搶鮮版](/help/main/r-release-notes/target-release-notes.md){target=_blank} | 有關當月 Target 版本的資訊，包括搶鮮版資訊。 |
