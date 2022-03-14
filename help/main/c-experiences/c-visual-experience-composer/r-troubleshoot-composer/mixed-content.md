---
keywords: 混合內容；安全；不安全；chrome;troubleshooting;vec;visual experience composer;unsecure;http;https;internet explorer
description: 如果安全的內容與不安全的內容混合，則某些瀏覽器會封鎖頁面的顯示。瞭解如何在Chrome、Firefox和Edge中啟用混合內容。
title: 如何在瀏覽器中啟用混合內容？
feature: Visual Experience Composer (VEC)
exl-id: a2209af6-65e5-427e-b2cb-53b803728ef3
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 26%

---

# 在您的瀏覽器中啟用混合式內容

如果初始請求通過HTTPS安全，但HTTPS安全，則出現混合內容 *和* 載入HTTP內容以顯示網頁。 HTTPS內容是安全的。 HTTP內容不安全。

如果安全內容與不安全內容混合使用，現代瀏覽器可能會阻止頁面顯示或顯示警告消息。

如果 [!UICONTROL 視覺體驗作曲家] (VEC) [!DNL Target] 嘗試開啟包含混合內容的頁面。 此消息將通知您如何禁用瀏覽器中的阻止。 禁用阻塞功能可開啟HTTP站點或具有混合調用（HTTPS和HTTP）的站點。

![混合內容警告](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/mixed_content_warning.png)

以前，雖然不允許混合內容，但您在建立活動時，仍可在三步驟引導式工作流程的步驟 1 中執行一些動作。[!DNL Target] 現在禁止在步驟 1 執行動作。顯示此消息時，必須先啟用混合內容，然後才能繼續建立活動。

瀏覽器的安全性設定可能會阻止混合內容或不安全 (HTTP) 內容載入至安全 (HTTPS) 頁面或頁框 (例如 VEC)。如果不想禁用瀏覽器的安全設定，則必須有HTTPS網站。

如果網站在不安全(HTTP)域上運行，則需要允許VEC載入活動混合內容。

>[!NOTE]
>
>允許混合內容只會影響 VEC，不影響已上線的網站。

如需詳細資訊，請參閱 *Mozilla Developer Network* (MDN) 網站上的[混合內容](https://developer.mozilla.org/en-US/docs/Web/Security/Mixed_content)。

## 在GoogleChrome中啟用混合內容 {#task_FF297A08F66E47A588C14FD67C037B3A}

如果您通過安全連接訪問網站，Chrome將驗證網頁上的內容是否已安全傳輸。

請參閱「」[此頁面的內容不安全](https://support.google.com/chrome/answer/1342714?hl=en)&quot;在《Google·克羅姆幫助》中。

如果要將VEC與最新版本的Chrome(79.0.3945.117版或更高版本)一起使用，則必須更新站點設定。 訪問您站點的訪問者不需要完成這些步驟。

1. 按一下鎖定（警告）表徵圖，然後按一下 **[!UICONTROL 站點設定]**。

   ![站點設定](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/site-settings.png)

1. 滾動到 **[!UICONTROL 不安全的內容]**，然後使用下拉清單將「Block(default)」更改為「Allow（允許）」。

   ![不安全的內容](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/insecure-content.png)

1. 重新載入VEC頁。

## 在Mozilla Firefox中啟用混合內容 {#task_5448763B8DC941FD80F84041AEF0A14D}

依預設，Firebox 會封鎖混合了安全和不安全內容的頁面。若要使用 [!DNL Target]，建議您永久變更此設定。訪問您站點的訪問者不需要完成這些步驟。

1. 在 Firefox 的位址列中，輸入 `about:config`。
1. 認可 Firefox 顯示的警告訊息。

   ![Firefox警告](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox.png)

1. 在搜尋列中，輸入 `block_active`。

   ![Firefox塊_活動設定](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox3.png)

1. 按兩下 ` **[!UICONTROL security.mixed_content.block_active_content]**`。

   值會從「True」變更為「False」。值顯示「False」時即為完成。

   ![Firefox安全](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox2.png)

更改此設定後重新啟動電腦。

## 在Microsoft邊緣啟用混合內容

如果您通過安全連接訪問站點，Edge將驗證網頁上的內容是否已安全傳輸。

如果將VEC與最新版本的Edge一起使用，則必須更新站點設定。 訪問您站點的訪問者不需要完成這些步驟。

1. 按一下鎖定（警告）表徵圖，然後按一下 **[!UICONTROL 站點權限]**。

   ![Microsoft邊緣中的站點權限](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/ms-edge.png)

1. 滾動到 **[!UICONTROL 不安全的內容]**，然後使用下拉清單將「Block(default)」更改為「Allow（允許）」。

   ![不安全的內容](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/ms-edge-2.png)

1. 重新載入VEC頁。
