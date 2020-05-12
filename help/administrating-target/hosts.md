---
keywords: host;hosts;host group;environment;troubleshooting;best practices;ubox;redirects;redirect;whitelist
description: 組織您的網站和生產前環境，適用於簡易管理和分開的報表。
title: 主機
topic: Standard
uuid: c7682269-4ec2-4a0f-b053-7e0ec77f4604
translation-type: tm+mt
source-git-commit: 111a960201e14c5283b8c7212dffac9fde9c49e9
workflow-type: tm+mt
source-wordcount: '1823'
ht-degree: 92%

---


# 主機{#hosts}

組織您的網站和生產前環境，適用於簡易管理和分開的報表。

主機管理的主要目標是確保網站上沒有意外出現非使用中的內容。主機管理還可讓您依環境來分隔報表資料。

主機是指您在任何專案階段進行期間支援內容的任何所在網站伺服器 (或網站網域)。系統會識別所有做為 mbox 的主機。

主機會整合至環境以便輕鬆管理。例如，您可能有許多主機聚集在兩個或三個環境中。預設環境包括生產、測試和開發。您可以新增環境並重新命名環境 (如需要)。

一個環境 (預設環境) 已預先命名為「生產」。即使重新命名此預設環境，亦無法刪除此環境。[!DNL Target] 假設這是您提供最終批准活動與測試的地方。

從新網站或網域收到 mbox 請求時，這些新網域會一律顯示於「生產」環境中。「生產」環境無法變更其設定，因此可保證在未知或新網站上只會看見使用中和準備好的內容。主機管理亦可讓您在啟動活動之前，輕鬆針對測試、預備和開發環境確保新活動和內容的品質。

Target 不限制可傳送和接收 mbox 的主機，有新的伺服器或網域出現時，就會自動運作 (除非您已設定白名單或黑名單)。這樣也可讓您針對未知或無法預測的其他網域進行廣告測試。

若要管理主機和環境，請按一下「**[!UICONTROL 設定]** > **[!UICONTROL 主機]**」。

![](assets/hosts_list.png)

## Recognizing hosts {#concept_0D4B43E23AA9408F8B28A57ED754BF65}

關於必須符合條件，[!DNL Target] 才能識別主機並將它新增至主機清單的資訊。

若要識別主機，需符合下列條件:

* 主機上至少必須有一個 mbox
* 主機上的頁面必須具有下列:

   * 精確的 [!DNL mbox.js] 參考
   * mbox 或自動產生的全域 mbox 呼叫

* 必須在瀏覽器中檢視具有 mbox 的網頁

在檢視過頁面之後，主機就會列在[!UICONTROL 「主機」]清單中，可讓您在環境中管理它，以及預覽和啟動活動及測試。

>[!NOTE] {class=&quot;- topic/note &quot;}
>
>這包括任何個人開發伺服器。

當主機新增至[!UICONTROL 「主機」]清單之後，請確定可辨識該主機。

1. 按一下「**[!UICONTROL 設定]** > **[!UICONTROL 主機]**」。
1. 如果您的主機未列出，請重新整理瀏覽器。依預設，新識別的主機會放在「生產」環境中。這是最安全的環境，因為它不允許從這些主機檢視未批准的活動。
1. (依條件) 將主機移至「開發」或「預備」環境。

>[!NOTE]
>
>即使您重新命名「生產」環境，亦無法刪除此環境。這是您提供最終使用中活動與測試的地方。預設環境不允許檢視非使用中的行銷活動。

## Manage hosts and environments {#concept_90573F5A52E04600A8C3C5897880C10F}

可協助您管理主機和環境 (主機群組) 的資訊，包括設定報表的預設主機、建立白名單、變更環境的名稱、將主機移動至另一個環境，以及刪除主機或環境。


若要存取[!UICONTROL 「主機」]清單，請按一下「**[!UICONTROL 設定]** > **[!UICONTROL 主機]**」。

![](assets/hosts_list.png)

## Filter, sort, or search the Hosts list {#section_068B23C9D8224EB78BC3B7C8580251B0}

若要依環境篩選[!UICONTROL 「主機」]清單，請按一下&#x200B;**[!UICONTROL 「全部」]**&#x200B;下拉式清單，然後選取所需的環境 (生產、預備、開發或您建立的自訂環境)。

若要排序[!UICONTROL 「主機」]清單，請按一下任何欄標頭 (名稱、環境或上次要求)，以遞增或遞減順序來排序清單。

若要搜尋[!UICONTROL 「主機」]清單，請在「搜尋」方塊中輸入搜尋詞彙。

## Select multiple hosts {#section_EF3B458475184B7EA997C3559714397C}

