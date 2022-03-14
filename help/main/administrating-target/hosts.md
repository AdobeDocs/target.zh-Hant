---
keywords: 主機；主機；主機組；故障排除；最佳做法；ubox；重定向；白名單；黑名單；黑名單；黑名單；
description: 瞭解如何組織您的網站和生產前環境，以便在Adobe Target輕鬆管理和分開報告。
title: 什麼是主機以及如何使用它們？
feature: Administration & Configuration
role: Admin
exl-id: 31c661c0-686d-440e-ad58-864fb853b1c4
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1078'
ht-degree: 21%

---

# 主機

組織您的站點和生產前環境，以便於管理和分開報告 [!DNL Adobe Target]。

主機管理的主要目標是確保網站上沒有意外出現非使用中的內容。主機管理還允許您按 [環境](/help/main/administrating-target/environments.md)。

主機是從中 [!DNL Target] 請求。 在網站上，通常 `location.hostname` URL的屬性 [!DNL Target] 請求。

預設情況下， [!DNL Target] 不限制可以 [!DNL Target] 請求和接收 [!DNL Target] 響應。 當新主機發出請求時，它們會自動工作。 此過程還允許在您不知道或無法預料的不同域上進行測試。 如果要覆蓋此預設行為，可以設定允許清單或阻止清單以限制哪些主機使用 [!DNL Target]。

要管理主機，請按一下 **[!UICONTROL 管理]** > **[!UICONTROL 主機]**。

![](assets/hosts_list.png)

## 識別主機 {#concept_0D4B43E23AA9408F8B28A57ED754BF65}

識別主機並將其添加到 [!UICONTROL 主機] 清單中，必須滿足以下條件：

* 至少一個 [!DNL Target] 主機上必須存在請求
* 主機上的頁面必須具有以下內容：

   * at.js的準確引用
   * A [!DNL Target] 請求或自動生成的全局 [!DNL Target] 請求

* 包含 [!DNL Target] 必須在瀏覽器中查看請求

查看頁面後，主機列在 [!UICONTROL 主機] 清單，允許您在環境中管理它，並預覽和啟動活動和test。

>[!NOTE]
>
>這包括任何個人開發伺服器。

當主機新增至[!UICONTROL 「主機」]清單之後，請確定可辨識該主機。

1. 按一下 **[!UICONTROL 管理]** > **[!UICONTROL 主機]**。
1. 如果您的主機未列出，請重新整理瀏覽器。

   預設情況下，新識別的主機將放置在 [!UICONTROL 生產] 環境。 的 [!UICONTROL 生產] 環境是最安全的環境，因為它不允許從這些主機查看非活動活動。

1. （條件）按一下 **[!UICONTROL 移動]** 表徵圖。 ![移動表徵圖](/help/main/administrating-target/assets/icon-move.png) )將主機移入 [!UICONTROL 開發]。 [!UICONTROL 暫存]或其他環境。

>[!NOTE]
>
>的 [!UICONTROL 生產] 即使您更名環境，也無法刪除它。 假定此環境是您為最終、活動活動和test服務的場所。 預設環境不允許檢視非使用中的行銷活動。

## 排序或搜索主機清單 {#section_068B23C9D8224EB78BC3B7C8580251B0}

排序 [!UICONTROL 主機] 清單，按一下任何列標題([!UICONTROL 名稱]。 [!UICONTROL 環境]或 [!UICONTROL 上次請求])按升序或降序對清單進行排序。

搜索 [!UICONTROL 主機] 清單中，在 [!UICONTROL 搜索主機] 框。

## 建立允許清單，指定有權發送的主機 [!DNL Target] 請求 [!DNL Target]。 {#allowlist}

您可以建立一個允許清單，該清單指定有權發送的主機（域） [!DNL Target] 請求 [!DNL Target]。 所有其他生成請求的主機都會收到注釋掉的授權錯誤響應。 預設情況下，包含 [!DNL Target] 請求註冊 [!DNL Target] 的 [!UICONTROL 生產] 並有權訪問所有活動和批准的活動。 如果不需要此方法，則可以改用允許清單來記錄符合條件的特定主機 [!DNL Target] 請求和接收 [!DNL Target] 內容。 所有主機繼續顯示在 [!UICONTROL 主機] 並且環境仍可用於對這些主機進行分組，並為每個主機分配不同的級別，例如，主機是否可以看到活動和/或非活動活動。

