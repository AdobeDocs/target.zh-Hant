---
keywords: 主機；主機群組；疑難排解；最佳作法；ubox；重新導向；重新導向；白名單；允許清單；黑名單；封鎖清單
description: 了解如何組織您的網站和生產前環境，以便在Adobe Target中輕鬆管理並分開報告。
title: 什麼是主機？如何使用？
feature: 管理與設定
role: Admin
exl-id: 31c661c0-686d-440e-ad58-864fb853b1c4
source-git-commit: be7b5478006af231aae2b78e4a8c0066e3cb4a5b
workflow-type: tm+mt
source-wordcount: '1080'
ht-degree: 21%

---

# 主機

在[!DNL Adobe Target]中組織您的網站和生產前環境，以便進行輕鬆的管理和分開的報告。

主機管理的主要目標是確保網站上沒有意外出現非使用中的內容。主機管理也可讓您依[environment](/help/administrating-target/environments.md)來分隔報表資料。

主機是從中提出[!DNL Target]請求的任何域。 在網站上，通常是提出[!DNL Target]要求之URL的`location.hostname`屬性。

預設情況下，[!DNL Target]不限制可發出[!DNL Target]請求並接收[!DNL Target]響應的主機。 新主機提出請求時，就會自動運作。 此程式也可讓您針對您不知道或無法預測的不同網域進行測試。 如果要覆蓋此預設行為，可以設定允許清單或阻止清單以限制哪些主機可與[!DNL Target]一起工作。

要管理主機，請按一下「**[!UICONTROL 管理]** > **[!UICONTROL 主機]**」。

![](assets/hosts_list.png)

## 辨識主機 {#concept_0D4B43E23AA9408F8B28A57ED754BF65}

要識別主機並將其添加到[!UICONTROL Hosts]清單，必須滿足以下條件：

* 主機上必須至少存在一個[!DNL Target]請求
* 主機上的頁面必須具備下列項目：

   * 精確的at.js參考
   * [!DNL Target]請求或自動產生的全域[!DNL Target]請求

* 必須在瀏覽器中檢視具有[!DNL Target]請求的頁面

檢視頁面後，主機會列在[!UICONTROL  Hosts]清單中，可讓您在環境中管理它，以及預覽和啟動活動和測試。

>[!NOTE]
>
>這包括任何個人開發伺服器。

當主機新增至[!UICONTROL 「主機」]清單之後，請確定可辨識該主機。

1. 按一下「**[!UICONTROL 管理]** > **[!UICONTROL 主機]**」。
1. 如果您的主機未列出，請重新整理瀏覽器。

   預設情況下，新識別的主機放置在[!UICONTROL Production]環境中。 [!UICONTROL 生產]環境是最安全的環境，因為它不允許從這些主機檢視非作用中活動。

1. （條件性）按一下&#x200B;**[!UICONTROL 移動]**&#x200B;圖示（![移動圖示](/help/administrating-target/assets/icon-move.png)），將主機移入[!UICONTROL 開發]、[!UICONTROL 測試]或其他環境。

>[!NOTE]
>
>即使您重新命名[!UICONTROL 生產]環境，亦無法刪除該環境。 假設此環境是您提供最終作用中活動和測試的位置。 預設環境不允許檢視非使用中的行銷活動。

## 排序或搜尋主機清單 {#section_068B23C9D8224EB78BC3B7C8580251B0}

若要排序[!UICONTROL Hosts]清單，請按一下任何列標題（[!UICONTROL Name]、[!UICONTROL Environment]或[!UICONTROL Last Requested]）以升序或降序排序清單。

要搜索[!UICONTROL Hosts]清單，請在[!UICONTROL Search Hosts]框中鍵入搜索詞。

## 建立允許清單，指定獲授權將[!DNL Target]請求發送到[!DNL Target]的主機。 {#allowlist}

您可以建立允許清單，指定獲授權將[!DNL Target]請求傳送至[!DNL Target]的主機（網域）。 產生請求的所有其他主機會收到註銷的授權錯誤回應。 依預設，在[!UICONTROL Production]環境中，包含[!DNL Target]請求的任何主機都會向[!DNL Target]註冊，且可存取所有使用中和已核准的活動。 如果不需要此方法，您可以改為使用允許清單，記錄適合提出[!DNL Target]請求並接收[!DNL Target]內容的特定主機。 所有主機繼續顯示在[!UICONTROL  Hosts]清單中，並且環境仍可用來對這些主機進行分組，並為每個主機分配不同級別，例如主機是否可以看到活動和/或非活動活動。

