---
keywords: host;hosts;host group;troubleshooting;best practices;ubox;redirects;redirect;whitelist
description: 組織您的網站和生產前環境，適用於簡易管理和分開的報表。
title: 主機
topic: Standard
uuid: c7682269-4ec2-4a0f-b053-7e0ec77f4604
translation-type: tm+mt
source-git-commit: 34c4c48602df8550287e86c535ebc350fe2185f7
workflow-type: tm+mt
source-wordcount: '1179'
ht-degree: 68%

---


# 主機{#hosts}

組織您的網站和生產前環境，適用於簡易管理和分開的報表。

主機管理的主要目標是確保網站上沒有意外出現非使用中的內容。Host management also lets you separate report data by [environment](/help/administrating-target/environments.md).

主機是指您在任何專案階段進行期間支援內容的任何所在網站伺服器 (或網站網域)。系統會識別所有做為 mbox 的主機。

主機會整合至環境以便輕鬆管理。例如，您可能有許多主機聚集在兩個或三個環境中。The preset environments include [!UICONTROL Production], [!UICONTROL Staging], and [!UICONTROL Development]. 您可以新增環境並重新命名環境 (如需要)。

One environment, the default environment, is pre-named [!UICONTROL Production]. 即使重新命名此預設環境，亦無法刪除此環境。[!DNL Target] 假設這是您提供最終批准活動與測試的地方。

When an mbox request is received from new websites or domains, these new domains always appear in the [!UICONTROL Production] environment. The [!UICONTROL Production] environment cannot have its settings changed, so unknown or new sites are guaranteed to see only content that is active and ready. 主機管理亦可讓您在啟動活動之前，輕鬆針對測試、預備和開發環境確保新活動和內容的品質。

[!DNL Target] 不限制可傳送和接收 mbox 的主機，有新的伺服器或網域出現時，就會自動運作 (除非您已設定白名單或黑名單)。這樣也可讓您針對未知或無法預測的其他網域進行廣告測試。

若要管理主機，請按一 **[!UICONTROL 下「管理]** > **[!UICONTROL 主機]**」。

![](assets/hosts_list.png)

## Recognizing hosts {#concept_0D4B43E23AA9408F8B28A57ED754BF65}

要識別主機並將其添加到「主 [!UICONTROL 機] 」清單中，必須滿足以下條件：

* 主機上至少必須有一個 mbox
* 主機上的頁面必須具有下列:

   * 精確的at.js或mbox.js參考
   * mbox 或自動產生的全域 mbox 呼叫

* 必須在瀏覽器中檢視具有 mbox 的網頁

在檢視過頁面之後，主機就會列在[!UICONTROL 「主機」]清單中，可讓您在環境中管理它，以及預覽和啟動活動及測試。

>[!NOTE] {class=&quot;- topic/note &quot;}
>
>這包括任何個人開發伺服器。

當主機新增至[!UICONTROL 「主機」]清單之後，請確定可辨識該主機。

1. 按一 **[!UICONTROL 下「管理]** > **[!UICONTROL 主機]**」。
1. 如果您的主機未列出，請重新整理瀏覽器。

   By default, a newly recognized host is placed in the [!UICONTROL Production] environment. 這是最安全的環境，因為它不允許從這些主機檢視未批准的活動。

1. （條件性）按一下「移動」 ![圖示(移動圖示](/help/administrating-target/assets/icon-move.png) )，將主機移至「開 [!UICONTROL 發]」、「 [!UICONTROL 測試]」或其他環境。

>[!NOTE]
>
>The [!UICONTROL Production] environment cannot be deleted, even if you rename it. 這是您提供最終使用中活動與測試的地方。預設環境不允許檢視非使用中的行銷活動。

## Sort or search the Hosts list {#section_068B23C9D8224EB78BC3B7C8580251B0}

To sort the [!UICONTROL Hosts] list, click any column header ([!UICONTROL Name], [!UICONTROL Environment], or [!UICONTROL Last Requested]) to sort the list in ascending or descending order.

To search the [!UICONTROL Hosts] list, type a search term in the [!UICONTROL Search Hosts] box.

## Create whitelists that specify hosts that are authorized to send mbox calls to Target. {#whitelist}

