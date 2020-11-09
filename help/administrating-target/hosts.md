---
keywords: host;hosts;host group;troubleshooting;best practices;ubox;redirects;redirect;whitelist;allowlist;blacklist;blocklist
description: 組織您的網站和生產前環境，適用於簡易管理和分開的報表。
title: 主機
feature: hosts and environments
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '1079'
ht-degree: 26%

---


# 主機{#hosts}

組織您的網站和生產前環境，適用於簡易管理和分開的報表。

主機管理的主要目標是確保網站上沒有意外出現非使用中的內容。Host management also lets you separate report data by [environment](/help/administrating-target/environments.md).

主機是指從中提出請求的 [!DNL Target] 任何網域。 在網站上，它通常是提出 `location.hostname` 請求的URL的屬 [!DNL Target] 性。

依預設， [!DNL Target] 不會限制可發出請求並接收回 [!DNL Target] 應的 [!DNL Target] 主機。 當新主機發出請求時，它們會自動運作。 這也可讓您在您不知道或無法預測的不同網域上進行測試。 如果要覆蓋此預設行為，可以設定允許清單或塊清單以限制將使用哪些主機 [!DNL Target]。

若要管理主機，請按一 **[!UICONTROL 下「管理]** > **[!UICONTROL 主機]**」。

![](assets/hosts_list.png)

## Recognizing hosts {#concept_0D4B43E23AA9408F8B28A57ED754BF65}

要識別主機並將其添加到「主 [!UICONTROL 機] 」清單中，必須滿足以下條件：

* At least one [!DNL Target] request must exist on the host
* 主機上的頁面必須具有以下內容：

   * 精確的at.js或mbox.js參考
   * 請求 [!DNL Target] 或自動產生的全域請 [!DNL Target] 求

* The page with the [!DNL Target] request must be viewed in a browser

After the page is viewed, the host is listed in the [!UICONTROL Hosts] list, allowing you to manage it in an environment, as well as preview and launch activities and tests.

>[!NOTE]
>
>這包括任何個人開發伺服器。

當主機新增至[!UICONTROL 「主機」]清單之後，請確定可辨識該主機。

1. 按一 **[!UICONTROL 下「管理]** > **[!UICONTROL 主機]**」。
1. 如果您的主機未列出，請重新整理瀏覽器。

   By default, a newly recognized host is placed in the [!UICONTROL Production] environment. 這是最安全的環境，因為它不允許從這些主機檢視未批准的活動。

1. （條件性）按一 **[!UICONTROL 下「移動]** 」圖示( ![移動圖示](/help/administrating-target/assets/icon-move.png) )，將主機移入「開發 [!UICONTROL 」、「Staging]」或「StagingLink」或其他環境。

>[!NOTE]
>
>The [!UICONTROL Production] environment cannot be deleted, even if you rename it. 這是您提供最終使用中活動與測試的地方。預設環境不允許檢視非使用中的行銷活動。

## Sort or search the Hosts list {#section_068B23C9D8224EB78BC3B7C8580251B0}

To sort the [!UICONTROL Hosts] list, click any column header ([!UICONTROL Name], [!UICONTROL Environment], or [!UICONTROL Last Requested]) to sort the list in ascending or descending order.

To search the [!UICONTROL Hosts] list, type a search term in the [!UICONTROL Search Hosts] box.

## Create allowlists that specify hosts that are authorized to send Target requests to Target. {#allowlist}

You can create an allowlist that specifies hosts (domains) that are authorized to send [!DNL Target] requests to [!DNL Target]. 所有其他產生請求的主機將收到註解的授權錯誤回應。 By default, any host that contains a [!DNL Target] request registers with [!DNL Target] in the [!UICONTROL Production] environment and has access to all active and approved activities. If this is not the desired approach, you can instead use the allowlist to record specific hosts that are eligible to make [!DNL Target] requests and receive [!DNL Target] content. All hosts will continue to display in the [!UICONTROL Hosts] list, and environments can still be used to group these hosts and assign different levels to each, such as whether the host can see active and/or inactive activities.

