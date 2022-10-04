---
keywords: 鎖定目標；可視化體驗撰寫器； VEC；疑難排解可視化體驗撰寫器；疑難排解； TLS; TLS 1.2
description: 了解如何疑難排解Adobe中有時發生的問題 [!DNL Target] 可視化體驗撰寫器(VEC)。
title: 如何疑難排解可視化體驗撰寫器的相關問題？
feature: Visual Experience Composer (VEC)
exl-id: ca251025-25e8-4e56-9b59-81310fc763c1
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '804'
ht-degree: 85%

---

# 疑難排解可視化體驗撰寫器的相關問題

顯示有時發生在 [!DNL Adobe Target] [!UICONTROL 可視化體驗撰寫器] (VEC)。

## 當我在可視化體驗撰寫器中開啟我的網站時， [!DNL Target] 程式庫不會載入。 (僅限 VEC) {#section_8A7D3F4AD2CC4C3B823EE9432B97E06F}

在可視化體驗撰寫器中開啟網站時，Target 會新增兩個參數 (`mboxEdit=1` 和 `mboxDisable=1`)。

如果您的網站 (特別是單頁應用程式) 在從一個頁面導覽至另一個頁面時 (而沒有重新載入頁面)，修剪我們的參數或實際上將參數移除，Target 功能會中斷，並且 Target 資料庫不會載入。若要避免此問題，請確保您不會修剪或移除這兩個參數。

## 我的頁面不會在 EEC 中開啟，或載入緩慢。活動或體驗在 VEC 中載入緩慢。(僅限 VEC) {#section_71E7601BE9894E3DA3A7FBBB72B6B0C1}

有數個問題可能會影響 Target 體驗撰寫器中的頁面效能。一些常見問題包括:

* 您的頁面上沒有 mbox。
* 您的網站使用 Proxy 封鎖，它不允許在這兩個體驗撰寫器中開啟頁面。
* 您的網站不允許在 iFrame 中開啟網站本身。

如果問題是在增強體驗撰寫器中發生，請嘗試關閉增強體驗撰寫器，並改為使用可視化體驗撰寫器。

若要停用增強體驗撰寫器，請前往 **[!UICONTROL 管理]** > **[!UICONTROL 可視化體驗撰寫器]** 關掉 **[!UICONTROL 啟用增強體驗撰寫器]** 選項。

有些使用者在主控台中看見下列錯誤訊息:

![Console 錯誤訊息](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/console_error_message.jpg)

如果可視化體驗撰寫器或增強體驗撰寫器均無法運作，請使用可為您的網站覆寫 X-Frames 標頭選項的瀏覽器擴充功能，像是 Requestly (Chrome 或 Firefox) 或 Modify Response Headers (Firefox)，並啟用 VEC 以允許在 iFrames 中載入它們。如果您無法使用瀏覽器擴充功能，請使用表單撰寫器。

>[!NOTE]
>
>除了下列資訊外，您還可以使用適用於 Google Chrome 的 [Adobe Target VEC Helper 瀏覽器擴充功能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)。


>[!NOTE]
>
>這些外掛程式僅應用於 VEC 編輯環境中。
>
>對於 Requestly 擴充功能，只要需要移除標頭，您就應該執行下列任一動作:
>
>* 為要在 VEC 中開啟的 URL 新增 URL 規則，如此一來，便僅有那些 URL 的標頭會移除。
>
>* 在 VEC 中編輯時啟用規則，並在不使用 VEC 時停用規則。
>
>對於「Modify Response Header」擴充功能 (Firefox)，由於無法新增 URL 規則，因此您必須執行下列操作:
>
>* 在 VEC 中編輯時啟用規則，並在不使用 VEC 時停用規則。


**若要在 Chrome 或 Firefox 上使用 Requestly 擴充功能:**

1. 關閉增強體驗撰寫器。
1. 在 Chrome 或 Firefox 上安裝 Requestly 瀏覽器擴充功能。
1. 開啟擴充功能並使用下列項目來設定它:
1. 選取&#x200B;**[!UICONTROL 「Modify Headers」]**。
1. 輸入下列:

   * 規則名稱
   * 修改規則

      * 將&#x200B;**[!UICONTROL 「新增」]**&#x200B;切換為&#x200B;**[!UICONTROL 「移除」]**。
      * 將&#x200B;**[!UICONTROL 「要求」]**&#x200B;切換為&#x200B;**[!UICONTROL 「回應」]**。
      * 輸入 &quot;X-Frame-Options&quot; 作為標頭名稱。
      * 重複先前的步驟並輸入 &quot;x-frame-options&quot; 作為標頭名稱。

         >[!NOTE]
         >
         >透過 Requestly 處理的標頭須區分大小寫。

      * 將&#x200B;**[!UICONTROL 「等於」]**&#x200B;變更為&#x200B;**[!UICONTROL 「包含」]**，作為來源 URL 的條件，並輸入您嘗試在 VEC 中載入之活動的 URL。

      ![chrome_extension影像](assets/chrome_extension.png)


1. 按一下&#x200B;**[!UICONTROL 儲存]**。

   ![requestly image](assets/requestly.png)

   您現在應該可以使用可視化體驗撰寫器快速載入頁面。

**若要在 Firefox 上使用 Modify Response Headers 擴充功能:**

1. 在 Firefox 上安裝 Modify Response Headers，並重新啟動瀏覽器。
1. 從您的 Firefox 擴充功能，選取「Modify Response Headers」擴充功能。
1. 按一下&#x200B;**[!UICONTROL 「偏好設定」]**。
1. 從「動作」下拉式功能表選取&#x200B;**[!UICONTROL 「篩選」]**。
1. 在「Header Name」欄位中，輸入: **[!UICONTROL X-Frame-Options]**。
1. 重複步驟 4 和 5 來使用 **[!UICONTROL x-frame-options]** 新增篩選條件。
1. 按一下&#x200B;**[!UICONTROL 「新增」]**。
1. 按一下&#x200B;**[!UICONTROL 「開始」]**。

![firefox_extension影像](assets/firefox_extension.png)

設定擴充功能之後，開啟 Target。您的頁面現在應該會在可視化體驗撰寫器中載入，即便已停用增強體驗撰寫器。

## 我的頁面未在 VEC 中顯示 (僅限 VEC) {#section_87B3BEA4B6174CFDA6C9A69A1A051FA1}

* 瀏覽器不受支援。
* 瀏覽器正在封鎖安全網站上不安全的頁面。

   按一下瀏覽器位址列 URL 左側的圖示，然後按一下&#x200B;**[!UICONTROL 「停用此頁面上的保護」]**
* 您輸入了無效的 URL。
* 您尚未在您的帳戶設定頁面中輸入預設 URL。

確認已啟用此設定，然後在您的網站上下載和更新at.js。

## 當我使用瀏覽模式時，VEC 似乎損毀。(僅限 VEC) {#section_FA2A18E8FD6A4274B2E395DBAA2FB407}

使用瀏覽模式時，如果您存取的 URL 沒有 target.js 或包含 frame-buster 標頭，可視化體驗撰寫器似乎損毀。由於瀏覽器的安全性考量，Target 無法存取您所導覽的 URL。
