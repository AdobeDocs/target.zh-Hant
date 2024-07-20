---
keywords: 疑難排解 Target; 預設內容; 測試未上線; 活動未上線; 鎖定目標無法使用; 顯示上一個體驗; 無法建立活動; 建立活動; 頁面結構已變更; 頁面結構已修改; 錯誤訊息; 誤刪設定檔指令碼; ajax 無法使用
description: 如果您的 Adobe [!DNL Target] 活動未出現在網站上，請尋找疑難排解建議。
title: 如何疑難排解活動？
feature: Activities
exl-id: 6aa0486a-9ca3-4545-ae06-9b02e586d777
source-git-commit: f1cbc46323f71c2fa091cd2c9a3e49d34676e7a1
workflow-type: tm+mt
source-wordcount: '846'
ht-degree: 44%

---

# 疑難排解活動

如果您的 [!DNL Adobe Target] 活動未出現在網站上，這些疑難排解建議應可協助您尋找您的解決方案。

>[!NOTE]
>
>除了下列疑難排解資訊，請參閱[疑難排解 Target](/help/main/r-troubleshooting-target/troubleshooting-target.md#reference_A9DB82675D044BD8861F6752A4EE6839) 中提供的連結，取得其他疑難排解主題、常見問答和疑難排解活動與其他 [!DNL Adobe Target] 功能的其他實用資訊。

以下小節包含您可能會遇到的問題，以及建議的解決方案。

## 我使用 [!DNL Target] UI 建立了一個活動，但無法透過 API 更新它。

使用[!DNL Target] UI建立的活動應透過[!DNL Target] UI更新。 透過 API 建立的活動應透過 API 更新。例如，如果您最初使用API建立活動，但稍後透過[!DNL Target] UI編輯活動，則不會更新所有變更。 所有變更都儲存在後端，並可進行其他API呼叫來更新。

最佳實務是嘗試使用與原始建立活動相同的方法 (UI 或 API) 來更新活動。

## 您看到的是預設內容。

請確定您的活動已完成且已啟動。

## 活動未上線。

**驗證：**&#x200B;移至[!UICONTROL Overview]標籤，檢視測試是否標示為非使用中或草稿。

**選項:**

* 啟動測試。
* 使用「預覽連結」來顯示非使用中的測試。

## 您不符合對象鎖定目標條件的資格。

**驗證：**&#x200B;檢閱概覽頁面上的鎖定目標條件。

**選項:**

* 設法符合資格，然後再試一次。
* 使用「預覽連結」以避開鎖定目標條件。

## 頁面不符合頁面鎖定目標條件。

**驗證：**&#x200B;在[!UICONTROL Overview]頁面上，判斷頁面是否落在鎖定目標條件之外。

**選項:**

* 前往[!UICONTROL Visual Experience Composer]，按一下「URL >進階>目前頁面」。

## 出現上一個體驗，而非新的體驗。

**驗證:** 嘗試下列其中一個選項，並試著再次檢視體驗。

**選項:**

* 清除快取和 Cookie，然後再試一次。
* 嘗試不同瀏覽器。
* 使用私人/無痕模式。

## 您最近已加入 [!DNL Target] 但無法建立活動。

**驗證：**&#x200B;按一下[!UICONTROL Create Activity]。 如果無法使用此選項，很可能是您沒有足夠權限來建立活動。

**選項:**

將您新增為[!DNL Target]中的使用者後，您需要擁有[!UICONTROL Approver]角色才能建立活動。

* 請要求您的帳戶管理員將您設為核准者。
* 如果您是管理員，請在[!DNL Target]中從&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Users]**&#x200B;為自己指定[!UICONTROL Approver]角色。

  請參閱[將核准者角色指派給您自己](/help/main/administrating-target/start-target.md#task_15CAA437A71444E2932B333D5E66A3C7)。

## 頁面的結構自從設定活動後已變更。

**驗證：**&#x200B;前往現有活動的[!UICONTROL Visual Experience Composer]。 尋找指出選取器 (或結構) 已變更的警告訊息。

**選項:**

* 重建活動。

如需有關頁面修改如何影響[!DNL Target]顯示能力的詳細資訊，請參閱[頁面修改案例](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB)。

## 頁面的結構在頁面載入期間 (執行階段) 已修改。

**驗證:** 詢問開發人員。

**注意：**&#x200B;為了讓[!DNL Target]能夠識別應該套用活動變更的位置，請避免以相同類別動態插入元素，或是動態修改任何同層級的類別。

**選項:**

* 更新頁面程式碼（使用ID）以唯一識別每個測試的元素。
* 如上所述，停止動態修改類別或同層級。

如需有關頁面修改如何影響[!DNL Target]顯示能力的詳細資訊，請參閱[頁面修改案例](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB)。

## 其他活動正在相同頁面上執行。

**驗證：**&#x200B;使用[!UICONTROL Collisions]索引標籤檢視其他活動是否正在執行。

**注意：** [!UICONTROL Collisions]標籤不適用於範本測試模組。

**選項:**

* 提高此活動的優先順序。
* 降低其他活動的優先順序。
* 停用其他活動。

## 刪除設定檔指令碼時出現錯誤訊息。

**驗證：**&#x200B;從[!DNL Target]刪除設定檔指令碼會顯示錯誤訊息「無法刪除設定檔指令碼」。

**選項:**

進行以下一項操作：

* 再次刪除設定檔指令碼。 出現成功訊息。
* 等候約10分鐘，讓[!DNL Target]匯入工具執行。 匯入器會更新設定檔指令碼清單。

## 有些 ajax [!DNL Target] 呼叫無法運作。

**注意：**&#x200B;具有相同名稱但不同引數的多個ajax [!DNL Target]呼叫無法在同一頁面上運作。 只進行第一次呼叫。

## 您已使用[!DNL Target] API啟動活動，但活動在[!DNL Target] UI中顯示[!UICONTROL Inactive]狀態。

執行特定動作時（例如在UI外部使用[!DNL Target] API來啟動活動），更新最多可能需要10分鐘才會傳播至UI。

## 活動轉換後，訪客沒有任何體驗。

在極少數的情況下，如果在與活動資格相同的請求中傳送了活動符合體驗資格的轉換量度，則訪客在傳送請求後可能沒有任何體驗。 在此情況下，訪客會看到預設內容，而透過權杖擷取的體驗ID將是–1。 [!DNL Adobe]不建議在同一[!DNL Target]要求中傳送活動資格和轉換。

如果您想要在相同要求中傳送這兩個量度，您可以使用[!UICONTROL Advanced Settings]來指定在轉換後訪客會維持相同的體驗。
