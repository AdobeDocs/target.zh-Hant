---
keywords: visual experience composer;vec;default url;enhanced experience composer;eec;mixed content;experience snapshots;mobile viewport;css;css selectors
description: 指定Adobe Target Visual Experience Composer(VEC)的一般設定、行動檢視埠設定和CSS選擇器，以設定Adobe Target Visual Experience Composer(VEC)。
title: 設定Adobe Target Visual Experience Composer
feature: null
topic: Standard
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '694'
ht-degree: 51%

---


# 設定視覺體驗撰寫器

透過指 [!DNL Adobe Target] 定其一般設定、行動檢視埠設定和CSS選擇器，來設定Visual Experience Composer  (VEC)。

若要存取「 [!UICONTROL Visual Experience Composer] 」設定頁面，請按一下「 **[!UICONTROL 管理]** > **[!UICONTROL Visual Experience Composer」]。**

>[!NOTE]
>
>請注意，此頁面上的設定會套用至整個帳 [!DNL Target] 戶。

![「Visual Experience Composer」配置頁](/help/administrating-target/assets/vec.png)

## 一般設定

您可以指定Visual Experience Composer的一般設定。

![「常規設定」部分](/help/administrating-target/assets/general-settings.png)

可使用下列設定:

### 預設URL

設定[!UICONTROL 可視化體驗撰寫器]所使用的預設 URL。這是每當您為每個新增活動設定體驗時會使用的預設頁面 (例如您的首頁)。如果您不設定預設的 URL，則必須在建立活動時，為每個活動輸入 URL。

### 啟用增強體驗撰寫器

允許在 iframe-busting 網站以及含有混合內容的網站上編輯。有些網站可能與增強版不相容。 Deselect this option to revert to the original [!UICONTROL Visual Experience Composer]. 此選擇不會影響網站上的活動傳送。

如需詳細資訊，請參閱[疑難排解可視化體驗撰寫器](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)。

You can also enable the [!UICONTROL Enhanced Experience Composer] at the activity level.

### 載入混合內容

Enable mixed content while opening a website using the [!UICONTROL Enhanced Experience Composer] (EEC). Enabling this option avoids the extra overhead of loading static resources via [!DNL Target] proxy servers.

例如，如果：

* 您的內容安全性政策(CSP)標題允許載入混合內容，而不需使用啟用EEC的代理伺服器。
* 在EEC中，HTTP網站的載入時間會增加，其中JavaScript、影像等需要較長的時間才能透過proxy載入。

### 在活動流程圖中生成體驗快照

啟用體驗快照會在活動工作流程圖表中產生您的體驗的縮圖。停用快照可能對部分使用者造成較快速的效能。

## ![Premium badge](/help/assets/premium.png) Mobile Viewport設定

您可以新增裝置以在預覽體驗時使用。每個裝置有相關聯的對象。

![「移動視區配置」部分](/help/administrating-target/assets/mobile-viewport-configuration.png)

Click **[!UICONTROL Add]**, specify a descriptive name for the mobile viewport, specify the width and height, select the desired operating system, then click [!UICONTROL Save].

如需如何新增行動檢視區的詳細資訊，請參閱[行動檢視區設定](/help/c-experiences/c-visual-experience-composer/mobile-viewports.md)。

## CSS 選取器 {#css}

指定 [!DNL Target] 如何產生 CSS 選取器。

![「CSS選擇器」區段](/help/administrating-target/assets/css-selectors.png)

這些選項可幫助 [!DNL Target] 瞭解您網站的結構，以為內容傳送產生更好的 CSS 選取器。依預設，[!DNL Target] 會根據頁面上的元素 ID 產生選取器。如果您的網站在相同頁面上使用一些 ID 或重複的 ID，那麼，使用類別可能是較好的選項。

您可以選擇以下的一或兩個選項:

### 使用元素 ID

如果將相同的 ID 用於多個元素，或如果元素 ID 可能在頁面載入時變更，請取消選取此選項。

### 使用元素類別

依預設，[!DNL Target] 僅使用元素 ID。不過，如果您的頁面的設計是要使用類別來識別元素 (例如使用 [!DNL Adobe Experience Manager] 建立的頁面)，您也應該選取[!UICONTROL 「使用元素類別」]。

>[!NOTE]
>
>儘管已做了一切來確保正確性，但請注意，使用類會導致錯誤。 如果您不選取這兩個選項中的一個，準確性也會受到影響。準確性的順序為: ID > 類別 > 兩個選項皆不選取。請務必測試您的頁面以確定選取器皆正確。

您可以根據每個活動覆寫此設定 (按一下「設定」齒輪圖示，然後選取[!UICONTROL 「CSS 選取器」])。如果您有多個設定方式不同的網站，這特別實用。

>[!NOTE]
>
>Overriding the setting per activity is not available in [!UICONTROL Automated Personalization] and [!UICONTROL Multivariate Testing] activities.  如需選取器的其他資訊，請參閱[可視化體驗撰寫器中使用的元素選取器](/help/c-experiences/c-visual-experience-composer/vec-selectors.md)。

## 訓練影片：帳戶偏好設定(7:33)概 ![觀徽章](/help/assets/overview.png)

此影片包括關於帳戶偏好設定的資訊。

* 說明 中可用的帳戶設定[!DNL Target Standard]

>[!NOTE]
>
>「管 [!DNL Target] 理」功能表UI(舊稱 [!UICONTROL Setup])已重新設計，以提供改善的效能、減少發佈新功能時所需的維護時間，並改善整個產品的使用體驗。 以下視頻中的資訊通常正確；不過，選項可能位於稍微不同的位置。 更新的影片將很快發佈。

>[!VIDEO](https://video.tv.adobe.com/v/17379)
