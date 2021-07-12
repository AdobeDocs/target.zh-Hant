---
keywords: 可視化體驗撰寫器； VEC；預設URL；增強體驗撰寫器； EEC；混合內容；體驗快照；行動檢視區； CSS; CSS選取器
description: 了解如何透過指定Adobe的一般設定、行動檢視區設定和CSS選取器來設定體驗 [!DNL Target] 可視化體驗撰寫器(VEC)。
title: 如何設定可視化體驗撰寫器(VEC)?
feature: 管理與設定
role: Admin
exl-id: cf6c9ece-6745-477e-81ac-a3e9a9fddb09
source-git-commit: be7b5478006af231aae2b78e4a8c0066e3cb4a5b
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 50%

---

# 設定 Visual Experience Composer

指定其一般設定、行動檢視區設定和CSS選取器，以設定[!DNL Adobe Target] [!UICONTROL 可視化體驗撰寫器](VEC)。

若要存取[!UICONTROL 可視化體驗撰寫器]設定頁面，請按一下&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 可視化體驗撰寫器]。**

>[!NOTE]
>
>請注意，此頁上的設定會套用至整個[!DNL Target]帳戶。

![可視化體驗撰寫器設定頁面](/help/administrating-target/assets/vec.png)

## 一般設定

您可以為可視化體驗撰寫器指定一般設定。

![一般設定區段](/help/administrating-target/assets/general-settings.png)

可使用下列設定:

### 預設URL

設定[!UICONTROL 可視化體驗撰寫器]所使用的預設 URL。這是每當您為每個新增活動設定體驗時會使用的預設頁面 (例如您的首頁)。如果您不設定預設的 URL，則必須在建立活動時，為每個活動輸入 URL。

### 啟用增強體驗撰寫器 {#eec}

允許在 iframe-busting 網站以及含有混合內容的網站上編輯。某些網站可能與增強版本不相容。 取消選取此選項，將還原為原始的[!UICONTROL 可視化體驗撰寫器]。 此選擇不會影響網站上的活動傳送。

如需詳細資訊，請參閱[疑難排解可視化體驗撰寫器](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)。

您也可以在活動層級啟用[!UICONTROL 增強體驗撰寫器]。

### 載入混合內容

使用[!UICONTROL 增強體驗撰寫器](EEC)開啟網站時啟用混合內容。 啟用此選項可避免透過[!DNL Target]代理伺服器載入靜態資源時的額外負荷。

例如，如果下列情況，此選項會很實用：

* 您的內容安全性原則(CSP)標頭允許載入混合內容，而無須使用Proxy伺服器並啟用EEC。
* HTTP網站在EEC中的載入時間會增加，其中JavaScript、影像等內容透過Proxy載入需要較長時間。

### 在活動流程圖表中產生體驗快照

啟用體驗快照會在活動工作流程圖表中產生您的體驗的縮圖。停用快照可能對部分使用者造成較快速的效能。

## ![Premium徽](/help/assets/premium.png) 章行動檢視區設定

您可以新增裝置以在預覽體驗時使用。每個裝置有相關聯的對象。

![「行動檢視區設定」區段](/help/administrating-target/assets/mobile-viewport-configuration.png)

按一下「**[!UICONTROL 新增]**」，為行動檢視區指定描述性名稱、指定寬度和高度、選取所需的作業系統，然後按一下「[!UICONTROL 儲存]」。

如需如何新增行動檢視區的詳細資訊，請參閱[行動檢視區設定](/help/c-experiences/c-visual-experience-composer/mobile-viewports.md)。

## CSS 選取器 {#css}

指定 [!DNL Target] 如何產生 CSS 選取器。

![「CSS選取器」區段](/help/administrating-target/assets/css-selectors.png)

這些選項可幫助 [!DNL Target] 瞭解您網站的結構，以為內容傳送產生更好的 CSS 選取器。依預設，[!DNL Target] 會根據頁面上的元素 ID 產生選取器。如果您的網站在相同頁面上使用一些 ID 或重複的 ID，那麼，使用類別可能是較好的選項。

您可以選擇以下的一或兩個選項:

### 使用元素 ID

如果將相同的 ID 用於多個元素，或如果元素 ID 可能在頁面載入時變更，請取消選取此選項。

### 使用元素類別

依預設，[!DNL Target] 僅使用元素 ID。不過，如果您的頁面的設計是要使用類別來識別元素 (例如使用 [!DNL Adobe Experience Manager] 建立的頁面)，您也應該選取[!UICONTROL 「使用元素類別」]。

>[!NOTE]
>
>雖然您已完成各項動作來確保準確性，請注意，使用類別可能會導致錯誤。 如果您不選取這兩個選項中的一個，準確性也會受到影響。準確性的順序為: ID > 類別 > 兩個選項皆不選取。請務必測試您的頁面以確定選取器皆正確。

您可以根據每個活動覆寫此設定 (按一下「設定」齒輪圖示，然後選取[!UICONTROL 「CSS 選取器」])。如果您有多個設定方式不同的網站，這特別實用。

>[!NOTE]
>
>在[!UICONTROL Automated Personalization]和[!UICONTROL Multivariate Testing]活動中，不能針對每個活動覆寫設定。  如需選取器的其他資訊，請參閱[可視化體驗撰寫器中使用的元素選取器](/help/c-experiences/c-visual-experience-composer/vec-selectors.md)。

## 訓練影片：帳戶首選項(7:33) ![概述徽章](/help/assets/overview.png)

此影片包括關於帳戶偏好設定的資訊。

* 說明 中可用的帳戶設定[!DNL Target Standard]

>[!NOTE]
>
>已重新設計[!DNL Target] [!UICONTROL Administration]功能表UI（原稱[!UICONTROL Setup]），以提供改善的效能、減少發行新功能時所需的維護時間，並改善整個產品的使用者體驗。 以下視頻中的資訊通常正確；不過，選項可能位於稍微不同的位置。 更新的影片即將發佈。

>[!VIDEO](https://video.tv.adobe.com/v/17379)