若要選取多個主機，請選取所需主機的[!UICONTROL 「名稱」]欄旁邊的核取方塊。然後，您可以移動或刪除全部已選取的主機。

## Create an environment {#section_32097D0993724DF3A202D164D3F18674}

1. 從[!UICONTROL 「主機」]清單，按一下&#x200B;**[!UICONTROL 「環境」]**&#x200B;索引標籤。
1. 按一下&#x200B;**[!UICONTROL 「建立環境」]**。
1. 為環境指定描述性名稱。
1. 為環境指定所需的使用中模式: [!UICONTROL 使用中的活動]或[!UICONTROL 使用中或非使用中的活動]。
1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

## Set the default host for reporting {#section_4F8539B07C0C45E886E8525C344D5FB0}

您可以選取想要的環境作為所有活動報表的預設環境。

如果您使用「生產」作為預設值，則所有未知主機會自動新增在這裡，而來自那裡的報表資料會包含在預設報表檢視中。反之，建立「全新」環境可確保只包含您的核心網站/網域。

若要設定報表的預設環境:

1. 從[!UICONTROL 「主機」]清單，按一下&#x200B;**[!UICONTROL 「設定」]**&#x200B;索引標籤。
1. 從&#x200B;**[!UICONTROL 「環境設定」]**&#x200B;下拉式清單中選取預設主機。
1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

>[!NOTE]
>
>[!DNL Recommendations]如果主機會切換主機群組， 的使用者必須重建其行為資料庫和產品資料庫。

## Create whitelists that specify hosts that are authorized to send mbox calls to Target. {#whitelist}

您可以建立白名單，指定獲授權可將 mbox 呼叫傳送至 [!DNL Target] 的主機 (網域)。其他產生呼叫的所有主機將收到註銷的授權錯誤回應。依預設，在「生產」環境中，包含 mbox 呼叫的任何主機都會向 [!DNL Target] 註冊，且可以存取所有使用中和已批准的活動。如果這不是理想的作法，您可以改為使用白名單，記錄適合執行 mbox 呼叫和接收 [!DNL Target] 內容的特定主機。所有主機將持續出現在[!UICONTROL 「主機」]清單中，環境仍可用來組合這些主機並指派不同層級給各主機，例如主機是否可以看到使用中和/或非使用中的行銷活動。

若要建立白名單:

1. 從[!UICONTROL 「主機」]清單，按一下&#x200B;**[!UICONTROL 「設定」]**&#x200B;索引標籤。
1. 選取&#x200B;**[!UICONTROL 「啟用已獲授權的主機以進行內容傳送」]**&#x200B;核取方塊。
1. 在&#x200B;**[!UICONTROL 「主機包含」]**&#x200B;方塊中，依需要新增所需的主機。

   可新增多個主機，每個主機各一行。

1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

如果未授權的主機進行了 mbox 呼叫，該呼叫會以 `/* no display - unauthorized mbox host */` 回應。

>[!IMPORTANT]
>
>**安全性最佳實務**: 如果您使用的ubox功 [!DNL Target]能，請注意，此白名單也會控制重新導向程式可導覽的網 [域清單](/help/c-implementing-target/c-non-javascript-based-implementation/working-with-redirectors.md) 。 當您將ubox用作實作的一部分時，請確定您新增任何要重新導向的網域。 如果未指定白名單，Adobe將無法驗證重新導向URL並防止潛在的惡意重新導向。
>
>白名單優先於環境。在使用白名單功能前，應先清除所有主機，只讓白名單允許的主機顯示在主機清單中。接著可將主機移至想要的環境中。

有時，來自其他網站的網域會出現在您的環境中。若網域呼叫 mbox.js，則清單中會顯示網域。例如，若有人將您的其中一個網頁複製到他們的伺服器，則您環境中就會出現該網域。您也可以從編目引擎、語言翻譯工具網站或本機磁碟中看見網域。

如果在 API 呼叫中傳入 `mboxHost`，則會針對傳入的環境來記錄轉換。如果未傳遞任何環境，則呼叫中的主機預設為「生產」。

您也可以建立黑名單，在[!DNL Target]「主機不包含」[!UICONTROL 方塊中新增所需的主機，以指定不能將 mbox 呼叫傳送至 ] 的主機 (網域)。

## Change the name of an environment {#section_9F5F94285F8E495E9CE69810CE94CA08}

1. 從[!UICONTROL 「主機」]清單，按一下&#x200B;**[!UICONTROL 「環境」]**&#x200B;索引標籤。
1. 暫留在所需的環境上，然後按一下&#x200B;**[!UICONTROL 「編輯」]**&#x200B;圖示。
1. 變更環境名稱。
1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