要建立允許清單：

1. 從 [!UICONTROL 主機] 清單，按一下 **[!UICONTROL 授權主機]**。
1. 啟用 **[!UICONTROL 為內容交付啟用授權主機]** 切換。
1. 在 **[!UICONTROL 主機包含]** 按鈕，將選定控制項在Tab鍵次序中下移一個位置。

   可新增多個主機，每個主機各一行。

1. 在 **[!UICONTROL 主機不包含]** 按鈕，將選定控制項在Tab鍵次序中下移一個位置。

   可新增多個主機，每個主機各一行。

1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

如果 [!DNL Target] 在未授權的主機上發出請求，該呼叫以 `/* no display - unauthorized mbox host */`。

>[!IMPORTANT]
>
>**安全最佳做法**:如果使用的 [!DNL Target]，此允許清單還控制您的 [重設](/help/main/c-implementing-target/c-non-javascript-based-implementation/working-with-redirectors.md) 可以導航。 確保在將ubox用作實施的一部分時添加要重定向到的任何域。 如果未指定允許清單， [!DNL Adobe] 無法驗證重定向URL並防止潛在的惡意重定向。
>
>允許清單優先於環境。 在使用允許清單功能之前清除所有主機，則只有允許清單允許的主機才會顯示在主機清單中。 接著可將主機移至想要的環境中。

有時，來自其他網站的網域會出現在您的環境中。如果域調用at.js ，則清單中將顯示域。 例如，若有人將您的其中一個網頁複製到他們的伺服器，則您環境中就會出現該網域。您也可以從編目引擎、語言翻譯工具網站或本機磁碟中看見網域。

如果在 API 呼叫中傳入 `mboxHost`，則會針對傳入的環境來記錄轉換。如果未傳遞任何環境，則呼叫中的主機預設為 [!UICONTROL 生產]。

您還可以建立一個denylist，該denylist指定無法發送的主機（域） [!DNL Target] 請求 [!DNL Target] 在 [!UICONTROL 主機不包含] 框。

>[!NOTE]
>
>的 [!UICONTROL 授權主機] 清單用於 [!DNL Target] 主機和預設重定向主機。 添加所有已批准使用的現有域 [!DNL Adobe Target] JavaScript SDK(at.js) *和* ubox預設重定向URL中使用的所有域。 將來將任何新的類似域添加到允許清單中。

## 刪除主機 {#section_F56355BA4BC54B078A1A8179BC954632}

您不再需要使用某個主機時，可以將它刪除。

1. 從 [!UICONTROL 主機] 清單，按一下 **[!UICONTROL 刪除]** 表徵圖
1. 按一下「**[!UICONTROL 刪除]**」以確認刪除。

>[!NOTE]
>
>如果有人瀏覽包含 [!DNL Target] 請求。

## 疑難排解主機 {#concept_B3D7583FA4BB480382CC7453529FE1B7}

如果遇到主機方面的問題，請嘗試下列疑難排解訣竅:

**主機未出現在您帳戶的清單中。**

* 在瀏覽器中重新整理[!UICONTROL 「主機」]頁面。
* 確認 [!DNL Target] 請求正確，包括at.js引用。
* 嘗試瀏覽到 [!DNL Target] 請求。 有可能不 [!DNL Target] 在瀏覽器中呈現了主機上的請求。

**[!UICONTROL 主機]清單中出現隨機或未知的網域。**

如果請求 [!DNL Target] 是從域生成的。 通常，您可以從編目引擎、語言翻譯工具網站或本機磁碟中看見網域。如果列出的網域不是您團隊使用的網域，則可以按一下[!UICONTROL 刪除]將它移除。

**我的 [!DNL Target] 請求返回/*無顯示 — 未經授權的mbox主機*/。**

如果 [!DNL Target] 請求是在未經授權的主機上發出的，該請求以/* no display - unauthorized mbox host */作為響應。
