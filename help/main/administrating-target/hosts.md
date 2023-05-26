---
keywords: 主機；主機；主機群組；疑難排解；最佳實務；Ubox；重新導向；重新導向；白名單；允許清單；黑名單；封鎖清單
description: 瞭解如何在Adobe Target中組織您的網站和生產前環境，以方便管理和分隔報表。
title: 什麼是主機？如何使用主機？
feature: Administration & Configuration
role: Admin
exl-id: 31c661c0-686d-440e-ad58-864fb853b1c4
source-git-commit: 2fc704a1779414a370ffd00ef5442fce36e7a5dd
workflow-type: tm+mt
source-wordcount: '1088'
ht-degree: 21%

---

# 主機

組織您的網站和生產前環境，以便輕鬆管理並在下列位置建立獨立報表： [!DNL Adobe Target].

主機管理的主要目標是確保網站上沒有意外出現非使用中的內容。主機管理也可讓您依下列方式分隔報表資料： [環境](/help/main/administrating-target/environments.md).

主機是從中取得 [!DNL Target] 已提出要求。 在網站上，通常是 `location.hostname` 建立URL的 [!DNL Target] 要求。

依預設， [!DNL Target] 不會限制可以建立的主機 [!DNL Target] 要求與接收 [!DNL Target] 回應。 當新主機提出請求時，會自動運作。 此程式還可在您不知道或無法預測的不同網域上進行測試。 如果您想要覆寫此預設行為，可以設定允許清單或封鎖清單來限制使用哪些主機 [!DNL Target].

若要管理主機，請按一下 **[!UICONTROL 管理]** > **[!UICONTROL 主機]**.

![hosts_list影像](assets/hosts_list.png)

## 辨識主機 {#concept_0D4B43E23AA9408F8B28A57ED754BF65}

識別主機並將其新增至 [!UICONTROL 主機] 清單，必須符合下列條件：

* 至少一個 [!DNL Target] 要求必須存在於主機上
* 主機上的頁面必須具備下列專案：

   * 精確的at.js參考
   * A [!DNL Target] 請求或自動產生的全域 [!DNL Target] 請求

* 具有的頁面 [!DNL Target] 請求必須在瀏覽器中檢視

檢視頁面後，主機會列在 [!UICONTROL 主機] 清單，讓您在環境中管理它，並預覽和啟動活動和測試。

>[!NOTE]
>
>這包括任何個人開發伺服器。

當主機新增至[!UICONTROL 「主機」]清單之後，請確定可辨識該主機。

1. 按一下 **[!UICONTROL 管理]** > **[!UICONTROL 主機]**.
1. 如果您的主機未列出，請重新整理瀏覽器。

   依預設，新辨識的主機會放在 [!UICONTROL 生產] 環境。 此 [!UICONTROL 生產] 環境是最安全的環境，因為它不允許從這些主機檢視非作用中的活動。

1. （視條件而定）按一下 **[!UICONTROL 移動]** 圖示( ![移動圖示](/help/main/administrating-target/assets/icon-move.png) )，將主機移至 [!UICONTROL 開發]， [!UICONTROL 分段]，或其他環境。

>[!NOTE]
>
>此 [!UICONTROL 生產] 即使您重新命名，亦無法刪除環境。 我們假設此環境是您提供最終作用中活動和測試的地方。 預設環境不允許檢視非使用中的行銷活動。

## 排序或搜尋主機清單 {#section_068B23C9D8224EB78BC3B7C8580251B0}

若要排序 [!UICONTROL 主機] 清單，按一下任何欄標題([!UICONTROL 名稱]， [!UICONTROL 環境]，或 [!UICONTROL 上次要求])，以遞增或遞減順序排序清單。

若要搜尋 [!UICONTROL 主機] 清單中，輸入搜尋字詞 [!UICONTROL 搜尋主機] 方塊。

## 建立允許清單，指定授權傳送的主機 [!DNL Target] 要求 [!DNL Target]. {#allowlist}

您可以建立允許清單，指定授權傳送的主機（網域） [!DNL Target] 要求 [!DNL Target]. 所有其他產生請求的主機都會收到註銷的授權錯誤回應。 依預設，任何包含 [!DNL Target] 要求註冊 [!DNL Target] 在 [!UICONTROL 生產] 環境，並可存取所有使用中和已核准的活動。 如果不需要此方法，您可以改為使用允許清單來記錄適合製作的特定主機 [!DNL Target] 要求與接收 [!DNL Target] 內容。 所有主機都會繼續顯示在 [!UICONTROL 主機] 清單，而環境仍可用來群組這些主機，並為每個主機指派不同的層級，例如主機是否可以看見作用中及/或非作用中活動。

