---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: 提供最新或即將發行的DNL Adobe Target版本功能、增強功能和修正資訊的發行說明。
title: Adobe Target搶鮮版注意事項
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: ba4c776d93f911c122f36113a99ce4349b3c5524

---


# Target 版本說明 (發行前){#target-release-notes-prerelease}

以下版本說明提供最新或即將發行之 [!DNL Adobe Target] 版本的功能、增強功能、修正和已知問題等資訊。

**上次更新日期: 2020 年 25 月 3 日**

>[!NOTE]
>
>* 本文包含發行前資訊。 發行日期、功能和其他資訊可能會有所變更，恕不另行通知。若要檢視最新版本的相關資訊，請參閱 [Target 發行說明](release-notes.md)。這些頁面上的資訊可能相同或有所不同，端視發行的時間而定。
   >
   >
* 括號內的問題編號供 [!DNL Adobe] 內部使用。
   >
   >
* **TLS支援變更**:自2020年3月1日起，Target將停用對TLS 1.1和TLS 1.0加密的支援。 傳輸層安全性 (TLS) 是目前針對須透過網路安全交換資料的網頁瀏覽器和其他應用程式，部署最廣泛的安全通訊協定。需要進行此項變更，才能符合TLS 1.2或更高版本的公認安全性規範標準。 檢查您目前使用的TLS版本。 如果您的版本低於1.2，請在2020年3月1日之前實作必要的變更，以便繼續依預期使用Target。
   >
   >   
   如需更新實作可能影響的詳細資訊，以及您可能需要採取哪些步驟，請參閱 [TLS（傳輸層安全性）加密變更](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md)。
   >
   >
* **mbox.js淘汰**:自2020年8月30日起，Adobe Target將不再支援mbox.js程式庫。 在2020年8月30日發佈後，從mbox.js進行的所有呼叫都將失敗，並影響您執行Target活動的頁面。 我們建議所有客戶在此日期前移轉至最新版的at.js程式庫，以避免您網站出現任何潛在問題。 For more information, see [How At.js Works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md).
   >
   >   
   雖然目前支援mbox.js，但自2017年7月起，我們尚未提供此程式庫的功能更新。 較新的at.js提供許多優於mbox.js的優點。 除了其他優點外，at.js可改善Web實作的頁面載入時間、改善安全性，並為單頁應用程式提供更佳的實作選項。
   >
   >   
   透過將所有客戶移至at.js，我們的工程師和支援人員將能為您提供新功能，並提供您期待從Adobe獲得的支援。


## Target at.js（2020年3月25日）

下列是Target at.js JavaScript程式庫的新版本：

* at.js 2.3.0版
* at.js 1.8.1版

For more information, see [at.js version details](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md).

## Target Standard/Premium 20.2.1 (2020 年 3 月 23 日)

>[!IMPORTANT]
>
>請參閱上述有關mbox.js取代的資訊。

此發行包含下列增強功能、修正和變更：

* 修正客戶在執行目錄搜尋時無法選取系列的問題。 (TGT-36230)
* 已修正此問題：透過API建立但未由Target UI中建立之活動所參照的准則，可能會從UI中錯誤刪除。 (TGT-35917)
* 已實作內容安全性政策(CSP)的安全性改進。 (TGT-36190)
* 修正將「屬性加權」百分比列滑至最左側時，顯示「NaN%」的問題。 (TGT-36211)
* 已解決本地化問題，讓各種語言的UI文字可正確顯示。
* 我們淘汰目前Adobe Analytics API版本不支援的Adobe Analytics量度，標準化了Adobe Analytics for Target(A4T)活動的可用量度清單。 這可讓我們在未來的Adobe Target版本中擴充A4T支援。

   已進行下列變更：

   * 「頁面平均逗留時間」已取代為「網站平均逗留時間」。 任何使用此作為主要目標量度的活動都會有「網站平均逗留時間」(注意：測量單位為分鐘（而非秒），在下次編輯活動時選取為主要目標量度。
   * 「訪客」已由「獨特訪客」取代。 使用此量度作為主要目標量度的任何活動，在下次編輯活動時，都會將「獨特訪客」選為主要目標量度。

* 下列量度已過時，在建立新的A4T活動時，無法再選為主要目標量度。

   | 過時的量度 | 建議的取代量度 |
   |--- |--- |
   | 每日訪客、每小時訪客、每月訪客、每季訪客、每週訪客、每年訪客 | 獨特訪客 |
   | 平均存取深度 | n/a。未建議作為主要目標量度 |
   | 機器人 | n/a。未建議作為主要目標量度 |
   | 行動裝置當機率、行動裝置平均上一階段作業長度、行動應用程式商店平均排名、行動裝置應用程式效能當機率、行動裝置應用程式商店平均評分 | n/a。未建議作為主要目標量度 |

## 發行前資訊 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要收到 Target 和其他 Adobe Experience Cloud 解決方案日後產品增強功能的提前通知，請註冊 Adobe 優先產品更新:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
