---
keywords: 擷取分數; 分數
description: 瞭解Adobe [!DNL Target]中的「擷取分數」參與量度，該量度會根據指派給網站上造訪頁面的值，計算彙總分數。
title: 擷取分數量度是什麼？
feature: Success Metrics
exl-id: 3446cdef-7ee0-40dd-bf17-27def56668d4
TQID: 'https://experienceleague.adobe.com/iqCPEY9x7Lg9TlAhxn8e-B1XOnUfNgUWFdOf8Bw2F3w'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: dfc8a233-f2b5-4811-bf63-b4262aebc5a5
    internal-label: Administration and configuration
subfeature_v2:
  - id: eb2bfbe8-b0f3-4cc3-ae8d-af79179585eb
    internal-label: Success metrics
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 8c6f23b495228ab930e6649aa2f9e6dae506cae2
workflow-type: tm+mt
source-wordcount: '834'
ht-degree: 13%
---
# 擷取分數 {#capture-score}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解「擷取分數」參與量度如何計算造訪分數，以及如何指派分數至頁面。

>[!ENDSHADEBOX]

[!DNL Adobe Target]中的擷取分數參與量度會根據指派給訪客在您網站上檢視之頁面的值，計算彙總分數。 此分數從訪客第一次看到活動的第一個顯示[!DNL Target]要求點開始。

下列範例說明如何在測試兩個體驗（一個有貓影像，一個有狗影像）的活動中計算分數。

![貓咪體驗造訪的頁面流量，每個頁面都有分數](assets/example_score.png)

在此範例中，第一個訪客會看到貓體驗。 假設全域[!DNL Target]請求根據頁面的值傳入頁面分數。 如果行銷人員已擷取與&#x200B;**任何Target請求**&#x200B;相關聯之成功量度的頁面計數參與度，則會針對在貓圖片的四周顯示請求後出現的任何請求累計瀏覽分數。

第一個頁面會新增1至分數、第二個頁面0.25、第三個頁面0.10以及第四個頁面0.10，總計為1.45。 此總計可解譯為貨幣或點。 在另一次造訪中，訪客會看到狗狗體驗。 雖然此訪客檢視的頁面較少，但分數為2.10，高於其他造訪，因為訪客檢視了較有價值的頁面。

您可以考慮透過傳遞 adbox 和重新導向程式，來採用贏取成本和附屬單位連結收入，如以下的頁面流程中所述。 在此範例中，文章頁面上的兩個[!DNL Target]請求都會傳遞分數，可能代表已知的CPM。

![頁面流程，其贏取成本和附屬機構連結收入以分數傳遞](assets/example_score2.png)

## 指派頁面分數

您可以根據頁面的價值，在網站上為任何頁面指定一個值。 例如，烹飪網站在其特色文章頁面上可以比在其體驗區段以更高的價格銷售廣告。 因此，功能文章會比體驗區段更有價值。 頁面分數可讓您發展造訪的總體「價值」，因此閱讀更多功能文章的人，會比只瀏覽體驗的人獲得更多「分數」。

指定頁面分數共有以下兩種方法:

* 在[!DNL Target]要求中，建立名為`mboxPageValue`的引數。

  範例: `('global_mbox', 'mboxPageValue=10');`

  每次檢視帶有[!DNL Target]請求的頁面時，指定的值都會新增至分數。 如果頁面上的多個請求包含分數值，則頁面分數是所有請求值的總計。 `mboxPageValue`是保留的引數，用於將值傳入[!DNL Target]要求以擷取參與分數。 可傳入正值和負值。 總和會在每次造訪結束時計算，以判斷造訪的總分。

* 在頁面URL中傳遞`?mboxPageValue=n`引數。

  範例: `https://www.mydomain.com?mboxPageValue=5`

  指定的值會新增至頁面上每個[!DNL Target]要求的分數。 例如，若您傳遞引數`?mboxPageValue=10`，而頁面上共有三個[!DNL Target]請求，則頁面分數為30。

>[!NOTE]
>
>計數器以活動的第一個顯示要求開頭，而非專案要求，而分數中不包含位於該要求上方的[!DNL Target]要求。 例如，如果您在首頁上輸入沒有顯示要求的活動，然後連結至包含顯示要求的目錄頁面，則當您移至目錄頁面時，計數器會開始。

最佳做法是指派[!DNL Target]請求中的值。 此方法可讓您根據每個請求的內容，精確測量值。

>[!NOTE]
>
>為了便於維護，您可以在[!DNL at.js]檔案中，使用某些條件式JavaScript邏輯來設定網站的頁面分數值指派。 此方法讓您不需要在頁面中新增更多程式碼。 請連絡您的帳戶顧問以取得協助。

您可以併用兩種方法，但可能會導致分數高於預期值。 例如，您為三個[!DNL Target]請求中的每一個指派值10，而為第四個請求指派無分數，然後傳遞URL引數`?mboxPageValue=5`。 頁面的分數是50：對於指派值的三個請求為30，加上URL引數為20 （頁面上四個請求中的每一個為5）。

您也可以針對需要花費金錢或不適合訪客瀏覽的特定頁面，來傳遞負值。 負值也會影響整體分數。 訪客從廣告觸及的頁面上可使用此技巧，以便您瞭解CPC有多少。 它也可用於支援或聯絡頁面，讓訪客致電或要求協助。
