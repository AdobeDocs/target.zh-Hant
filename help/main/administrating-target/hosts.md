---
keywords: 主機；主機；主機群組；疑難排解；最佳實務；ubox；重新導向；重新導向；白名單；允許清單；黑名單；封鎖清單
description: 瞭解如何組織您的網站和預先生產環境，以在Adobe Target中輕鬆管理和分開的報表。
title: 什麼是主機？如何使用主機？
feature: Administration & Configuration
role: Admin
exl-id: 31c661c0-686d-440e-ad58-864fb853b1c4
source-git-commit: 12831d6584acc482db415629d7e70a18e39c47c2
workflow-type: tm+mt
source-wordcount: '1027'
ht-degree: 17%

---

# 主機

組織您的網站和生產前環境，以在[!DNL Adobe Target]中輕鬆管理和分隔報表。

主機管理的主要目標是確保網站上沒有意外出現非使用中的內容。主機管理也可讓您依[環境](/help/main/administrating-target/environments.md)來分隔報表資料。

主機是發出[!DNL Target]要求的任何網域。 在網站上，它通常是發出[!DNL Target]請求的URL的`location.hostname`屬性。

依預設，[!DNL Target]不會限制可以發出[!DNL Target]個要求並接收[!DNL Target]個回應的主機。 當新主機提出請求時，就會自動運作。 此程式也可針對您不知道或無法預測的不同網域進行測試。 如果您要覆寫此預設行為，可以設定允許清單或封鎖清單來限制哪些主機可搭配[!DNL Target]使用。

{{permissions-update}}

若要管理主機，請按一下&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Hosts]**。

## 辨識主機 {#concept_0D4B43E23AA9408F8B28A57ED754BF65}

若要識別主機並將其新增至[!UICONTROL Hosts]清單，必須符合下列條件：

* 主機上必須至少有一個[!DNL Target]要求
* 主機上的頁面必須具備下列專案：

   * 精確的at.js參考
   * [!DNL Target]要求或自動產生的全域[!DNL Target]要求

* 必須在瀏覽器中檢視具有[!DNL Target]要求的頁面

檢視頁面後，主機會列在[!UICONTROL Hosts]清單中，可讓您在環境中管理該主機，以及預覽和啟動活動與測試。

>[!NOTE]
>
>這包括任何個人開發伺服器。

將主機新增至[!UICONTROL Host]清單之後，請確定可辨識該主機。

1. 按一下&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Hosts]**。
1. 如果您的主機未列出，請重新整理瀏覽器。

   依預設，新辨識的主機會置於[!UICONTROL Production]環境中。 [!UICONTROL Production]環境是最安全的環境，因為它不允許從這些主機檢視非作用中的活動。

1. （視條件而定）按一下&#x200B;**[!UICONTROL Move]**&#x200B;圖示（ ![移動圖示](/help/main/administrating-target/assets/icon-move.png) ）將主機移至[!UICONTROL Development]、[!UICONTROL Staging]或其他環境。

>[!NOTE]
>
>無法刪除[!UICONTROL Production]環境，即使您將其重新命名亦然。 我們假設此環境是您提供最終作用中活動與測試的地方。 預設環境不允許檢視非使用中的行銷活動。

## 排序或搜尋「主機」清單 {#section_068B23C9D8224EB78BC3B7C8580251B0}

若要排序[!UICONTROL Hosts]清單，請按一下任何欄標題（[!UICONTROL Name]、[!UICONTROL Environment]或[!UICONTROL Last Requested]），以遞增或遞減順序排序清單。

若要搜尋[!UICONTROL Hosts]清單，請在[!UICONTROL Search Hosts]方塊中輸入搜尋字詞。

## 建立允許清單，指定授權傳送[!DNL Target]要求給[!DNL Target]的主機。{#allowlist}

您可以建立允許清單，指定授權傳送[!DNL Target]要求給[!DNL Target]的主機（網域）。 所有其他產生請求的主機都會收到註銷的授權錯誤回應。 依預設，任何包含[!DNL Target]要求的主機都會在[!UICONTROL Production]環境中向[!DNL Target]註冊，且可以存取所有使用中和已核准的活動。 如果不想要這個方法，您可以改用允許清單來記錄適合發出[!DNL Target]要求並接收[!DNL Target]內容的特定主機。 所有主機都會繼續顯示在[!UICONTROL Hosts]清單中，而環境仍可用來群組這些主機，並為每個主機指派不同的層級，例如主機是否可以看見作用中及/或非作用中的活動。

