---
keywords: 混合式內容;安全;不安全;chrome;疑難排解;vec;視覺體驗撰寫器;不安全;http;https;firefox;internet explorer
description: 如果安全的內容與不安全的內容混合，則某些瀏覽器會封鎖頁面的顯示。 了解如何在 Chrome、Firefox 和 Edge 中啟用混合式內容。
title: 如何在我的瀏覽器中啟用混合式內容？
feature: Visual Experience Composer (VEC)
exl-id: a2209af6-65e5-427e-b2cb-53b803728ef3
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: ht
source-wordcount: '588'
ht-degree: 100%

---

# 在您的瀏覽器中啟用混合式內容

如果最初的要求是透過 HTTPS 的安全內容，但載入了 HTTPS *和* HTTP 內容來顯示網頁，則會發生混合式內容。 HTTPS 內容是安全的。 HTTP 內容是不安全的。

如果安全內容與不安全內容混合，新型瀏覽器可能會封鎖頁面的顯示或顯示警告訊息。

如果 [!DNL Target] 中的[!UICONTROL 視覺體驗撰寫器] (VEC) 嘗試開啟包含混合式內容的頁面，則會顯示警告訊息。 此訊息會通知您如何在瀏覽器中停用封鎖功能。 停用封鎖功能可讓您開啟 HTTP 網站或具有混合式呼叫 (HTTPS 和 HTTP) 的網站。

![混合式內容警告](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/mixed_content_warning.png)

先前雖然不允許混合式內容，但是當您在建立活動時，仍可在三步驟引導式工作流程的步驟 1 執行一些動作。 [!DNL Target] 現在禁止在步驟 1 執行動作。 出現此訊息時，您必須啟用混合式內容才能繼續建立活動。

瀏覽器的安全性設定可能會封鎖混合式內容或不安全 (HTTP) 內容，使其無法載入到安全 (HTTPS) 頁面或頁框 (例如 VEC)。 如果您不想停用瀏覽器的安全性設定，您必須擁有 HTTPS 網站。

如果您的網站在不安全 (HTTP) 網域中運作，您需要允許 VEC 載入使用中的混合式內容。

>[!NOTE]
>
>允許混合式內容只會影響 VEC，不影響已上線的網站。

如需詳細資訊，請參閱 *Mozilla Developer Network* (MDN) 網站上的[混合式內容](https://developer.mozilla.org/en-US/docs/Web/Security/Mixed_content)。

## 在 Google Chrome 中啟用混合式內容 {#task_FF297A08F66E47A588C14FD67C037B3A}

如果您透過安全連線造訪網站，Chrome 將會驗證網頁上的內容是否已安全地傳輸。

請參閱 Google Chrome 說明中的「[此頁面有不安全的內容](https://support.google.com/chrome/answer/1342714?hl=en)」。

如果您正在搭配最新版 Chrome (版本 79.0.3945.117 或更新版本) 使用 VEC，您必須更新網站設定。 您網站的訪客不需要完成這些步驟。

1. 按一下掛鎖 (警告) 圖示，然後按一下&#x200B;**[!UICONTROL 網站設定]**。

   ![網站設定](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/site-settings.png)

1. 捲動到&#x200B;**[!UICONTROL 不安全內容]**，然後使用下拉式清單將「封鎖 (預設)」變更為「允許」。

   ![不安全內容](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/insecure-content.png)

1. 重新載入 VEC 頁面。

## 在 Mozilla Firefox 中啟用混合式內容 {#task_5448763B8DC941FD80F84041AEF0A14D}

根據預設，Firebox 會封鎖混合了安全和不安全內容的頁面。 若要使用 [!DNL Target]，建議您永久變更此設定。 您網站的訪客不需要完成這些步驟。

1. 在 Firefox 的位址列中，輸入 `about:config`。
1. 認可 Firefox 顯示的警告訊息。

   ![Firefox 警告](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox.png)

1. 在搜尋列中，輸入 `block_active`。

   ![Firefox block_active 設定](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox3.png)

1. 按兩下 ` **[!UICONTROL security.mixed_content.block_active_content]**`。

   值會從「True」變更為「False」。當值顯示「False」時，就表示完成了。

   ![Firefox 安全性](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox2.png)

在變更此設定後，請重新啟動電腦。

## 在 Microsoft Edge 中啟用混合式內容

如果您透過安全連線造訪網站，Edge 將會驗證網頁上的內容是否已安全地傳輸。

如果您正在搭配最新版 Edge 使用 VEC，您必須更新網站設定。 您網站的訪客不需要完成這些步驟。

1. 按一下掛鎖 (警告) 圖示，然後按一下&#x200B;**[!UICONTROL 網站權限]**。

   ![Microsoft Edge 中的網站權限](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/ms-edge.png)

1. 捲動到&#x200B;**[!UICONTROL 不安全內容]**&#x200B;然後使用下拉式清單將「封鎖 (預設)」變更為「允許」。

   ![不安全內容](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/ms-edge-2.png)

1. 重新載入 VEC 頁面。
