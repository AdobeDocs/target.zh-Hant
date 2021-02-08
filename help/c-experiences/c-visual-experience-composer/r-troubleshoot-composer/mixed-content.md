---
keywords: 混合內容；安全；不安全；chrome；疑難排解；vec；視覺體驗撰寫器；不安全；http;https;firefox;internet explorer
description: 如果安全的內容與不安全的內容混合，則某些瀏覽器會封鎖頁面的顯示。瞭解如何在Chrome、Firefox和Edge中啟用混合內容。
title: 如何在瀏覽器中啟用混合內容？
feature: Visual Experience Composer (VEC)
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 34%

---


# 在瀏覽器中啟用混合內容

如果同時載入HTTPS（安全）*和* HTTP（不安全）內容以顯示相同的網頁，且初始要求在HTTPS上是安全的，則會發生混合內容。

如果安全內容與不安全內容混合，現代瀏覽器可能會封鎖頁面顯示或顯示警告訊息。

如果[!DNL Target]中的[!UICONTROL Visual Experience Composer](VEC)嘗試開啟包含混合內容的頁面，會顯示訊息，指出如何停用瀏覽器中的封鎖功能，以便您開啟HTTP網站或具有混合呼叫（HTTPS和HTTP）的網站。

![混合內容警告](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/mixed_content_warning.png)

以前，雖然不允許混合內容，但您在建立活動時，仍可在三步驟引導式工作流程的步驟 1 中執行一些動作。[!DNL Target] 現在禁止在步驟 1 執行動作。顯示此訊息時，您必須先啟用混合內容，才能繼續建立活動。

瀏覽器的安全性設定可能會阻止混合內容或不安全 (HTTP) 內容載入至安全 (HTTPS) 頁面或頁框 (例如 VEC)。如果不想停用瀏覽器的安全性設定，則您需要有 HTTPS 網站。

如果網站在不安全 (HTTP) 網域中運作，則您需要允許 VEC 載入使用中的混合內容。

>[!NOTE]
>
>允許混合內容只會影響 VEC，不影響已上線的網站。

如需詳細資訊，請參閱 *Mozilla Developer Network* (MDN) 網站上的[混合內容](https://developer.mozilla.org/en-US/docs/Web/Security/Mixed_content)。

## 在Google Chrome中啟用混合內容{#task_FF297A08F66E47A588C14FD67C037B3A}

如果您透過安全連線造訪網站，Chrome會驗證網頁上的內容是否已安全傳輸。

請參閱 Google Chrome 說明中的[此頁面有不安全的內容](https://support.google.com/chrome/answer/1342714?hl=en)。

如果您正將VEC與最新版Chrome（79.0.3945.117版或更新版本）搭配使用，則需要更新網站設定。 您網站的訪客不需要完成這些步驟。

1. 按一下鎖定或警告圖示，然後按一下「網站設定」]**。**[!UICONTROL 

   ![網站設定](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/site-settings.png)

1. 捲動至&#x200B;**[!UICONTROL 不安全的內容]**，然後使用下拉式清單將「區塊（預設）」變更為「允許」。

   ![不安全的內容](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/insecure-content.png)

1. 重新載入VEC頁面。

## 在Mozilla Firefox中啟用混合內容{#task_5448763B8DC941FD80F84041AEF0A14D}

依預設，Firebox 會封鎖混合了安全和不安全內容的頁面。若要使用 [!DNL Target]，建議您永久變更此設定。您網站的訪客不需要完成這些步驟。

1. 在 Firefox 的位址列中，輸入 `about:config`。
1. 認可 Firefox 顯示的警告訊息。

   ![Firefox警告](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox.png)

1. 在搜尋列中，輸入 `block_active`。

   ![Firefox區塊作用中設定](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox3.png)

1. 按兩下 ` **[!UICONTROL security.mixed_content.block_active_content]**`。

   值會從「True」變更為「False」。值顯示「False」時即為完成。

   ![Firefox安全性](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox2.png)

我們建議您在變更此設定後重新啟動電腦。

## 在Microsoft Edge中啟用混合內容

如果您透過安全連線造訪網站，Edge會驗證網頁上的內容是否已安全傳輸。

如果您正將VEC與最新版Edge搭配使用，則需要更新網站設定。 您網站的訪客不需要完成這些步驟。

1. 按一下鎖定或警告圖示，然後按一下「網站權限&#x200B;]**」。**[!UICONTROL 

   ![Microsoft Edge中的網站權限](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/ms-edge.png)

1. 捲動至&#x200B;**[!UICONTROL 不安全的內容]**，然後使用下拉式清單將「區塊（預設）」變更為「允許」。

   ![不安全的內容](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/ms-edge-2.png)

1. 重新載入VEC頁面。