若要建立允許清單：

1. 從[!UICONTROL Hosts]清單，按一下&#x200B;**[!UICONTROL Authorize Hosts]**。
1. 啟用&#x200B;**[!UICONTROL Enable Authorized Hosts for content delivery]**&#x200B;切換。
1. 視需要在&#x200B;**[!UICONTROL Host contains]**&#x200B;方塊中新增所需的主機。

   可新增多個主機，每個主機各一行。

1. 視需要在&#x200B;**[!UICONTROL Host does not contains]**&#x200B;方塊中新增所需的主機。

   可新增多個主機，每個主機各一行。

1. 按一下 **[!UICONTROL Save]**。

如果未授權的主機發出[!DNL Target]要求，呼叫會以`/* no display - unauthorized mbox host */`回應。

>[!IMPORTANT]
>
>**安全性最佳實務**：如果您使用[!DNL Target]的ubox功能，此允許清單也會控制您的[重新導向程式](https://experienceleague.adobe.com/docs/target-dev/developer/implement-email/working-with-redirectors.html?lang=zh-Hant){target=_blank}可瀏覽的網域清單。 使用ubox作為實施作業的一部分時，請務必新增您要重新導向的任何網域。 如果允許清單未指定，[!DNL Adobe]將無法驗證重新導向URL，並保護不受潛在的惡意重新導向。
>
>允許清單的優先順序高於環境。 在使用允許清單功能之前，請先清除所有主機，然後只有允許清單允許的主機才會出現在您的主機清單中。 接著可將主機移至想要的環境中。

有時，來自其他網站的網域會出現在您的環境中。如果網域呼叫at.js，則清單中會顯示網域。 例如，若有人將您的其中一個網頁複製到他們的伺服器，則您環境中就會出現該網域。您也可以從編目引擎、語言翻譯工具網站或本機磁碟中看見網域。

如果在 API 呼叫中傳入 `mboxHost`，則會針對傳入的環境來記錄轉換。如果未傳遞任何環境，則呼叫中的主機預設為[!UICONTROL Production]。

您也可以建立封鎖清單，在[!UICONTROL Host Does Not Contain]方塊中新增所需的主機，以指定無法將[!DNL Target]要求傳送至[!DNL Target]的主機（網域）。

>[!NOTE]
>
>[!UICONTROL Authorized Hosts]清單同時用於[!DNL Target]個主機和預設的重新導向主機。 新增所有已核准使用[!DNL Adobe Target] JavaScript SDK (at.js) *和*&#x200B;在ubox預設重新導向URL中使用的所有現有網域。 將來，新增任何類似的網域至允許清單。

## 刪除主機 {#section_F56355BA4BC54B078A1A8179BC954632}

您不再需要使用某個主機時，可以將它刪除。

1. 從[!UICONTROL Hosts]清單中，按一下&#x200B;**[!UICONTROL Delete]**&#x200B;圖示。
1. 按一下&#x200B;**[!UICONTROL Delete]**&#x200B;以確認刪除。

>[!NOTE]
>
>如果有人瀏覽到主機上包含[!DNL Target]請求的頁面，則主機會再次列出。

## 疑難排解主機 {#concept_B3D7583FA4BB480382CC7453529FE1B7}

如果遇到主機方面的問題，請嘗試下列疑難排解訣竅:

**主機未出現在您帳戶的清單中。**

* 重新整理瀏覽器中的[!UICONTROL Hosts]頁面。
* 確認[!DNL Target]要求是否正確，包括at.js參考。
* 嘗試瀏覽至主機上的其中一個[!DNL Target]要求。 主機上的任何[!DNL Target]請求都未曾在瀏覽器中轉譯。

**隨機或未知的網域出現在[!UICONTROL Host]清單中。**

如果從某個網域向[!DNL Target]發出請求，則該網域會顯示在此清單中。 通常，您可以從編目引擎、語言翻譯工具網站或本機磁碟中看見網域。如果列出的網域不是您的團隊使用的網域，您可以按一下[!UICONTROL Delete]來移除它。

**我的[!DNL Target]要求傳回/&#42;無顯示 — 未獲授權的mbox主機&#42;/.**

如果未授權的主機發出[!DNL Target]要求，則要求會以/&#42; no display - unauthorized mbox host &#42;/回應。
