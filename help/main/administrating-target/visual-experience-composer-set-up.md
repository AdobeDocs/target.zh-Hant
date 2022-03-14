---
keywords: 視覺體驗合成器；vec;default url;enhanced experience composer;eec;mixed content;experience snapshots;mobile viewport;css;css;selectors
description: 瞭解如何配置Adobe [!DNL Target] 通過指定Visual Experience Composer(VEC)的常規設定、移動視區配置和CSS選擇器。
title: 如何配置Visual Experience Composer(VEC)?
feature: Administration & Configuration
role: Admin
exl-id: cf6c9ece-6745-477e-81ac-a3e9a9fddb09
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '717'
ht-degree: 50%

---

# 設定可視化體驗撰寫器

配置 [!DNL Adobe Target] [!UICONTROL 視覺體驗作曲家] (VEC)，方法是指定其常規設定、移動視區配置和CSS選擇器。

訪問 [!UICONTROL 視覺體驗作曲家] 配置頁，按一下 **[!UICONTROL 管理]** > **[!UICONTROL 視覺體驗作曲家]。**

>[!NOTE]
>
>請注意，此頁上的設定應用於整個 [!DNL Target] 帳戶。

![「Visual Experience Composer配置」頁](/help/main/administrating-target/assets/vec.png)

## 一般設定

可以為Visual Experience Composer指定常規設定。

![「常規設定」部分](/help/main/administrating-target/assets/general-settings.png)

可使用下列設定:

### 預設URL

設定[!UICONTROL 可視化體驗撰寫器]所使用的預設 URL。這是每當您為每個新增活動設定體驗時會使用的預設頁面 (例如您的首頁)。如果您不設定預設的 URL，則必須在建立活動時，為每個活動輸入 URL。

### 啟用增強體驗撰寫器 {#eec}

允許在 iframe-busting 網站以及含有混合內容的網站上編輯。某些站點可能與增強版本不相容。 取消選擇此選項可恢復為原始 [!UICONTROL 視覺體驗作曲家]。 此選擇不會影響網站上的活動傳送。

如需詳細資訊，請參閱[疑難排解可視化體驗撰寫器](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)。

您還可以 [!UICONTROL 增強的體驗作曲家] 在活動級別。

### 載入混合內容

使用 [!UICONTROL 增強的體驗作曲家] （歐共體）。 啟用此選項可避免通過 [!DNL Target] 代理伺服器。

例如，如果：

* 您的內容安全策略(CSP)標頭允許載入混合內容，而不使用啟用了EEC的代理伺服器。
* 您的HTTP網站在EEC中面臨載入時間的增加，其中JavaScript、映像等通過代理載入需要較長時間。

### 在活動流程圖中生成體驗快照

啟用體驗快照會在活動工作流程圖表中產生您的體驗的縮圖。停用快照可能對部分使用者造成較快速的效能。

## ![高級徽章](/help/main/assets/premium.png) 移動視區配置

您可以新增裝置以在預覽體驗時使用。每個裝置有相關聯的對象。

![「移動視區配置」部分](/help/main/administrating-target/assets/mobile-viewport-configuration.png)

按一下 **[!UICONTROL 添加]**，為移動視區指定描述性名稱，指定寬度和高度，選擇所需的作業系統，然後按一下 [!UICONTROL 保存]。

如需如何新增行動檢視區的詳細資訊，請參閱[行動檢視區設定](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md)。

## CSS 選取器 {#css}

指定 [!DNL Target] 如何產生 CSS 選取器。

![「CSS選擇器」部分](/help/main/administrating-target/assets/css-selectors.png)

這些選項可幫助 [!DNL Target] 瞭解您網站的結構，以為內容傳送產生更好的 CSS 選取器。依預設，[!DNL Target] 會根據頁面上的元素 ID 產生選取器。如果您的網站在相同頁面上使用一些 ID 或重複的 ID，那麼，使用類別可能是較好的選項。

您可以選擇以下的一或兩個選項:

### 使用元素 ID

如果將相同的 ID 用於多個元素，或如果元素 ID 可能在頁面載入時變更，請取消選取此選項。

### 使用元素類別

依預設，[!DNL Target] 僅使用元素 ID。不過，如果您的頁面的設計是要使用類別來識別元素 (例如使用 [!DNL Adobe Experience Manager] 建立的頁面)，您也應該選取[!UICONTROL 「使用元素類別」]。

>[!NOTE]
>
>儘管已做了一切來確保準確性，但請注意，使用類會導致錯誤。 如果您不選取這兩個選項中的一個，準確性也會受到影響。準確性的順序為: ID > 類別 > 兩個選項皆不選取。請務必測試您的頁面以確定選取器皆正確。

您可以根據每個活動覆寫此設定 (按一下「設定」齒輪圖示，然後選取[!UICONTROL 「CSS 選取器」])。如果您有多個設定方式不同的網站，這特別實用。

>[!NOTE]
>
>覆蓋每個活動的設定在中不可用 [!UICONTROL Automated Personalization] 和 [!UICONTROL Multivariate Testing] 活動。  如需選取器的其他資訊，請參閱[可視化體驗撰寫器中使用的元素選取器](/help/main/c-experiences/c-visual-experience-composer/vec-selectors.md)。

## 培訓視頻：帳戶首選項(7:33) ![概述徽章](/help/main/assets/overview.png)

此影片包括關於帳戶偏好設定的資訊。

* 說明 中可用的帳戶設定[!DNL Target Standard]

>[!NOTE]
>
>的 [!DNL Target] [!UICONTROL 管理] 菜單UI（以前） [!UICONTROL 設定])已重新設計，以提供改進的效能，減少發佈新功能時所需的維護時間，並改善整個產品的用戶體驗。 以下視頻中的資訊一般是正確的；但是，選項可能位於稍有不同的位置。 更新的視頻將很快發佈。

>[!VIDEO](https://video.tv.adobe.com/v/17379)
