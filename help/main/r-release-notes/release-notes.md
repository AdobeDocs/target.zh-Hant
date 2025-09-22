---
keywords: 發行說明；新功能；發行；更新；更新；發行；增強功能；增強功能；修正；錯誤修正；更新；目前更新
description: 了解  [!DNL Adobe Target] 目前版本包含的新功能、加強功能和錯誤修正，其中包括 SDK、API 和 JavaScript 程式庫。
landing-page-description: 深入了解  [!DNL Adobe Target] 目前版本所包含的新功能、增強功能和修正。
short-description: 深入了解  [!DNL Target] 目前版本所包含的新功能、增強功能和修正。
title: 目前發行的版本包含哪些內容？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 186bfa96c0849d9cd838b3d493c10cccfd4ff068
workflow-type: tm+mt
source-wordcount: '4104'
ht-degree: 8%

---

# [!DNL Target] 發行說明 (最新)

探索[!DNL Adobe Target]的最新功能、增強功能和修正。 這些發行說明也涵蓋了[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js和其他平台元件（如適用）的更新。

(括號內的問題編號供 [!DNL Adobe] 內部使用。)

## 您需要瞭解的時間性更新 {#time-sensitive}

[!BADGE 重要]{type=Informative}

針對與[!DNL Adobe Target]和您的實作相關的時效性更新，[!DNL Adobe]會透過[!UICONTROL Experience League]提供詳細的發行說明和檔案。 以下是和您的實作相關的一些重點專案：

### [!DNL Target] UI版本切換為棄用

+++檢視詳細資料
[!DNL Target]團隊提供暫時功能，可讓您使用切換按鈕，在更新的[!DNL Target] UI和舊版之間切換。 此選項僅在UI轉出的最後階段可用。

![目標UI版本切換](/help/main/r-release-notes/assets/toggle.png)

轉出完成後，切換將會移除，且所有使用者都會永久轉換為更新後的UI。 [!DNL Adobe]建議提前規劃，因為此功能將很快淘汰。

#### 淘汰時間表

由於最近發現的問題（主要與複雜的客戶自訂有關），[!DNL Target]團隊已調整淘汰時間表：

* **2025年6月17日**：所有IMS組織均已針對特定使用者或整個組織啟用更新的[!DNL Target] UI，以開始測試新體驗。

* **2025年6月30日**： [已更新 [!DNL Target] UI](/help/main/c-intro/understand-the-target-ui.md)成為已啟用UI版本切換之所有IMS組織的預設體驗。

   * 目前看到舊版UI的客戶，預設會在登入時看到更新的UI。
   * UI版本切換在7月底之前仍然可用，以便使用者在需要時切換回去。

  >[!IMPORTANT]
  >
  > [!DNL Adobe]強烈建議使用更新的[!DNL Target] UI。 只有在發生封鎖程式問題時，才能切換回舊版UI，因為切換切換行為[的限制](#limitations)。

* **2025年7月15日至7月30日**： UI版本切換將會分階段永久停用。 受影響的IMS組織無法再還原至舊版UI。

   * 例外會根據不同情況逐一審查。
   * 在封鎖程式問題解決期間，僅會短暫地允許切換式淘汰的延遲（幾天）。

如有任何疑慮或您預期在此轉換期間發生問題，請聯絡[Adobe客戶服務](/help/main/cmp-resources-and-contact-information.md#/help/main/cmp-resources-and-contact-information.md)。

#### UI切換行為的限制 {#limitations}

下列資訊說明選擇使用版本切換時應該注意的限制：

* **新活動的可見性**：如果您切換回舊版使用者介面，在更新的UI中建立的活動將不可見。
* **編輯現有活動**：使用更新的UI時，對現有活動所做的變更（原本是在舊版UI中建立）會發佈至您的網站。 不過，如果您切換回去，這些更新不會顯示在舊版UI中；那裡只會顯示舊版UI進行的最後更新。
* **活動詳細資料的一致性**：無論您使用哪種UI，最新變更都會反映在您已上線的網站上。 不過，舊版UI只會顯示該版本的最新變更。 如果在更新的UI中編輯的活動看起來與您在舊版UI中看到的不同，這種情況可能會導致混淆。

#### 深入瞭解更新UI的資源

* [[!DNL Target] UI更新常見問題集](/help/main/c-intro/updated-ui-faq.md)：此常見問題集解決有關新[!DNL Target] UI和[!UICONTROL Visual Experience Composer] (VEC)的常見問題，包括導覽變更、功能位置以及暫時性UI版本切換的淘汰。 無論您是行銷人員、開發人員或管理員，此FAQ可協助您順利轉換，並充分運用更新後的UI。
* [[!DNL Target Standard/Premium] 25.2.1 （2025年2月17日）發行說明](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-2)：提供[!DNL Target]中[!UICONTROL Activities]、[!UICONTROL Recommendations]和[!UICONTROL Visual Experience Composer] (VEC)的關鍵UI變更摘要。
* [[!DNL Target Standard/Premium] 25.1.1 （2025年1月9日）發行說明](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-1)：提供[!DNL Target]中[!UICONTROL Offers Library]主要UI變更的摘要。
* [瞭解 [!DNL Target] UI](/help/main/c-intro/understand-the-target-ui.md)：提供簡短的總覽，協助您熟悉[!DNL Target]，並提供連結，以取得更深入的資訊和逐步指示。
* [[!UICONTROL Visual Experience Composer]個變更](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md)： [!DNL Adobe Target Standard/Premium] 25.2.1版本（2015年2月17日）推出更新的[!UICONTROL Visual Experience Composer] (VEC)。 本文說明VEC舊版和更新版本之間的差異。
* [[!UICONTROL Visual Experience Composer]選項](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)：本文說明更新的VEC UI及其選項。

+++

## [!DNL Target Standard/Premium] 25.9.2 （2025年9月22日）

此版本包含下列修正和增強功能:

**[!UICONTROL Audiences]**

+++檢視詳細資料
* **修正因對象ID無效而無法複製活動的問題。**&#x200B;客戶嘗試在更新的活動建立程式中複製活動時，遇到因對象ID無效(例如 — 1752722444307)導致的錯誤。 此後端驗證問題可防止相同工作區中的活動重複。 此問題已解決，現在可以成功複製活動而不會出現對象相關錯誤。 (TGT-53717)
* **修正在[!UICONTROL Automated Personalization]強制回應視窗中，[!UICONTROL Manage Content]個活動的僅限活動對象出現無效使用者輸入錯誤的問題。**&#x200B;客戶在AP活動的[!UICONTROL  Manage Content]強制回應視窗中設定僅限活動的對象時，發生無效的使用者輸入錯誤。 儘管先前已成功使用對象，仍發生此問題。 合併的對象設定現在可正確儲存，而不會觸發驗證錯誤。 (TGT-53749)

+++

**文件**

+++檢視詳細資料
* **已將Target專屬的Web SDK檔案頁面移至Adobe Target存放庫。**&#x200B;作為網頁SDK檔案重組的一部分，[!DNL Target]特定內容已從一般網頁SDK檔案移轉至[!DNL Adobe Target] [開發人員指南](https://experienceleague.adobe.com/en/docs/target-dev/developer/a4t/overview-a4t?lang=en){target=_blank}。 此變更可改善內容可發現性，並確保解決方案特定指導由適當的產品團隊維護。 (TGT-53374)

+++

**[!UICONTROL Offer Decisions]**

+++檢視詳細資料
* **優惠決定選項現在會在初始活動建立期間持續顯示。**&#x200B;解決更新後UI中，A/B活動首次建立流程期間，尤其是以無痕模式存取啟用「優惠決定」的租使用者時，無法顯示[!UICONTROL Offer Decision]選項的問題。 只有在導覽至[!UICONTROL Targeting]步驟並返回[!UICONTROL Experiences]後，選項才會出現。 此修正可確保[!UICONTROL Offer Decision]選項在初始設定期間立即可用，從而提高可用性並減少混淆。 (TGT-51888)

+++

**[!UICONTROL Offers]**

+++檢視詳細資料
* **修正當`redirectOptions`時，重新導向選件未在承載中包含`includeContent=true`的問題。**&#x200B;使用`includeContent=true `擷取重新導向選件的客戶在回應承載中遺失`redirectOptions`欄位。 此不一致會影響工作流程，例如選件複製和活動建立。 要求內容時，重新導向選件現在正確包含`redirectOptions`。 (TGT-53737)

+++

**[!DNL Recommendations]**

+++檢視詳細資料
* 已針對在更新的UI中建立的&#x200B;**個活動還原[!UICONTROL Recommendations]點選追蹤。**&#x200B;解決在更新的UI中建立的[!UICONTROL Recommendations]個活動無法註冊點選追蹤的AB問題，導致報告的轉換數為零。 舊版UI中內建的活動可正確追蹤點按次數，並如預期回報轉換。 此修正可確保在更新UI中建立的Recommendations活動現在包含正確的追蹤屬性、還原轉換報告並符合A4T量度。 (TGT-53287)
* **已針對建議活動還原點選追蹤。**&#x200B;解決在更新的UI中建立的[!UICONTROL Recommendations]活動無法登入點選追蹤，導致零回報轉換的問題。 舊版UI已正確將追蹤ID (`at-track-click`)套用至[!UICONTROL Recommendations]內容，而更新的UI誤插入預留位置(`__recsClickTrackIdPlaceholder__`)，導致後端追蹤無法進行。 此修正可確保[!DNL Recommendations]內容現在包含正確的追蹤ID、還原轉換報告並與A4T量度一致。 (TGT-53496)
* 在更新的UI中解決&#x200B;**集合編輯器當機。**&#x200B;修正更新的[!UICONTROL Visual Experience Composer] (VEC) UI中，從編輯器面板開啟集合導致頁面因TypeError當機的問題：無法讀取未定義的屬性（讀取&#39;customLocale&#39;）。 此錯誤發生在多個活動型別，包括[!UICONTROL Recommendations]和A/B測試。 (TGT-53703)
* **移除在VEC中還原之選取集合的選項。**&#x200B;修正VEC中使用者只能取代[!UICONTROL Recommendations]活動中選取的集合，但無法完全移除的問題。 此限制會封鎖需要清除移除集合而不進行替代的使用案例。 此修正引進了清除選項來移除選取的集合，讓活動設定擁有更大的彈性，並與舊版UI行為一致。 (TGT-53652)
* **自訂條件集合現在會在[!UICONTROL Recommendations] UI中正確顯示。**&#x200B;修正Recommendations介面中，使用自訂條件建立的集合無法顯示產品結果的問題。 雖然標準屬性型集合如預期般運作，但使用自訂篩選器的集合會傳回「找不到結果」，儘管目錄符合有效。 此修正可確保使用自訂屬性的集合現在能正確填入[!UICONTROL Product]索引標籤中，還原個人化建議工作流程的完整功能。 (TGT-53653)
* **修正第一次開啟[!UICONTROL Products]頁面時，集合未顯示產品的問題。**&#x200B;在[!UICONTROL Recommendations]區段中存取集合的客戶在首次開啟[!UICONTROL Products]頁面時，遇到空的產品結果。 此問題是由於GraphQL查詢中的後端錯誤所導致，該錯誤無法載入具有自訂條件之集合的產品資料。 問題已解決，產品現在無需環境切換即可正確顯示。 (TGT-53694)
* **修正無法在表單式[!UICONTROL Recommendations]活動中移除集合的問題。**&#x200B;使用[!UICONTROL Recommendations]建立[!UICONTROL Form-Based Experience Composer]活動的客戶無法取消選取先前選擇的集合。 UI要求在儲存前選取集合，以防止使用者恢復為「所有集合」。 此行為已更新，以符合VEC功能，允許客戶在儲存時無需選取集合，並按預期預設為「所有集合」。 (TGT-53708)
* **修正因遺失集合或篩選規則值而無法由屬性設定促銷活動的問題。**&#x200B;客戶在活動建立程式中依屬性設定促銷活動時，發生錯誤，指出促銷活動缺少集合ID或篩選規則值。 即使設定看似完成，此驗證問題仍會封鎖進度。 現在起，只要依屬性設定，即可成功儲存促銷活動。 (TGT-53750)
* **修正因重複體驗名稱而無法儲存活動的問題。**&#x200B;客戶在儲存包含特定條件和設計組合的活動時遇到無效的使用者輸入錯誤。 即使安裝程式看起來有效，重複體驗名稱也會觸發錯誤。 現在可以儲存具有不同設定的活動，而不會出現命名衝突。 (TGT-53805)
* **修正屬性所設定促銷活動的驗證仍無效的問題。**&#x200B;客戶在活動建立程式中依屬性設定促銷活動時，即使所有必要欄位皆已正確填入，仍遇到持續性驗證錯誤。 此問題是由於[!UICONTROL Recommendations]工作流程中的驗證邏輯不正確所導致。 屬性式促銷活動現在會驗證並如預期儲存。 (TGT-53811)
* **修正將促銷活動套用至即時[!UICONTROL Recommendations]活動觸發錯誤的問題。**&#x200B;客戶在嘗試將前端促銷活動套用至即時[!UICONTROL Recommendations]活動時，發生「促銷活動缺少集合ID或篩選規則值」錯誤，即使在提供有效的設定詳細資料後亦然。 促銷活動現在可以成功套用至已上線的活動，而不會觸發驗證錯誤，以確保在更新的活動建立UI中更順暢的體驗。 (TGT-53738)
* **修正[!UICONTROL Recommendations] UI中的集合未顯示產品的問題。**&#x200B;來自單一租使用者的客戶報告說在新UI的[!UICONTROL Recommendations]區段中檢視某些集合時，無法載入產品清單。 問題透過切換環境而暫時解決，但此因應措施導致使用者體驗不佳。 產品實體現在會一致載入，不需要環境切換。 (TGT-53783)
* **修正活動建立UI中未在一行顯示條件和設計的問題。**&#x200B;之前，活動建立程式中的條件和設計是以壓縮格式顯示，因此客戶很難檢視和管理個別專案。 每個標準和設計現在都顯示在其自己的線上，提高了更新UI中的可讀性和可用性。 (TGT-53818)

+++

**報表**

+++檢視詳細資料
* **[!UICONTROL Total Revenue]量度現在包含在來自活動報表的CSV匯出中。**&#x200B;已解決更新[!UICONTROL Overview] UI中的問題，其中總收入在活動報告檢視中正確顯示，但在CSV匯出中遺失，顯示為$0。 這種差異導致使用者無法依賴匯出的資料進行離線分析和報告。 (TGT-53325)
* **[!UICONTROL Total Sales]量度現在包含在來自活動報表的CSV匯出中。**&#x200B;已解決更新UI中，[!UICONTROL Total Sales]量度在活動報告檢視中正確顯示，但CSV匯出中缺少的問題。 這種差異導致使用者無法存取下載報表中的完整效能資料。 此修正可確保[!UICONTROL Total Sales]值現在準確地包含在CSV匯出中，恢復應用程式內報表與離線分析之間的一致性。 (TGT-53330)
* **改善未啟用量度時[!UICONTROL Graph View]的錯誤訊息。**&#x200B;修正VEC中，相關[!UICONTROL Graph View]報表套裝中未啟用要求的量度時，[!DNL Analytics]顯示一般「發生錯誤」訊息的問題。 此問題是由後端GraphQL回應中的`not_enabled_metric`錯誤所觸發。 此修正以較具資訊性的訊息取代模糊的錯誤，協助使用者識別[!DNL Analytics]中的設定問題，減少混淆和不必要的支援升級。 (TGT-53577)
* **修正報表期間超過支援90天限制的問題。**&#x200B;在[!UICONTROL Last X Days]區段中使用&quot;[!UICONTROL Reports]&quot;篩選的客戶能夠選取超過90天的期間，這可能會導致效能問題和資料不完整。 已更新篩選器以強制實施最多90天的範圍，確保一致且可靠的報表。 (TGT-53795)
* **修正使用預設環境（而非選取的環境）產生效能CSV報表的問題。**&#x200B;以往，當客戶變更報告設定中的環境並產生效能報告時，產生的CSV會包含來自預設環境的資料，而非選取的資料。  UI現在可正確傳遞`environmentId`引數，確保報表可反映所選環境。 此外，錯誤處理已得到改善。 如果CSV產生期間發生GraphQL錯誤，UI現在會顯示清楚的錯誤訊息，而不是產生空的CSV檔案。 (TGT-53064)
* **修正Analytics for Target (A4T)報告無法在[!UICONTROL Graph View]中顯示資料的問題。使用**&#x200B;搭配A4T整合的[!DNL Target]客戶在A/B測試活動的「報表」索引標籤中切換至圖表檢視時發生「發生錯誤」錯誤。 雖然[!UICONTROL Table View]已正確載入，[!UICONTROL Graph View]仍無法呈現所選時間範圍內的量度趨勢。 [!UICONTROL Graph View]現在會依預期顯示所有支援量度的效能資料，以在更新的UI中改善可見度和報告準確性。 (TGT-53573)

+++

**可視化體驗撰寫器 (VEC)**

+++檢視詳細資料
* **元素中繼資料現在會顯示在階層連結功能表的暫留中。**&#x200B;改善VEC中的階層連結功能表，以在暫留在專案上時顯示其他元素詳細資訊，例如ID、類別和名稱。 此增強功能可幫助使用者在活動設定期間更輕鬆地識別和區分元素。 (TGT-53409)
* **階層連結暫留現在會反白顯示VEC中的對應元素。**&#x200B;改善[!UICONTROL Visual Experience Composer]，在階層連結功能表中暫留專案時，在編輯器中反白顯示對應的元素。 也會顯示元素型別，例如容器、粗體文字或按鈕。 此行為會套用至同層級元素，並根據驗證清單排除不支援的型別，例如SVG。 (TGT-53411)
* **VEC修改工作流程中已還原未儲存的變更警示。**&#x200B;修正VEC中，使用者不再收到修改自訂程式碼時未儲存變更之通知的問題。 與舊版UI不同，新體驗在導覽離開或關閉個人化編輯器時缺少提示，這會導致意外的進度遺失。 此修正會還原所有修改型別的警報，包括自訂程式碼，並確保使用者在退出前收到警告而不儲存。 (TGT-53435)。
* **自訂程式碼變更現在會在VEC的頁面重新整理期間持續存在。**&#x200B;修正在VEC中，自訂程式碼修改在網站重新整理期間遺失的問題。 此問題發生在多次重新載入的頁面上，導致編輯器重設並回覆未儲存的變更。 此修正可確保自訂程式碼編輯作業在編輯期間即使頁面重新載入，仍會維持不變，避免意外失去進度。 (TTGT-53501)
* **VEC內網站存取的登入問題已解決。**&#x200B;修正使用者透過VEC存取網站時，無法登入網站的問題。 登入流程會反複將使用者重新導向回登入頁面，導致活動設定和預覽受阻。 此修正可確保VEC不再干擾登入行為，還原已驗證使用者的預期存取權。 (TGT-53524)
* VEC Helper擴充功能中已解決&#x200B;**個Cookie重複問題。**&#x200B;修正[!UICONTROL Adobe Experience Cloud Visual Editing Helper]擴充功能在通過預覽連結進行QA期間重複`at_qa_mode` Cookie的問題。 當手動切換預覽索引時，會建立多個具有跨網域衝突值的Cookie，以防止測試者可靠地切換變體。 在Target UI外部也觀察到此行為，並影響內部和使用者端帳戶。 此修正可防止重複專案並調整網域範圍，確保一致的Cookie處理，允許無縫的變體切換，而不需要手動Cookie清理。 (TGT-53579)
* **修正點選特定首頁上的元素造成記憶體流失的問題。**&#x200B;在此首頁上建立活動的客戶在與頁面元素互動時遭遇記憶體遺失。 此問題與過多主控台警告和增加子框架中的記憶體使用量有關，尤其是與格式錯誤的srcset屬性有關。 現在，記憶體使用在互動期間會保持穩定。 (TGT-53761)
* **修正VEC在載入特定活動時當機並顯示空白畫面的問題。**&#x200B;特定租使用者的客戶回報編輯器無法載入特定活動。 VEC在當機並顯示空白畫面之前，仍停留在「套用初始修改」上。 VEC現在會載入受影響的活動，而不會在更新的活動建立程式中發生錯誤。 (TGT-52932)
* **修正[!UICONTROL Manage Content]活動中的[!UICONTROL Automated Personalization]邊欄顯示不一致位置標籤的問題。**&#x200B;客戶回報[!UICONTROL Manage Content]邊欄在[!UICONTROL Experiences]和[!UICONTROL Offers]索引標籤中顯示不相符的位置編號。 （例如，體驗中的位置2和位置4，以及選件中的位置1和位置2），即使僅設定了兩個位置亦然。 位置標籤現在是一致的，並準確地對應到修改，提高了活動建立過程中的清晰度和可用性。 (TGT-52934)
* **修正VEC中修改在儲存後遺失的問題。**&#x200B;客戶回報在VEC中儲存修改後，頁面會重新整理並將變更還原到先前的版本。 此問題會導致最近一次的更新遺失，除非立即儲存整個活動。 修改現在會在儲存後正確持續存在，且編輯器不會再意外回覆變更，以確保活動建立工作流程中的可靠體驗。 (TGT-53500)
* **藉由在暫留和選取範圍上顯示元素型別，增強VEC中的元素選取範圍。**&#x200B;為了提高活動建立期間的可用性，VEC現在會在滑鼠懸停在上方或選取時，以HTML元素的型別加以裝飾。 此增強功能可協助客戶更輕鬆地辨識及選取正確的元素。 選取的元素會以不同顏色反白，而懸停的元素則會以藍色外框。 元素型別也會顯示，在編輯期間提供更清楚的上下文。 (TGT-53502)

+++

## 資料流更新（2025年9月19日）

[!DNL Adobe Target]個目的地連線的資料串流ID和沙箱組合必須是唯一的。

更新[!DNL Target]目的地連線的驗證邏輯，以強制執行IMS組織內的資料串流ID和沙箱名稱組合必須是唯一的。這表示：

* 相同的資料串流ID +沙箱名稱組無法在多個[!DNL Target]目的地連線中重複使用。
* 相同的資料串流ID只能用於不同的連線，前提是它們是在不同的沙箱中設定。
* 此規則適用於所有資料流選取專案，包括選取「無」時。

此更新可確保一致的設定，並防止多個沙箱環境之間發生衝突。 如需詳細資訊，請參閱[Adobe Target目的地](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/personalization/adobe-target-connection){target=_blank}指南中的&#x200B;*Experience Platform連線*。

## [!DNL Target Standard/Premium] 25.9.1 （2025年9月5日）

此版本包含下列更新和修正：

**[!UICONTROL Experience Fragments]**

+++檢視詳細資料
* **已改善[!UICONTROL AEM Experience Fragment]優惠方案的使用者歸因。**&#x200B;解決VEC中[!UICONTROL Last updated] (XF)選件的「[!UICONTROL AEM Experience Fragment]」欄位未正確顯示程式碼ID而非使用者名稱的問題。 在更新UI中選擇優惠期間發生這種差異，導致與舊版UI和HTML優惠不一致，後者正確顯示上次編輯者的名稱。 此修正可確保跨選件型別的使用者歸因一致，提高透明度並與預期行為一致。 (TGT-52880 和 TGT-52898)

+++

**Offer Decisioning**

+++檢視詳細資料
* 已解決ODE優惠的&#x200B;**優惠決定錯誤。**&#x200B;解決透過[!DNL Target]插入的優惠決定引擎(ODE)優惠由於缺少格式中繼資料而傳回400錯誤的問題。 錯誤訊息指出MIME型別為空，導致無法成功處理優惠決定。 此修正可確保正確處理優惠方案中繼資料、恢復個人化內容傳送的功能，並使行銷活動的執行不會受到干擾。 (TGT-53635)
* **ODS選件轉譯問題已解決。**&#x200B;解決在更新的UI中使用VEC建立活動時，透過[!DNL Offer Decision Service] (AJO)建立的[!DNL Adobe Journey Optimizer] (ODS)選件未呈現的問題。 舊版UI中的相同設定可正確運作，導致混淆並封鎖行銷活動執行。 此修正可確保兩個UI版本間提供一致的選件，還原AJO驅動個人化的預期行為。

+++

**報表**

+++檢視詳細資料
* **更新報告總覽UI的報告區段中已還原下載選項。**&#x200B;解決新的總覽UI中「報表」區段遺失[!UICONTROL Download]按鈕，導致使用者無法匯出屬性重要性分數的問題。 此更新會還原完整的匯出功能，簡化可下載資料的存取，以供分析和報告之用。 (TGT-53222)
* 已在&#x200B;**[!UICONTROL Download full CSV report]檢視中還原[!UICONTROL Important attributes]按鈕。**&#x200B;解決在更新的活動建立UI中，報告檢視的[!UICONTROL Download full CSV report]區段中缺少[!UICONTROL Important Attributes]按鈕的問題。 此修正可恢復對可下載深入分析的存取權，確保更新和舊版UI的功能一致。 (TGT-53238)
* **已解決影響更新總覽UI中[!UICONTROL Auto Target]報告的UI問題。**&#x200B;已修正更新總覽介面中影響[!UICONTROL Auto Target]活動報告的多個UI問題。 這些修正包括：

   * 摘要報表中缺少提升度和信賴度量度
   * 「建立的模型」核取方塊的顏色指示器不正確
   * 無功能圖表報告，儘管[!DNL Analytics]中有資料差異
   * 缺少[!UICONTROL Automated Segments]和[!UICONTROL Important Attributes]報告的下載連結
   * [!UICONTROL Automated Segments]報告顯示中斷

  這些修正會還原預期的報告行為，並提升在更新UI中[!UICONTROL Auto Target]效能的可見度。 (TGT-53484)

+++

**[!UICONTROL Visual Experience Composer]**

+++檢視詳細資料
* **已針對更新的UI中的引數存在條件更正表單驗證。**&#x200B;已解決更新UI中選取「[!UICONTROL Custom mbox parameter value is present]」或「[!UICONTROL Parameter is present]」錯誤地要求客戶輸入值的問題。 此行為與預期邏輯衝突，預期邏輯只會檢查引數是否存在，無論其值為何。 此修正使表單驗證與預期行為一致，可讓您更順暢地設定活動，並支援完全採用更新的UI。 (TGT-53638)
* **已針對頁面傳送中的引數顯示狀態規則修正表單邏輯。」**&#x200B;已解決在更新的UI中選取頁面傳送規則（例如&quot;[!UICONTROL Parameter is present]&quot;、&quot;[!UICONTROL Parameter is not present]&quot;、&quot;[!UICONTROL Parameter value is present]&quot;或&quot;[!UICONTROL Parameter value is not present]&quot;）時，不正確地要求使用者輸入其他引數值的問題。 此行為與舊版UI不一致，且與在不指定值的情況下偵測引數存在的預期邏輯相衝突。 此修正可還原預期的規則設定行為，簡化活動設定並改善可用性。 (TGT-53640)
* 在更新的UI中，多頁規則產生器的&#x200B;**驗證邏輯已改善。**&#x200B;已解決更新UI中多頁規則產生器的多個驗證問題。 這些修正包括：

   * 當mbox引數為空時防止建立規則
   * 顯示無效規則狀態的適當錯誤訊息
   * 更正不需要運算元值的一元運運算元和以引數為基礎的運運算元的驗證邏輯
   * 透過還原儲存功能啟用含一元運運算元的雜湊片段規則

  這些更新可確保精確的規則設定，並提升複雜頁面傳送情境中的可用性。 (TGT-53722)
* **在A/B和MVT活動中已解決的位置重新命名問題。**&#x200B;修正更新UI中重新命名[!UICONTROL A/B Test]或[!UICONTROL Multivariate Test] (MVT)活動中的位置在位置清單、目標定位與返回之間導覽後未持續存在的錯誤。 此更新可確保儲存位置名稱變更，並在整個活動工作流程中一致地反映這些變更。 (TGT-52367)
* **已在更新的UI中修正MVT和AP活動的位置名稱持續性。**&#x200B;已解決在更新的UI中，[!UICONTROL Multivariate Test] (MVT)和[!UICONTROL Automated Personalization] (AP)活動中編輯的位置名稱未正確儲存的問題。 重新命名位置後，在標籤（例如[!UICONTROL Targeting]和[!UICONTROL Experiences]）之間導覽，導致名稱恢復為先前的狀態。 此修正可確保各索引標籤的位置命名一致，並改善活動設定期間的可靠性。 (TGT-52927)
* **已在MVT活動的「管理體驗」面板中修正位置標籤。**&#x200B;已解決更新UI中，[!UICONTROL Manage Experiences] (MVT)活動中的[!UICONTROL Multivariate Test]面板顯示不一致位置編號的問題。 此修正可確保位置標籤順序且正確與使用者定義的修改一致，進而在體驗設定期間提高清晰度和可用性。 (TGT-52929)

+++

## 額外的發行說明和版本詳細資料

| 資源 | 詳細資料 |
|--- |--- |
| [發行說明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hant) | 有關 Platform Web SDK 各版本變更的詳細資料。 |
| [at.js 版本詳細資料](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 有關 [!DNL Adobe Target] at.js JavaScript 程式庫每個版本中的變更的詳細資料。 |

## 文件變更、過去的發行說明和 Experience Cloud 發行說明

除了每次發行的說明，下列資源也提供額外資訊:

| 資源 | 詳細資料 |
|--- |--- |
| [文件變更](/help/main/r-release-notes/doc-change.md) | 檢視本指南未包含在這些發行說明中的更新詳細資訊。 |
| [舊版發行說明](/help/main/r-release-notes/release-notes-for-previous-releases.md)。 | 檢視舊版 Target Standard 和 Target Premium 中新功能和增強功能的詳細資訊。 |
| [Adobe Experience Cloud發行說明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html){target=_blank} | 檢視 Adobe Experience Cloud 解決方案的最新發行說明。 |

## 搶鮮版版本資訊 {#section_5D588F0415A2435B851A4D0113ACA3A0}

以下資源告訴您下個 Target 版本將推出哪些功能。

| 資源 | 詳細資料 |
|--- |--- |
| [Adobe 優先產品更新](https://www.adobe.com/tw/subscription/priority-product-update.html){target=_blank} | 收到對 [!DNL Target] 以及其他 [!DNL Adobe Experience Cloud] 解決方案未來產品增強功能的提前通知。 |
| [Target 發行說明 - 搶鮮版](/help/main/r-release-notes/target-release-notes.md){target=_blank} | 有關當月 Target 版本的資訊，包括搶鮮版資訊。 |
