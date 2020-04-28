---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates
description: 這些版本說明提供關於每個 Adobe Target Standard 和 Target Premium 版本功能、增強功能、修正和已知問題的資訊。
title: 'Adobe Target 版本說明 (最新) '
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: 00e69d8887cb79eb81b602a519d4b92d31612dad

---


# Target 版本說明 (最新){#target-release-notes-current}

這些版本說明提供關於每個 Target Standard 和 Target Premium 版本功能、增強功能和修正的資訊。此外，Target API、SDK、JavaScript程式庫(at.js)的發行說明，以及其他平台變更（如適用）也會隨附。

>[!NOTE]
>
>* **mbox.js淘汰**:自2020年8月30日起，Adobe Target將不再支援mbox.js程式庫。 在2020年8月30日發佈後，從mbox.js進行的所有呼叫都將失敗，並影響您執行Target活動的頁面。 我們建議所有客戶在此日期前移轉至最新版的at.js程式庫，以避免您網站出現任何潛在問題。 For more information, see [How At.js Works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md). 請參 *閱Adobe Target技能產生器：開發人員聊天、將Adobe Target的mbox.js移轉至下方的at.js* ，以取得註冊即將進行的開發人員聊天的相關資訊。
   >
   >   
   雖然目前支援mbox.js，但自2017年7月起，我們尚未提供此程式庫的功能更新。 較新的at.js提供許多優於mbox.js的優點。 除了其他優點外，at.js可改善Web實作的頁面載入時間、改善安全性，並為單頁應用程式提供更佳的實作選項。
   >
   >   
   透過將所有客戶移至at.js，我們的工程師和支援人員將能為您提供新功能，並提供您期待從Adobe獲得的支援。


括號內的問題編號供 [!DNL Adobe] 內部使用。

## Adobe Target Skill Builder:開發人員聊天，將Adobe Target的mbox.js移轉至at.js {#skill-builder}

與Adobe Target產品經理David Son一起，說明將mbox.js移轉至at.js的優點。 聽聽最新的at.js更新，瞭解其增強功能以及這些功能如何與技術領域的大趨勢一致，以及一些實用秘訣，以確保您在從mbox.js移轉至at.js時，能夠從Target中獲取同樣多的價值。 Adobe Target開發人員不會想錯過這個！

5月5日，星期二，上午8:00 - 9:00(PDT)

[立即註冊！](https://atskillbuilder-devchat.experienceleague.adobeevents.com/)

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

## Adobe Experience Cloud導覽（2019年2月22日）

* 當您登入時， [!DNL Adobe Experience Cloud]將會進入新的標題導覽。 它看起來與先前的導覽非常類似，頂端有黑色列，但提供下列改良功能：

   * 更輕鬆地在 [!DNL Identity Management System] (IMS)組織間切換或切換至不同的解決方案。
   * 改進的使用者說明：搜尋結果包括產品文 [!DNL Target] 件、社群論壇和更多視訊內容，讓您更輕鬆地存取更多內容，以協助您發揮最大效益 [!DNL Target]。 我們也直接在「說明」功能表中新增了意見回 [!UICONTROL 饋機制] ，讓您更輕鬆地報告問題或分享您的想法。

   * 改善網路推廣者分數(NPS)回饋功能，讓調查模式不會干擾您的工作流程。
   * 已改善登入流程。 以前，所 [!DNL Target] 有客戶在按一下頁首中的圖示後，就會著陸 [!DNL Target] 至Target登陸頁面。 然後，本頁允許客戶繼續使用 [!DNL Target Standard/Premium]、 [!DNL Search&Promote]或 [!DNL Recommendations Classic]，如下所示：

      ![登陸頁面](/help/r-release-notes/assets/landing.png)

      我們已取消所有客戶的登陸頁面。 現在，只要按一下新標題導覽列中的 [!UICONTROL 圖示，您就一律會直接進入「活][!DNL Target] 動清單」頁面。

      如果您使 [!DNL Recommendations Classic]用，您可以直接前往解決方案，或從Recommendations標籤上建立的簡短連結  ，如下所示：

      ![Recs Classic深層連結](/help/r-release-notes/assets/recs-classic.png)

      如果您使 [!DNL Search&Promote]用，您必須直接前往 [Search&amp;Promote URL](https://center.atomz.com/center/?ims=1) (https://center.atomz.com/center/?ims=1)。 從內部到達 [!DNL Search&Promote] 的路徑已 [!DNL Adobe Target] 完全移除。

   * 頁首的 [!DNL Target] 「通知」下拉式清單 [!UICONTROL 中] ，目前無法使用的通知。
   >[!NOTE]
   >
   >在新導覽列的推出過程中，您也會注意到一些URL變更。 所有先前的書籤化連結都會繼續運作，但我們鼓勵您將新連結加入書籤，以加快開啟速度。

## 其他發行說明和版本詳細資訊

| 資源 | 詳細資料 |
|--- |--- |
| [發行說明——目標伺服器端API](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md) | 與Adobe Target伺服器端API相關的發行說明。 |
| [發行說明- Target Node.js SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md) | 與Adobe Target的Node.js SDK相關的發行說明。 |
| [發行說明——目標Java SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-target-java-sdk.md) | 與Adobe Target Java SDK相關的發行說明。 |
| [at.js 版本詳細資料](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Adobe Target at.js JavaScript程式庫各版本變更的詳細資訊。 |
| [mbox.js 版本詳細資料](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mboxjs-change-log.md) | 本頁面顯示每個 mbox.js 版本的變更。<br>請注意，mbox.js程式庫已不再開發。 所有客戶應該從 mbox.js 移轉至 at.js。 |

## 文件變更、過去的版本說明和 Experience Cloud 版本說明 {#section_1BC5F5208DA548E9B4344A0836E4B943}

除了每次發行的說明，下列資源也提供額外資訊:

| 資源 | 詳細資料 |
|--- |--- |
| 文件變更 | 檢視在版本說明中可能未涵蓋的手冊更新詳細資訊。<br>如需詳細資訊，請參閱[文件變更](../r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| 舊版版本說明 | 檢視舊版 Target Standard 和 Target Premium 中新功能和增強功能的詳細資訊。<br>如需詳細資訊，請參閱[舊版版本說明](../r-release-notes/release-notes-for-previous-releases.md). |
| Adobe Experience Cloud 版本說明 | 檢視 Adobe Experience Cloud 解決方案的最新版本說明。<br>如需詳細資訊，請參 [閱Experience Cloud發行說明](https://docs.adobe.com/content/help/en/release-notes/experience-cloud/current.html)。 |

## 發行前資訊 {#section_5D588F0415A2435B851A4D0113ACA3A0}

以下資源告訴您下個 Target 版本將推出哪些功能。

| 資源 | 詳細資料 |
|--- |--- |
| Adobe 優先順序產品更新清單 | 若要接收即將推出的 Target 產品增強功能與其他 Adobe Experience Cloud 解決方案的進階通知，請註冊 Adobe 優先產品更新：<br>[](https://www.adobe.com/subscription/priority-product-update.html)https://www.adobe.com/subscription/priority-product-update.html |
| 即將發佈的發行說明 | 如需本月的 Target 版本的詳細資訊，包括發行前資訊，請參閱 [Target 版本說明 - 發行前](/help/r-release-notes/target-release-notes.md)頁面。 |
