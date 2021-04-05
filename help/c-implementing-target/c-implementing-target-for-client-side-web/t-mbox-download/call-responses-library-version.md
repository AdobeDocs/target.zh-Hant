---
description: 瞭解Adobe Target的舊版mbox.js實作。 移轉至Adobe Experience Platform網頁SDK（AEP網頁SDK）或最新版的at.js。
title: mbox.js使用哪些頁面方法？
feature: at.js
role: 開發人員
exl-id: a0f7b956-7855-4165-b34c-33d81a8fac55
translation-type: tm+mt
source-git-commit: 0a685427a047bfc0a2f5e81525b32df70af6d69f
workflow-type: tm+mt
source-wordcount: '931'
ht-degree: 88%

---

# 根據 mbox.js 程式庫版本鎖定頁面方法{#target-page-methods-by-mbox-js-library-version}

Target 進行和回應來自您頁面呼叫的方法，取決於您所使用的 Target 資料庫、是否實作 Experience Cloud 訪客 ID，以及是否有訪客 ID 存在。

>[!IMPORTANT]
>
>**mbox.js生命週期結束**:自2021年3月31日起， [!DNL Adobe Target] 不再支援mbox.js程式庫。自2021年3月31日起，從mbox.js進行的所有呼叫都會輕鬆失敗，並透過提供預設內容而影響執行[!DNL Target]活動的頁面。
>
>我們建議所有客戶在此日期前移轉至新[!DNL Adobe Experience Platform Web SDK]或at.js JavaScript程式庫的最新版本，以避免網站出現任何潛在問題。 如需詳細資訊，請參閱[概述：實作用戶端Web的Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)。

>[!NOTE]
>
>如果您使用 [!DNL at.js]，則會使用 JSON 執行所有呼叫。此頁面提供 [!DNL mbox.js] 程式庫版本的詳細資料。下列案例所述的行為不適用於 [!DNL at.js]。

在下列各案例中，針對每個 [!DNL Target] 程式庫版本如何回應來自頁面的 [!DNL Target] 呼叫，本節提供相關資訊。

視您的實作和程式庫版本而定而有多種類型或端點。您必須熟悉每個類型，才能瞭解每個案例中 [!DNL Target] 如何回應呼叫。

| 類型/端點 | 呼叫方法 | 回應內容 |
|--- |--- |--- |
| 自動建立全域 mbox - 同步 | document.write 以進行呼叫 | JavaScript 不帶 document.write() |
| 自動建立全域 mbox - 非同步 | createElement() 以附加呼叫至主體 | JavaScript 不帶 document.write() |
| 標準 | document.write 以進行呼叫 | JavaScript 含 document.write() |
| ajax | createElement() 以附加呼叫至主體 | JavaScript 不帶 document.write() |
| json | XMLHTTPrequest() 執行呼叫 | 傳回 JSON 回應 |

>[!IMPORTANT]
>
>對於 standard 以外的任何類型，所有自訂程式碼和選件皆應撰寫為支援 ajax 環境。例如，如果您使用包含 `document.write()` 的 JavaScript，指令碼將無法如運期般運作。

## 沒有訪客 ID 實作 {#section_C6F7213FDE4D48E8BBCB1A9A26310FEE}

如果您使用 [!DNL Target Standard] 或 [!DNL Premium] 並搭配 [!DNL mbox.js]，且您的帳戶已啟用[!UICONTROL 建立全域 Mbox]，則會執行 **autocreate global mbox synchronous** 類型的呼叫和回應，而不會考慮 [!DNL mbox.js] 版本。

如果您撰寫自訂的自訂程式碼，而不使用[!UICONTROL 可視化體驗撰寫器]動作，請確定您的程式碼適用於 ajax 環境。例如，如果您使用包含 `document.write()` 的 JavaScript，指令碼將無法如運期般運作。

>[!NOTE]
>
>具有相同 mbox 名稱但不同參數的多個 ajax mbox 呼叫將無法在同一個頁面上運作。僅會發出第一次呼叫。

