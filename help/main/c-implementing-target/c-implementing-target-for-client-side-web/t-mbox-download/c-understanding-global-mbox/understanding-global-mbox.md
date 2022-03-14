---
keywords: global mbox;;implement at.js
description: 瞭解Adobe Target的全局框，該名稱用於引用您的每個網頁頂部發出的單個伺服器調用 [!DNL Target] 執行。
title: 什麼是全球框？
feature: at.js
role: Developer
exl-id: 84d15feb-f5df-4879-ae35-a7f455c1b20f
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 82%

---

# 瞭解全域 mbox

關於全域 mbox 的資訊，此名稱用來指稱在您的 [!DNL Adobe Target] 實作中的每個網頁頂端進行的單一伺服器呼叫。

依預設，全域 mbox 的名稱為 `target-global-mbox`。必要的話，可以為您的帳戶來重新命名它。

一般 mbox (非全域 mbox) 和全域 mbox 之間有幾項差異，包括:

| 一般 mbox | 全域 mbox |
|--- |--- |
| 一般 mbox 通常會以 `<DIV>` 標籤包住內容。 | 全域 mbox 為「空白」，不會包住任何內容。 |
| 只來自一個活動的內容可以透過一般 mbox 來傳送。 | 來自多個活動的內容可以透過傳給全域 mbox 的一個回應來傳送。 |

如果透過全域 mbox 或多個一般 mbox 傳送多個活動，[!DNL Target] [會決定優先順序](/help/main/c-activities/priority.md#concept_1780C11FEA57440499F0047DD6900E0F)，並按照此優先順序將活動傳送至網頁。

使用 [!DNL Target] 函式，可將其他頁面層級資料連同全域 mbox 一起傳送至 `targetPageParams`。這類似於 mbox 參數功能。如需詳細資訊，請參閱[將參數傳遞至全域 mbox](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/pass-parameters-to-global-mbox.md#concept_33362A04146C4E3C8E7089B65F38B5E5)。