要建立允許清單：

1. 從「主 [!UICONTROL 機] 」清單中，按一 **[!UICONTROL 下「授權主機」]**。
1. 啟用「啟 **[!UICONTROL 用授權主機」以進行內容傳送]** 。
1. Add the desired hosts in the **[!UICONTROL Host contains]** box, as desired.

   可新增多個主機，每個主機各一行。

1. Add the desired hosts in the **[!UICONTROL Host does not contains]** box, as desired.

   可新增多個主機，每個主機各一行。

1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

If a [!DNL Target] request is made on an unauthorized host, the call will respond with `/* no display - unauthorized mbox host */`.

>[!IMPORTANT]
>
>**安全性最佳實務**:如果您使用的ubox功 [!DNL Target]能，請注意，此允許清單也會控制重新導向程式可導覽的網 [域清單](/help/c-implementing-target/c-non-javascript-based-implementation/working-with-redirectors.md) 。 當您將ubox用作實作的一部分時，請確定您新增任何要重新導向的網域。 如果未指定允許清單， [!DNL Adobe] 將無法驗證重新導向URL並防止潛在的惡意重新導向。
>
>允許清單優先於環境。 在使用allowlist功能之前，應清除所有主機，然後僅允許清單允許的主機顯示在主機清單中。 接著可將主機移至想要的環境中。

有時，來自其他網站的網域會出現在您的環境中。如果網域對您的at.js或mbox.js進行呼叫，網域會出現在清單中。 例如，若有人將您的其中一個網頁複製到他們的伺服器，則您環境中就會出現該網域。您也可以從編目引擎、語言翻譯工具網站或本機磁碟中看見網域。

如果在 API 呼叫中傳入 `mboxHost`，則會針對傳入的環境來記錄轉換。If no environment is passed, the host in the call defaults to [!UICONTROL Production].

You can also create a denylist that specifies hosts (domains) than cannot send [!DNL Target] requests to [!DNL Target] by adding the desired hosts in the [!UICONTROL Host Does Not Contain] box.

>[!NOTE]
>
>由於「授權主機」清單同時用於主機 [!DNL Target] 和預設的重新導向主機，因此您必須新增所有已核准使用 [!DNL Adobe Target] Javascript SDK(at.js) *AND* ubox預設重新導向URL中所有網域的現有網域。 您還必須在未來將任何新的類似域添加到allowlist中。

## Delete a host {#section_F56355BA4BC54B078A1A8179BC954632}

您不再需要使用某個主機時，可以將它刪除。

1. From the [!UICONTROL Hosts] list, click the **[!UICONTROL Delete]** icon.
1. 按一下「**[!UICONTROL 刪除]**」以確認刪除。

>[!NOTE]
>
>如果有人瀏覽到包含主機請求的頁面，則主機將 [!DNL Target] 再次列出。

## 疑難排解主機 {#concept_B3D7583FA4BB480382CC7453529FE1B7}

如果遇到主機方面的問題，請嘗試下列疑難排解訣竅:

**主機不會出現在您帳戶的清單中。**

* 在瀏覽器中重新整理[!UICONTROL 「主機」]頁面。
* 確認請 [!DNL Target] 求正確，包括at.js或mbox.js參考。
* Try browsing to one of the [!DNL Target] requests on the host. It&#39;s possible that no [!DNL Target] request on the host was ever rendered in a browser.

**[!UICONTROL 主機]清單中出現隨機或未知的網域。**

A domain appears in this list if a request to [!DNL Target] is made from the domain. 通常，您可以從編目引擎、語言翻譯工具網站或本機磁碟中看見網域。如果列出的網域不是您團隊使用的網域，則可以按一下[!UICONTROL 刪除]將它移除。

**我的 [!DNL Target] 請求傳回/*無顯示——未授權的mbox主機*/。**

If a [!DNL Target] request is made on an unauthorized host, the request will respond with /* no display - unauthorized mbox host */.
