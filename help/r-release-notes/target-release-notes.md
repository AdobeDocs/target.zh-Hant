---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes
description: 提供最新或即將發行的DNL Adobe target版本功能、增強功能和修正資訊的發行說明。
title: Adobe target搶鮮版注意事項
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 93ffd24946ad23780b8c141bec79e4492f0e8cda

---


# Target 版本說明 (發行前){#target-release-notes-prerelease}

以下版本說明提供最新或即將發行之 [!DNL Adobe Target] 版本的功能、增強功能、修正和已知問題等資訊。

**最後更新日期: 2020 年 2 月 18 日**

>[!NOTE]
>
>* 本文包含發行前資訊。 發行日期、功能和其他資訊可能會有所變更，恕不另行通知。若要檢視最新版本的相關資訊，請參閱 [Target 發行說明](release-notes.md)。這些頁面上的資訊可能相同或有所不同，端視發行的時間而定。
   >
   >
* 括號內的問題編號供 [!DNL Adobe] 內部使用。
   >
   >
* 自2020年3月1日起，Target將停用對TLS 1.1和TLS 1.0加密的支援。 傳輸層安全性 (TLS) 是目前針對須透過網路安全交換資料的網頁瀏覽器和其他應用程式，部署最廣泛的安全通訊協定。需要進行此項變更，才能符合TLS 1.2或更高版本的公認安全性規範標準。 檢查您目前使用的TLS版本。 如果您的版本低於1.2，請在2020年3月1日之前實作必要的變更，以便繼續依預期使用Target。
   >
   >   
   如需更新實作可能影響的詳細資訊，以及您可能需要採取哪些步驟，請參閱 [TLS（傳輸層安全性）加密變更](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md)。


## Target Standard/Premium 20.2.1 (2020 年 2 月 19 日)

此發行包含下列增強功能和修正：

* 修正客戶在執行目錄搜尋時無法選取系列的問題。 (TGT-36230)
* 已修正此問題：透過API建立但未由Target UI中建立之活動所參照的准則，可能會從UI中錯誤刪除。 (TGT-35917)
* 已實作內容安全性政策(CSP)的安全性改進。 (TGT-36190)
* 修正將「屬性加權」百分比列滑至最左側時，顯示「NaN%」的問題。 (TGT-36211)
* 解決客戶無法將「自動個人化」(AP)活動中的演算法從「隨機森林」變更為「殘留變數」的問題。 (TGT-36321)
* 已解決本地化問題，讓各種語言的UI文字可正確顯示。

## 發行前資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到 Target 和其他 Adobe Experience Cloud 解決方案日後產品增強功能的提前通知，請註冊 Adobe 優先產品更新:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