若要建立允許清單：

1. 從[!UICONTROL Hosts]清單中，按一下&#x200B;**[!UICONTROL Authorize Hosts]**。
1. 啟用&#x200B;**[!UICONTROL 啟用內容傳送的授權主機]**&#x200B;切換。
1. 在&#x200B;**[!UICONTROL 主機包含]**&#x200B;方塊中，視需要新增所需的主機。

   可新增多個主機，每個主機各一行。

1. 在&#x200B;**[!UICONTROL 主機不包含]**&#x200B;方塊中，視需要新增所需的主機。

   可新增多個主機，每個主機各一行。

1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

如果對未授權的主機發出[!DNL Target]請求，則呼叫會以`/* no display - unauthorized mbox host */`回應。

>[!IMPORTANT]
>
>**安全性最佳實務**:如果您使用的ubox功 [!DNL Target]能，此允許清單也會控制您重新導向程式所導覽 [](/help/c-implementing-target/c-non-javascript-based-implementation/working-with-redirectors.md) 的網域清單。在實作中使用ubox時，請確定您新增要重新導向的任何網域。 如果允許清單未指定，[!DNL Adobe]將無法驗證重新導向URL並防止潛在的惡意重新導向。
>
>允許清單優先於環境。 使用允許清單功能之前，請清除所有主機，然後只有允許清單允許的主機才會顯示在您的主機清單中。 接著可將主機移至想要的環境中。

有時，來自其他網站的網域會出現在您的環境中。如果網域呼叫at.js，則清單中會顯示網域。 例如，若有人將您的其中一個網頁複製到他們的伺服器，則您環境中就會出現該網域。您也可以從編目引擎、語言翻譯工具網站或本機磁碟中看見網域。

如果在 API 呼叫中傳入 `mboxHost`，則會針對傳入的環境來記錄轉換。如果未傳遞任何環境，則呼叫中的主機預設為[!UICONTROL Production]。

您也可以在[!UICONTROL 主機不包含]方塊中新增所需的主機，以建立封鎖清單，指定無法將[!DNL Target]請求傳送至[!DNL Target]的主機（網域）。

>[!NOTE]
>
>[!UICONTROL 授權主機]清單用於[!DNL Target]主機和預設的重新導向主機。 新增所有已核准使用[!DNL Adobe Target] JavaScript SDK(at.js)*AND*&#x200B;的現有網域，這些網域在ubox預設的重新導向URL中使用。 日後將任何新的類似網域新增至允許清單。

## 刪除主機 {#section_F56355BA4BC54B078A1A8179BC954632}

您不再需要使用某個主機時，可以將它刪除。

1. 從[!UICONTROL Hosts]清單中，按一下&#x200B;**[!UICONTROL Delete]**&#x200B;圖示。
1. 按一下「**[!UICONTROL 刪除]**」以確認刪除。

>[!NOTE]
>
>如果有任何人瀏覽到主機上包含[!DNL Target]請求的頁面，則會再次列出主機。

## 疑難排解主機 {#concept_B3D7583FA4BB480382CC7453529FE1B7}

如果遇到主機方面的問題，請嘗試下列疑難排解訣竅:

**主機未出現在您的帳戶清單中。**

* 在瀏覽器中重新整理[!UICONTROL 「主機」]頁面。
* 確認[!DNL Target]要求正確，包括at.js參考。
* 嘗試瀏覽至主機上的其中一個[!DNL Target]請求。 主機上的[!DNL Target]要求可能從未在瀏覽器中轉譯。

**[!UICONTROL 主機]清單中出現隨機或未知的網域。**

如果從網域發出[!DNL Target]請求，則此清單中會顯示網域。 通常，您可以從編目引擎、語言翻譯工具網站或本機磁碟中看見網域。如果列出的網域不是您團隊使用的網域，則可以按一下[!UICONTROL 刪除]將它移除。

**我的 [!DNL Target] 要求會傳回/* no display - unauthorized mbox host */。**

如果未授權的主機發出[!DNL Target]要求，要求會以/* no display - unauthorized mbox host */回應。
