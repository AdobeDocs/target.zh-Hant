---
keywords: troubleshoot target;troubleshooting target;default content;test not live;activity not live;targeting not working;previous experience displays;cannot create activities;can't create activities;create activities;page structure changed;page structure modified;error message;error delete profile script;ajax not working
description: 如果您的活動未出現在網站上，這些疑難排解建議應可協助您尋找您的解決方案。
title: 疑難排解活動
feature: activities
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '799'
ht-degree: 81%

---


# 疑難排解活動{#troubleshoot-activities}

如果您的活動未出現在網站上，這些疑難排解建議應可協助您尋找您的解決方案。

>[!NOTE]
>
>除了下列疑難排解資訊，請參閱[疑難排解 Target](/help/r-troubleshooting-target/troubleshooting-target.md#reference_A9DB82675D044BD8861F6752A4EE6839) 中提供的連結，取得其他疑難排解主題、常見問題集和疑難排解活動與其他 [!DNL Adobe Target] 功能的其他實用資訊。

以下各節包含您可能會遇到的問題，並提供建議的解決方案。

## 我使用Target UI建立活動，但無法透過API進行更新。

使用Target UI建立的活動應透過Target UI更新。 透過API建立的活動應透過API更新。 例如，如果您最初使用API建立活動，但稍後透過Target UI編輯活動，則不會更新所有變更。 所有變更都儲存在後端，並可進行其他API呼叫來更新。

最佳實務是，嘗試使用與原始建立活動相同的方法（UI或API）來更新活動。

## 您看到的是預設內容。

請確定活動已完成且已啟動。

## 活動未上線。

**驗證:** 前往「概覽」標籤，查看測試是否標示為非使用中或草稿。

**選項:**

* 啟動測試。
* 使用「預覽連結」來顯示非使用中的測試。

## 您不符合對象鎖定目標條件。

**驗證:**&#x200B;檢閱概覽頁面上的鎖定目標條件。

**選項:**

* 設法符合資格，然後再試一次。
* 使用「預覽連結」以避開鎖定目標條件。

## 頁面不符合頁面鎖定目標條件。

**驗證:**&#x200B;在概覽頁面上，判斷頁面是否落在鎖定目標條件之外。

**選項:**

* 前往可視化體驗撰寫器，按一下「URL > 進階 > [目前頁面]」。

## 出現上一個體驗，而非新的體驗。

**驗證:** 嘗試下列其中一個選項，並試著再次檢視體驗。

**選項:**

* 清除快取和 Cookie，然後再試一次。

* 嘗試不同瀏覽器。
* 使用私人/無痕模式。

## 您最近加入 Target，但無法建立活動。

**驗證:**&#x200B;按一下「建立活動」。如果無法使用此選項，很可能是您沒有足夠權限來建立活動。

**選項:**

當您加入 Target 中成為使用者時，需要具有「核准者」角色，才能建立活動。

* 請要求帳戶的管理員將您變成「核准者」。
* If you are the Admin, give yourself the Approver role from **[!UICONTROL Administration]** > **[!UICONTROL Users]** in Target.

   請參閱[將核准者角色指派給您自己](/help/administrating-target/start-target.md#task_15CAA437A71444E2932B333D5E66A3C7)。

## 頁面的結構自從設定活動後已變更。

**驗證:** 前往可視化體驗撰寫器來查看現有活動。尋找指出選取器 (或結構) 已變更的警告訊息。

**選項:**

* 重建活動。

如需關於頁面修改如何影響 Target 顯示功能的資訊，請參閱[頁面修改案例](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB)。

## 頁面的結構在頁面載入期間 (執行階段) 已修改。

**驗證:** 詢問開發人員。

**注意:** 為了讓 Target 辨識應該在何處套用活動變更，請避免動態插入相同類別的元素，或動態修改任何同層級的類別。

**選項:**

* 更新頁面程式碼 (使用 ID) 來唯一識別每個將測試的元素。
* 如上所述，停止動態修改類別或同層級。

如需關於頁面修改如何影響 Target 顯示功能的資訊，請參閱[頁面修改案例](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB)。

## mbox.js 會將 head 中所有後續的程式碼丟入 body 中。

**驗證:** 檢視原始碼，查明在 mbox.js 檔案後面到結尾`</body>`標記之前是否有宣告。

**選項:**

* 將 mbox.js 放在頁面的 `<head>` 區段內當作最後一項。
* 在內文內的最高層級元素上使用不重複的 div ID。

## 其他活動正在相同頁面上執行。

**驗證:** 使用「衝突」標籤查看其他活動是否正在執行。

**注意:**「衝突」標籤不適用於「範本測試」模組。

**選項:**

* 提高此活動的優先順序。
* 降低其他活動的優先順序。
* 停用其他活動。

## 刪除設定檔指令碼時出現錯誤訊息。

**驗證:** 從 Target Standard/Premium 中刪除設定檔指令碼時，會顯示錯誤訊息「無法刪除設定檔指令碼」。

**選項:**

進行以下一項操作: 

* 再刪除一次。出現成功訊息。
* 等待大約 10 分鐘，讓 Target Standard/Premium 匯入器執行。匯入器會更新設定檔指令碼清單。

## Some ajax [!DNL Target] calls are not working.

**注意:**[!DNL Target] 具有相同 名稱但不同參數的多個 ajax 呼叫將無法在相同頁面上運作。僅會發出第一次呼叫。

## You activated an activity using the Target API, but the activity shows a status of [!UICONTROL Inactive] in the Target UI.

執行特定動作時 (例如在 UI 外部使用 Target API 來啟動活動)，更新最多可能需要 10 分鐘才會傳播至 UI。