您可以建立白名單，指定獲授權可將 mbox 呼叫傳送至 [!DNL Target] 的主機 (網域)。其他產生呼叫的所有主機將收到註銷的授權錯誤回應。依預設，在「生產」環境中，包含 mbox 呼叫的任何主機都會向 [!DNL Target] 註冊，且可以存取所有使用中和已批准的活動。如果這不是理想的作法，您可以改為使用白名單，記錄適合執行 mbox 呼叫和接收 [!DNL Target] 內容的特定主機。所有主機將持續出現在[!UICONTROL 「主機」]清單中，環境仍可用來組合這些主機並指派不同層級給各主機，例如主機是否可以看到使用中和/或非使用中的行銷活動。

若要建立白名單:

1. 從「主 [!UICONTROL 機] 」清單中，按一 **[!UICONTROL 下「授權主機」]**。
1. 啟用「啟 **[!UICONTROL 用授權主機」以進行內容傳送]** 。
1. Add the desired hosts in the **[!UICONTROL Host contains]** box, as desired.

   可新增多個主機，每個主機各一行。

1. Add the desired hosts in the **[!UICONTROL Host does not contains]** box, as desired.

   可新增多個主機，每個主機各一行。

1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

如果未授權的主機進行了 mbox 呼叫，該呼叫會以 `/* no display - unauthorized mbox host */` 回應。

>[!IMPORTANT]
>
>**安全性最佳實務**: 如果您使用的ubox功 [!DNL Target]能，請注意，此白名單也會控制重新導向程式可導覽的網 [域清單](/help/c-implementing-target/c-non-javascript-based-implementation/working-with-redirectors.md) 。 當您將ubox用作實作的一部分時，請確定您新增任何要重新導向的網域。 如果未指定白名單，Adobe將無法驗證重新導向URL並防止潛在的惡意重新導向。
>
>白名單優先於環境。在使用白名單功能前，應先清除所有主機，只讓白名單允許的主機顯示在主機清單中。接著可將主機移至想要的環境中。

有時，來自其他網站的網域會出現在您的環境中。如果網域對您的at.js或mbox.js進行呼叫，網域會出現在清單中。 例如，若有人將您的其中一個網頁複製到他們的伺服器，則您環境中就會出現該網域。您也可以從編目引擎、語言翻譯工具網站或本機磁碟中看見網域。

如果在 API 呼叫中傳入 `mboxHost`，則會針對傳入的環境來記錄轉換。If no environment is passed, the host in the call defaults to [!UICONTROL Production].

您也可以建立黑名單，在[!DNL Target]「主機不包含」[!UICONTROL 方塊中新增所需的主機，以指定不能將 mbox 呼叫傳送至 ] 的主機 (網域)。

## Delete a host {#section_F56355BA4BC54B078A1A8179BC954632}

您不再需要使用某個主機時，可以將它刪除。

1. From the [!UICONTROL Hosts] list, click the **[!UICONTROL Delete]** icon.
1. 按一下「**[!UICONTROL 刪除]**」以確認刪除。

>[!NOTE]
>
>如有任何人瀏覽到主機上的 mbox 頁面，則主機會再次列出。

## 疑難排解主機 {#concept_B3D7583FA4BB480382CC7453529FE1B7}

在 [!DNL Adobe Target] 中管理和疑難排解主機的最佳作法。

如果遇到主機方面的問題，請嘗試下列疑難排解訣竅:

**主機未顯示在您帳戶的 mbox 清單中.**

* 在瀏覽器中重新整理[!UICONTROL 「主機」]頁面。
* 確認mbox代碼正確，包括at.js或mbox.js參考。
* 嘗試瀏覽至主機的其中一個 mbox。可能是主機的 mbox 不曾在瀏覽器中轉譯。

**[!UICONTROL 主機]清單中出現隨機或未知的網域。**

如果從某個網域呼叫 [!DNL Target]，該網域便會顯示在此清單中。通常，您可以從編目引擎、語言翻譯工具網站或本機磁碟中看見網域。如果列出的網域不是您團隊使用的網域，則可以按一下[!UICONTROL 刪除]將它移除。

**我的 mbox 呼叫傳回 /* no display - unauthorized mbox host */**。

如果未授權的主機進行了 mbox 呼叫，該呼叫會以 /* no display - unauthorized mbox host */ 回應。
