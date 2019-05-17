---
description: 設定您的帳戶偏好設定以設定 Target Standard 或 Target Premium 以便正確對您的帳戶運作。
keywords: 帳戶偏好設定; 偏好設定; 網站詳情; 自訂 mbox 名稱; 用於報表的 Experience Cloud 解決方案; 顯示預估收入提升度; CSS 選取器; 使用元素類別; 預設可視化體驗撰寫器 URL; 啟用增強體驗撰寫器; 產生體驗快照; 行動檢視區設定; 垂直產業; 篩選不相容的條件
seo-description: 設定帳戶偏好設定，設定Adobe Target Standard或Target Premium可正確搭配您的帳戶運作。
seo-title: 偏好設定
solution: Target
subtopic: 快速入門
title: 偏好設定
topic: Standard
uuid: ed3904c8-533b-4b9c-a3a1-079c61b1bf2a
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# 偏好設定{#preferences}

設定您的帳戶偏好設定來設定 [!DNL Target Standard] 或 [!DNL Target Premium] 以便對您的帳戶正確運作。

若要設定您的帳戶偏好設定，請按一下**[!UICONTROL 「設定]** &gt; **[!UICONTROL 偏好設定」]**，視需要設定您的偏好設定，然後按一下**[!UICONTROL 「提交」]**。

下圖顯示[!UICONTROL 「帳戶偏好設定」]頁面上可用的設定。

![偏好設定頁面](/help/administrating-target/r-target-account-preferences/assets/target-account-preferences.png)