如果您使用「auto-create global mbox」，但頁面上也有 `mboxCreate` 呼叫，假設您想在先前於舊版實作中使用的頁面上實作 [!DNL Target Standard] 或 [!DNL Premium]，則系統會使用 ** autocreate global mbox - standard** 端點執行全域 mbox 呼叫，並使用 `mboxCreate`standard **端點執行** 呼叫。**standard** 端點使用 `document.write()` 來執行呼叫和回應。這樣會防止頁面載入，包括 ajax 回應中傳送的內容，直到所有資訊皆下載為止。

例如，在使用 [!DNL Target Classic] 所建立的頁面上，如果您只使用 mboxCreate，則頁面會照常運作。

| 建立方法 | mbox.js 57 版 | mbox.js 58 版 | mbox.js 59 版 | mbox.js 60 版 |
|---|---|---|---|---|
| 自動建立全域 mbox | 自動建立全域 mbox - 同步 | 自動建立全域 mbox - 同步 | 自動建立全域 mbox - 同步 | 自動建立全域 mbox - 同步 |
| mboxCreate | 標準 | 標準 | 標準 | 標準 |

## 訪客 ID 實作存在，但未設定訪客 ID  {#section_29888A119C7A4753AD287FC845AA63F4}

如果尚未設定訪客 ID，則不會有使用者的 [!DNL Experience Cloud] 訪客 Cookie。頁面會呼叫訪客 ID 服務來取得訪客 ID。會以呼叫 [!DNL Target]Target 的 ID 來等待回應。

>[!NOTE]
>
>[!DNL Mbox.js]強烈建議使用 v58，以確保在執行 Target 呼叫之前傳回訪客 ID。

如果您在此案例中使用 [!DNL mbox.js] 版本 57，只要沒有訪客 ID 實作 (如上一個案例所述)，則一切皆沒問題。自 [!DNL mbox.js] 58 版開始，[!DNL Experience Cloud Visitor ID] 服務會在執行 [!DNL Target] 呼叫之前傳回訪客 ID。這可確保透過「設定檔和對象」核心服務共用的對象資料，可供訪客工作階段中的第一次 [!DNL Target] 呼叫使用。為了避免傳回測試內容前的預設內容發生忽隱忽現的情形，[!DNL Target] 會隱藏 `<BODY>` 直到訪客 ID 服務返回為止。在版本 58 中，`display:none` 用於隱藏頁面。這會對有回應的網站造成一些問題，所以自版本 59 開始，就使用 `opacity:0` 來隱藏內容。

| 建立方法 | mbox.js 57 版 | mbox.js 58 版 | mbox.js 59 版 | mbox.js 60 版 |
|---|---|---|---|---|
| 自動建立全域 mbox | 自動建立全域 mbox - 同步 | 自動建立全域 mbox - 非同步 | 自動建立全域 mbox - 非同步 | 自動建立全域 mbox - 非同步 |
| mboxCreate | 標準 | ajax | ajax | ajax |

## 訪客 ID 實作存在，訪客 ID 也存在  {#section_9CD4AE4C8186425D886398BC3CE6C46D}

如果訪客 ID Cookie 存在，[!DNL Target] 就不需要呼叫訪客 ID 服務。在此情況下，顯示內容之前不需要等待訪客 ID 服務。若為版本 57 至 59，則是使用 **autocreate global mbox - synchronous** 類型，所以頁面會等待 [!DNL Target] 的呼叫返回，才繼續載入。這可確保預設內容不會忽隱忽現。若為 v60，則是使用 **global mbox-asynchronous type**，以確保 [!DNL Target] 會等待 [!DNL Experience Cloud] 退出服務有所回應。退出服務是 2016 年秋天推出的 Data Co-op 的一部分。因為所有呼叫皆使用 ajax 來傳回，請勿在 [!DNL mbox.js] 60 版中使用 `document.write()`。

| 建立方法 | mbox.js 57 版 | mbox.js 58 版 | mbox.js 59 版 | mbox.js 60 版 |
|---|---|---|---|---|
| 自動建立全域 mbox | 自動建立全域 mbox - 同步 | 自動建立全域 mbox - 同步 | 自動建立全域 mbox - 同步 | autocreate global mbox - asynchronous (支援開發 Data Co-op，已於 2016 年下半年推出) |
| mboxCreate | 標準 | 標準 | 標準 | ajax |
