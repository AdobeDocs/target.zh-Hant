---
keywords: troubleshooting;frequently asked questions;FAQ;FAQs;global;global mbox
description: 關於全域 mbox 常見問題集 (FAQ) 的清單。
title: 全域 mbox 常見問題
feature: client-side
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 100%

---


# 全域 mbox 常見問題{#global-mbox-frequently-asked-questions}

關於全域 mbox 常見問題集 (FAQ) 的清單。

## 如果我的 Target 帳戶設定為跨多個網域，我可以有多個全域 mbox 嗎? {#section_B7252BA6C3BB4EF4AE9E53F47FD58ABD}

整個帳戶僅支援一個全域 mbox。

您可以在活動中新增 URL 規則，以限制執行活動的位置。如需詳細資訊，請參閱[在類似頁面上包含相同體驗](/help/c-experiences/c-visual-experience-composer/temtest.md#task_2539D51A18044F82B0D9895636546781)。

您也可以使用 [targetPageParams](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparams.md) 傳遞頁面上的參數，然後在[!UICONTROL 可視化體驗撰寫器] (VEC) 的「設定 URL」區段中選取參數，或在表單式體驗撰寫器中將參數新增為「細分」。

## 我該如何在 Target 全域 mbox 上傳遞收入資料? {#section_17AEA933BADA4D169CCEDF5833C41306}

若要在 target-global-mbox 上收集收入和訂單資訊，必須將「mbox 參數」傳送至 Target。這些參數為名稱/值配對，用來傳送更多資訊給 Target。Target 會自動尋找這些參數 (保留名稱) 以填入收入資料。

對於 `orderConfirmPage`，您應該傳入 `orderId`、`orderTotal` 和 `productPurchasedId`。如需詳細資訊，請參閱[建立訂購確認 mbox - mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/orderconfirm-create.md#task_0036D5F6C062442788BB55E872816D82)。

同樣的這些參數必須透過 `targetPageParams()` () 傳送至·target-global-mbox。如需詳細資訊，請參閱[將參數傳遞至全域 mbox](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/pass-parameters-to-global-mbox.md#concept_33362A04146C4E3C8E7089B65F38B5E5)。

您也可以將鎖定目標新增至轉換部分，以便只有在看過訂單確認頁面後，Target 才會在 target-global-mbox 上統計轉換，如下所示:

![](assets/revenue1.png)

上面顯示的「網站頁面」區段包含下列選擇: 目前頁面、URL、包含、orderconfirm。

![](assets/revenue2.png)

上圖中的選項包含下列設定:

* **您要測量這個活動的什麼?:**&#x200B;收入
* **報告的預設檢視:**&#x200B;每次造訪帶來的收入 (RPV)
* **對象採取什麼動作來指出已達到您的目標?** 已檢視 mbox、target-global-mbox