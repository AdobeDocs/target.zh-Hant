---
keywords: 發行說明;發行;更新;未來發行;增強;新功能;修正;更新;發行說明
description: 了解 Adobe Target 目前版本包含的新功能、增強功能和修正，其中包括 SDK、API 和 JavaScript 程式庫。
title: 即將發佈的版本中包括哪些新功能和增強功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 83a7fb03dcf334cb82eb507d2803e955a655b40a
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 23%

---

# Target 發行說明 (發行前)

本文包含發行前資訊。發行日期、功能和其他資訊可能會有所變更，恕不另行通知。

**最近更新: 2022 年 5 月 5 日**

若要檢視目前版本的相關資訊，請參閱「[Target 發行說明](release-notes.md)」。 這些頁面上的資訊可能會相同 (視發佈時間而定)。 括號內的問題編號供 [!DNL Adobe] 內部使用。

## [!DNL Target Standard/Premium] 22.5.1（錯開釋放）2022年5月10至12日)

此版本將按以下交錯計畫提供：

* **5月10日**:歐洲、中東和非洲(EMEA)地區
* **5月11日**:亞太區
* **5月12日**:北美(NA)地區

此版本包含以下增強和修復：

* 修復了導致JavaScript錯誤並阻止某些客戶訪問某些活動詳細資訊的問題 [!UICONTROL Automated Personalization] （美聯社）活動。 (TGT-43526)
* 修復了阻止某些客戶向AP活動添加（或編輯）特定優惠的問題。 (TGT-43503)
* 已修復 [!DNL Target] 顯示以下錯誤消息的UI:「您的全局框可能不同步。 請嘗試重新儲存。」此問題是UI問題，不會影響客戶的實施。 (TGT-43475)
* 修復了一個問題，如果在新操作之前建立了改進和受眾，則該問題會阻止一個客戶編輯活動的體驗級改進和受眾 [!UICONTROL 觀眾] 已部署UI。 (TGT-43433)
* 修復允許客戶選擇重複的問題 [!DNL Adobe Audience Manager] (AAM)編輯活動的報告受眾時的受眾。 (TGT-43430)
* 已修復一個問題，該問題阻止客戶建立重複的受眾，但是位於不同的工作區中。 (TGT-43423)
* 修復了一個問題，使客戶無法刪除在中建立的活動中具有臨時優惠的位置 [!UICONTROL 基於表單的體驗作曲家]。 (TGT-43315)
* 在按一下影像提供並刷新UI後，修復了阻止客戶訪問代碼提供的問題。 (TGT-43566)
* 已確保中可用的度量清單 [!DNL Target] 建立使用 [!DNL Analytics for Target] (A4T)僅顯示由 [!DNL Adobe Analytics]。 (TGT-43294)
* 修復了有時導致 [!UICONTROL 設定] 頁面請求失敗。 例如，更改&quot;[!UICONTROL 報告Experience Cloud解決方案]「 」選項[!UICONTROL 分析]&quot;到&quot;[!UICONTROL 目標]&quot;或&quot;[!UICONTROL 按活動選擇]。 (TGT-43272)
* 修復了有時導致配置檔案指令碼更改無法正確更新的問題。 (TGT-43249)
* 修復了在嘗試將受眾移動到另一個工作區時導致以下錯誤的問題：「我們無法完成您的請求。 如果問題仍然存在，請與Adobe客戶服務部聯繫。」 (TGT-43212)
* 已修復在克隆單頁應用()頁的自定義代碼修改時導致SPA錯誤的錯誤。 (TGT-43137)
* 已更改中處理「頁面視圖」度量的方SPA式。 而不是在中顯示頁面URL [!DNL Target] UI,UI現在顯示&quot;view&quot;。 (TGT-41200)
* 修復了在複製經驗並編輯促銷後導致原始促銷受到影響的問題。 (TGT-41775)

## 發行前資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

接收有關即將進行的產品增強的預先通知， [!DNL Target] 其他 [!DNL Adobe Experience Cloud] 解決方案，註冊 [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/tw/subscription/priority-product-update.html](https://www.adobe.com/tw/subscription/priority-product-update.html)