>[!NOTE]
>
>只有當您擁有 [Target Premium](/help/c-intro/intro.md#premium)時，才能使用其中一些偏好設定。

## 網站詳情 {#section_04A3340FC29B46978DB77058259F4EE0}

指定您的網站設定的方式。

### 自訂全域 Mbox

選取您用來傳送 [!DNL Target] 活動的選用自訂 mbox 名稱。此全域 mbox 必須為空白，表示它沒有預設內容。只有在您的網站上安裝更新 [!DNL at.js] 或 [!DNL mbox.js] 檔案後，才會儲存此設定。

>[!CAUTION]
>
>錯誤地設定此設定可能會導致現有活動中斷。

## 結果和報表 {#section_47C887AABD704A96BCD1C00BEABF4BCE}

設定可決定用於您的結果和報表資料的選項。

| 選項 | 說明 |
|--- |--- |
| 用於報表的 Experience Cloud 解決方案 | 選取您的活動的報表來源，可以是 [!DNL Target] 或 Adobe Analytics。您也可以選擇根據活動選取您的報表來源。選擇報表來源時，請考量下列資訊:<ul><li>無論選取的報表來源為何，均可建立、啟用和停用[!UICONTROL 「自動分配」]、[!UICONTROL 「自動鎖定目標」]和[!UICONTROL 「自動個人化」](AP) 活動。選擇 [Adobe Analytics 當作 Adobe Target (A4T) 的報表來源](/help/c-integrating-target-with-mac/a4t/a4t.md)時，不支援前述活動類型。即便指定 Analytics 當作報表來源，前述活動類型也會使用 [!DNL Target] 當作報表來源。</li><li>如果在此將報表來源設為「Analytics」，便不得啟用將 [!DNL Target] 作為報表來源的活動 (根據活動，報表來源指定為 Target)。您必須在活動中將報表來源變更為「Analytics」，或在「設定 &gt; 偏好設定」中將報表引擎變更為「根據活動選取」。</li><li>如果在此將報表來源設為[!DNL Target]「」，便不得啟用將「Analytics」當作報表來源的活動。您必須在活動中將報表來源變更為[!DNL Target]「」，或在「設定 &gt; 偏好設定」中將報表來源變更為「根據活動選取」。</li><li>如果在此將報表來源設為「根據活動選取」，您就可建立、啟用和停用所選報表來源支援的活動。如需支援活動的表格，請參閱 [](/help/c-integrating-target-with-mac/a4t/a4t.md)Adobe Analytics 作為 Adobe Target (A4T) 的報表來源。</li><li>從「A/B 手動」切換為[!UICONTROL 「自動分配」]或[!UICONTROL 「自動鎖定目標」]時，如果[!UICONTROL 「自動分配」]或[!UICONTROL 「自動鎖定目標」]活動不支援「A/B 手動」活動的報表來源，所有量度和報表對象都會消失。</li></ul> |
| 顯示預估提升收益 | 如果為您的目標輸入了貨幣值，您也可以選擇顯示預估提升收益。[!DNL Target]如果所有使用者要瞭解成功的藍圖， 可以估計您可能獲得的收入增益。預估提升度功能依預設會停用。<br>只有 Experience Cloud 管理員使用者可以啟用或停用此功能。如果已停用預估的提升度，則介面中不會出現對應的欄位。停用功能不會造成資料遺失，包括用於預估的資料。預估是根據收集的資料，而無論功能是否已啟用。<br>如需詳細資訊，請參閱 [預估收入中的提升度](/help/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md)。 |
| 啓用精細的優先順序 | 允許優先順序範圍從0-999的數字輸入。<br>視您的設定而定，優先順序的 UI 和選項可能有所不同。您可以使用低、中或高的舊版設定，或是您可以從 0 到 999 啟用微調優先順序。<br>如果將多個活動指派至具有相同對象的相同位置，則會使用優先順序。如果將兩個以上活動指派至位置，則會顯示具有最高優先順序的活動。 |

## CSS 選取器 {#section_8155EDBF449E4198863235F94D1EA872}

指定 [!DNL Target] 如何產生 CSS 選取器。

這些選項可幫助 [!DNL Target] 瞭解您網站的結構，以為內容傳送產生更好的 CSS 選取器。依預設，[!DNL Target] 會根據頁面上的元素 ID 產生選取器。如果您的網站在相同頁面上使用一些 ID 或重複的 ID，那麼，使用類別可能是較好的選項。

您可以選擇以下的一或兩個選項:

| 選項 | 說明 |
|--- |--- |
| 使用元素 ID | 如果將相同的 ID 用於多個元素，或如果元素 ID 可能在頁面載入時變更，請取消選取此選項。 |
| 使用元素類別 | 依預設，[!DNL Target] 僅使用元素 ID。不過，如果您的頁面的設計是要使用類別來識別元素 (例如使用 [!DNL Adobe Experience Manager] 建立的頁面)，您也應該選取[!UICONTROL 「使用元素類別」]。<br>**注意**: 雖然您已完成各個項目來確保準確性，請注意使用類別可能造成錯誤。如果您不選取這兩個選項中的一個，準確性也會受到影響。準確性的順序為: ID &gt; 類別 &gt; 兩個選項皆不選取。請務必測試您的頁面以確定選取器皆正確。<br>[!UICONTROL ]您可以根據每個活動覆寫此設定 (按一下「設定」齒輪圖示，然後選取[!UICONTROL 「CSS 選取器」])。如果您有多個設定方式不同的網站，這特別實用。<br>**注意**: 在[!UICONTROL 「自動個人化」]和[!UICONROL 「多變數測試」]活動中，不可根據活動使用覆寫設定。如需選取器的其他資訊，請參閱[可視化體驗撰寫器中使用的元素選取器](/help/c-experiences/c-visual-experience-composer/vec-selectors.md)。 |

## 可視化體驗撰寫器 {#section_CD9BDD372CF54E678F88E8BA95757A5A}

| 選項 | 說明 |
|--- |--- |
| 預設可視化體驗撰寫器 URL | 設定[!UICONTROL 可視化體驗撰寫器]所使用的預設 URL。這是每當您為每個新增活動設定體驗時會使用的預設頁面 (例如您的首頁)。如果您不設定預設的 URL，則必須在建立活動時，為每個活動輸入 URL。 |
| 啟用增強體驗撰寫器 | 允許在 iframe-busting 網站以及含有混合內容的網站上編輯。部分網站可能與加強的版本不相容。取消勾選此選項以還原至原始的體驗撰寫器。此選擇不會影響網站上的活動傳送。<br>如需詳細資訊，請參閱[疑難排解可視化體驗撰寫器](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)。<br>**注意**: 您也可以在活動層級啟用增強體驗撰寫器。 |
| 載入混合內容 | 使用增強的Experience Composer開啓網站時，啓用混合內容。啓用此選項可避免透過Target Proxy伺服器載入靜態資源的額外負荷。 |
| 產生體驗快照 | 啟用體驗快照會在活動工作流程圖表中產生您的體驗的縮圖。停用快照可能對部分使用者造成較快速的效能。 |

## 行動檢視區組態 {#section_42176D062BCE4A28ADBB784CC4BEF84D}

您可以新增裝置以在預覽體驗時使用。每個裝置有相關聯的對象。

| 選項 | 說明 |
|--- |--- |
| ![Premium 徽章](/help/assets/premium.png) 新增 | 按一下[!UICONTROL 「新增」]，為行動檢視區指定描述性的名稱、指定寬度和高度、選取需要的作業系統，然後按一下[!UICONTROL 「儲存」]。如需如何新增行動檢視區的詳細資訊，請參閱[行動檢視區設定](/help/c-experiences/c-visual-experience-composer/mobile-viewports.md)。 |

## 訓練影片: 帳戶偏好設定 (7:33)

此影片包括關於帳戶偏好設定的資訊。

* 說明 中可用的帳戶設定[!DNL Target Standard]

>[!VIDEO](https://video.tv.adobe.com/v/17379)