## Move a host to a different environment {#section_9F52549958BD485EB74FE78C32773D2A}

1. 從[!UICONTROL 「主機」]清單中，暫留在您要移動的主機上。
1. 按一下&#x200B;**[!UICONTROL 「移動」]**&#x200B;圖示。
1. 從下拉式清單中選取所需的環境，然後按一下勾號圖示。

## Delete a host {#section_F56355BA4BC54B078A1A8179BC954632}

您不再需要使用某個主機時，可以將它刪除。

1. 從[!UICONTROL 「主機」]清單中，暫留在您要刪除的主機上。
1. 按一下&#x200B;**[!UICONTROL 「刪除」]**&#x200B;圖示。
1. 按一下「**[!UICONTROL 刪除]**」以確認刪除。

>[!NOTE]
>
>如有任何人瀏覽到主機上的 mbox 頁面，則主機會再次列出。

## Delete an environment {#section_737F8869612047868D03FC755B1223D3}

您可以刪除不再需要的環境。

1. 從[!UICONTROL 「主機」]清單，按一下&#x200B;**[!UICONTROL 「環境」]**&#x200B;索引標籤。
1. 暫留在您要刪除的環境上。
1. 按一下&#x200B;**[!UICONTROL 「刪除」]**&#x200B;圖示。
1. 按一下「**[!UICONTROL 刪除]**」以確認刪除。

>[!NOTE]
>
>您無法刪除「生產」環境，但您可以重新命名。

## 疑難排解主機 {#concept_B3D7583FA4BB480382CC7453529FE1B7}

在 [!DNL Adobe Target] 中管理和疑難排解主機的最佳作法。

如果遇到主機方面的問題，請嘗試下列疑難排解訣竅:

**主機未顯示在您帳戶的 mbox 清單中.**

* 在瀏覽器中重新整理[!UICONTROL 「主機」]頁面。
* 確認 mbox 程式碼正確，包括 [!DNL mbox.js] 參考。
* 嘗試瀏覽至主機的其中一個 mbox。可能是主機的 mbox 不曾在瀏覽器中轉譯。

**[!UICONTROL 主機]清單中出現隨機或未知的網域。**

如果從某個網域呼叫 [!DNL Target]，該網域便會顯示在此清單中。通常，您可以從編目引擎、語言翻譯工具網站或本機磁碟中看見網域。如果列出的網域不是您團隊使用的網域，則可以按一下[!UICONTROL 刪除]將它移除。

**我的 mbox 呼叫傳回 /* no display - unauthorized mbox host */**。

如果未授權的主機進行了 mbox 呼叫，該呼叫會以 /* no display - unauthorized mbox host */ 回應。

## 建議: 按環境 (主機群組) 篩選集合和排除項目

![Premium 徽章](/help/assets/premium.png)

您可以預覽所選環境 (主機群組) 的建議集合和排除項目。

>[!NOTE]
>建議活動是 Target Premium 解決方案內建的功能。在沒有 Target Premium 授權的 Target Standard 中無法使用。

主機群組可按不同用途，用來區隔目錄中的可用項目。例如，您可以將主機群組用於開發和生產環境、不同品牌或不同地理位置。依照預設，「目錄搜尋」、「集合」和「排除項目」中的預覽結果是根據預設主機群組所產生。(您也可以使用「環境」篩選器，選取不同的主機群組來預覽結果。)依照預設，除非在建立或更新項目時指定環境 ID，否則新增的項目可在所有主機群組中使用。提供的建議取決於要求中指定的主機群組。

如果沒有看見您的產品，請確定您使用正確的主機群組。例如，假設您將建議設定為使用測試環境，並將主機群組設為「測試」，則可能需要在測試環境中重建集合，才會顯示產品。若要查看每個環境中可用的產品，請對每個環境使用「目錄搜尋」。您也可以針對所選的環境 (主機群組)，預覽 Recommendations 集合和排除項目的內容。

>[!NOTE]
>在變更選取的環境後，您必須按一下「搜尋」來更新傳回的結果。

Target UI 中的下列位置提供「環境」篩選條件:

* 「目錄搜尋」([!UICONTROL 「建議 > 目錄搜尋」])
* 「建立集合」對話方塊 ([!UICONTROL 「Recommendations > 集合 > 新建」])
* 「更新集合」對話方塊 ([!UICONTROL 「Recommendations > 集合 > 編輯」])
* 「建立排除項目」對話方塊 ([!UICONTROL 「Recommendations > 排除項目 > 新建」])
* 「更新排除項目」對話方塊 ([!UICONTROL 「Recommendations > 排除項目 > 編輯」])