若要建立允許清單：

1. 從 [!UICONTROL 主機] 清單，按一下 **[!UICONTROL 授權主機]**.
1. 啟用 **[!UICONTROL 啟用已獲授權的主機以進行內容傳送]** 切換。
1. 將所需主機新增至 **[!UICONTROL 主機包含]** 方塊中。

   可新增多個主機，每個主機各一行。

1. 將所需主機新增至 **[!UICONTROL 主機不包含]** 方塊中。

   可新增多個主機，每個主機各一行。

1. 按一下&#x200B;**[!UICONTROL 儲存]**。

若為 [!DNL Target] 在未授權的主機上進行要求，呼叫會以回應 `/* no display - unauthorized mbox host */`.

>[!IMPORTANT]
>
>**安全性最佳實務**：如果您使用的ubox功能 [!DNL Target]，此允許清單也會控制您的網站 [重新導向程式](https://experienceleague.adobe.com/docs/target-dev/developer/implement-email/working-with-redirectors.html){target=_blank} 可以導覽。 使用ubox作為實施作業的一部分時，請務必新增您要重新導向的任何網域。 如果允許清單保持未指定， [!DNL Adobe] 無法驗證重新導向URL並防止潛在的惡意重新導向。
>
>允許清單優先於環境。 在使用允許清單功能之前，請先清除所有主機，然後只有允許清單允許的主機會出現在您的主機清單中。 接著可將主機移至想要的環境中。

有時，來自其他網站的網域會出現在您的環境中。如果網域呼叫at.js，則清單中會顯示網域。 例如，若有人將您的其中一個網頁複製到他們的伺服器，則您環境中就會出現該網域。您也可以從編目引擎、語言翻譯工具網站或本機磁碟中看見網域。

如果在 API 呼叫中傳入 `mboxHost`，則會針對傳入的環境來記錄轉換。如果未傳遞任何環境，則呼叫中的主機預設為 [!UICONTROL 生產].

您也可以建立封鎖清單，指定無法傳送的主機（網域） [!DNL Target] 要求 [!DNL Target] 將所需主機新增至 [!UICONTROL 主機不包含] 方塊。

>[!NOTE]
>
>此 [!UICONTROL 授權的主機] 清單用於兩者 [!DNL Target] 主機和預設重新導向主機。 新增所有已核准使用的現有網域 [!DNL Adobe Target] JavaScript SDK (at.js) *和* ubox中使用的所有網域預設重新導向URL。 未來將任何新的類似網域新增到允許清單。

## 刪除主機 {#section_F56355BA4BC54B078A1A8179BC954632}

您不再需要使用某個主機時，可以將它刪除。

1. 從 [!UICONTROL 主機] 清單中，按一下 **[!UICONTROL 刪除]** 圖示。
1. 按一下「**[!UICONTROL 刪除]**」以確認刪除。

>[!NOTE]
>
>如果有人瀏覽的頁面包含 [!DNL Target] 主機上的要求。

## 疑難排解主機 {#concept_B3D7583FA4BB480382CC7453529FE1B7}

如果遇到主機方面的問題，請嘗試下列疑難排解訣竅:

**主機未出現在您帳戶的清單中。**

* 在瀏覽器中重新整理[!UICONTROL 「主機」]頁面。
* 確認 [!DNL Target] 要求正確，包括at.js參考。
* 嘗試瀏覽至以下其中一項： [!DNL Target] 主機上的要求。 可能否 [!DNL Target] 主機上的請求曾在瀏覽器中轉譯。

**[!UICONTROL 主機]清單中出現隨機或未知的網域。**

如果向以下專案提出請求，則此清單中會顯示一個網域： [!DNL Target] 是從網域中建立的。 通常，您可以從編目引擎、語言翻譯工具網站或本機磁碟中看見網域。如果列出的網域不是您團隊使用的網域，則可以按一下[!UICONTROL 刪除]將它移除。

**我的 [!DNL Target] 要求傳回/&#42; 無顯示 — 未獲授權的mbox主機 &#42;/.**

若為 [!DNL Target] 在未授權的主機上提出要求，要求會以/回應&#42; 無顯示 — 未獲授權的mbox主機 &#42;/.
