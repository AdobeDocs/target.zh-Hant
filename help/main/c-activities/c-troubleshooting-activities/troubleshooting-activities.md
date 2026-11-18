---
keywords: 疑難排解Target；預設內容；測試未上線；活動未上線；鎖定目標無法使用；顯示上一個體驗；無法建立活動；建立活動；頁面結構已變更；頁面結構已修改；錯誤訊息；錯誤刪除設定檔指令碼； ajax無法使用
description: 如果您的Adobe [!DNL Target]活動未出現在網站上，請尋找疑難排解建議。
title: 如何疑難排解活動？
feature: Activities
exl-id: 6aa0486a-9ca3-4545-ae06-9b02e586d777
TQID: 'https://experienceleague.adobe.com/L-011t7q6c3aICs0ZrM01m9pZByH86FKGiLG1A7Rl2s'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: 6efa6b7a-8062-5c41-aef4-b4853cc306ae
    internal-label: Activities
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 9621044454d3e1b47c06cac2ad5d08cba8e482c0
workflow-type: tm+mt
source-wordcount: '929'
ht-degree: 7%
---
# 開始使用疑難排解活動 {#troubleshooting-activities}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;尋找[!DNL Adobe Target]活動未出現在您的網站上或行為未如預期時，常見問題的解決方案。

>[!ENDSHADEBOX]

有幾個原因可能會導致[!DNL Adobe Target]活動無法在您的網站上出現。 使用以下問題和建議的解決方案來找出原因並套用修正。

>[!NOTE]
>
>除了下列疑難排解資訊，請參閱[疑難排解Target](/help/main/r-troubleshooting-target/troubleshooting-target.md)，以取得[!DNL Adobe Target]中其他疑難排解主題、常見問答和疑難排解活動與其他功能的其他實用資訊的連結。

## 活動未按預期顯示 {#not-displayed}

+++ 您會看到預設內容

請確定您的活動已完成且已啟動。

+++

</br>

+++ 活動未上線

**驗證：**&#x200B;在&#x200B;**[!UICONTROL 總覽]**&#x200B;索引標籤上，檢查活動是否標示為非使用中或草稿。

**選項:**

* 啟動活動。
* 使用預覽連結來顯示非使用中活動。

+++

</br>

+++ 您不符合對象鎖定目標條件的資格

**驗證：**&#x200B;檢閱&#x200B;**[!UICONTROL 總覽]**&#x200B;頁面上的鎖定目標條件。

**選項:**

* 符合對象資格，然後重試。
* 使用預覽連結來略過目標定位條件。

+++

</br>

+++ 頁面不符合頁面鎖定目標條件

**驗證：**&#x200B;在&#x200B;**[!UICONTROL 總覽]**&#x200B;頁面上，判斷頁面是否落在鎖定目標條件之外。

**選項:**

* 前往&#x200B;**[!UICONTROL 視覺化體驗撰寫器]**，然後按一下「URL >進階>目前頁面」。

+++

</br>

+++ 系統會顯示先前的體驗，而非新體驗

**驗證：**&#x200B;請嘗試下列其中一個選項，然後嘗試再次檢視體驗。

**選項:**

* 清除快取和Cookie，然後重試。
* 嘗試不同瀏覽器。
* 使用私人或無痕模式。

+++

</br>

+++ 設定活動後，頁面結構已變更

**驗證：**&#x200B;前往現有活動的&#x200B;**[!UICONTROL 視覺化體驗撰寫器]**，並尋找指出選取器（或結構）已變更的警告訊息。

**選項:**

* 重建活動。

如需有關頁面修改如何影響[!DNL Target]顯示內容能力的詳細資訊，請參閱[頁面修改案例](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md)。

+++

</br>

+++ 頁面結構會在頁面載入期間（執行階段）修改

**驗證：**&#x200B;請詢問您的開發人員。

**注意：**&#x200B;若要讓[!DNL Target]識別必須套用活動變更的位置，請避免以相同類別動態插入元素，或動態修改任何同層級的類別。

**選項:**

* 更新頁面程式碼，以使用ID唯一識別每個測試的元素。
* 停止動態修改類別或同層級，如上所述。

如需有關頁面修改如何影響[!DNL Target]顯示內容能力的詳細資訊，請參閱[頁面修改案例](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md)。

+++

</br>

+++ 其他活動正在相同頁面上執行

**驗證：**&#x200B;使用&#x200B;**[!UICONTROL 衝突]**&#x200B;索引標籤檢視其他活動是否正在執行。

**注意：** **[!UICONTROL 衝突]**&#x200B;索引標籤不適用於範本測試模組。

**選項:**

* 提高此活動的優先順序。
* 減少其他活動的優先順序。
* 停用其他活動。

+++

## 使用者、API和UI {#users-api-ui}

+++ 我使用[!DNL Target] UI建立了一個活動，但無法透過API更新它

使用[!DNL Target] UI建立的活動應透過[!DNL Target] UI更新。 透過 API 建立的活動應透過 API 更新。 例如，如果您使用API建立活動，但稍後透過[!DNL Target] UI編輯活動，則不會更新所有變更。 所有變更都儲存在後端，並可進行其他API呼叫來更新。

最佳實務是使用建立活動所用的相同方法（UI或API）來更新活動。

+++

</br>

+++ 您最近已新增至[!DNL Target]，但無法建立活動

**驗證：**&#x200B;按一下&#x200B;**[!UICONTROL 建立活動]**。 如果無法使用此選項，很可能是您沒有足夠權限來建立活動。

**選項:**

將您新增為[!DNL Target]中的使用者後，您需要&#x200B;**[!UICONTROL 核准者]**&#x200B;角色才能建立活動。

* 請要求您的帳戶管理員將您設為核准者。
* 如果您是管理員，請在[!DNL Target]中授與您自己&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 使用者]**&#x200B;的&#x200B;**[!UICONTROL 核准者]**&#x200B;角色。 請參閱[將核准者角色指派給您自己](/help/main/administrating-target/start-target.md#task_15CAA437A71444E2932B333D5E66A3C7)。

+++

</br>

+++ 您已使用[!DNL Target] API啟動活動，但活動在[!DNL Target] UI中顯示[!UICONTROL 非使用中]狀態

執行特定動作時（例如在UI外部使用[!DNL Target] API來啟動活動），更新最多可能需要10分鐘才會傳播至UI。

+++

</br>

+++ 當您刪除設定檔指令碼時，會出現錯誤訊息

**驗證：**&#x200B;從[!DNL Target]刪除設定檔指令碼會顯示錯誤訊息「無法刪除設定檔指令碼」。

**選項:**

進行以下一項操作：

* 再次刪除設定檔指令碼。 出現成功訊息。
* 等候約10分鐘，讓[!DNL Target]匯入工具執行。 匯入器會更新設定檔指令碼清單。

+++

## 呼叫和轉換 {#calls-and-conversion}

+++ 有些ajax [!DNL Target]呼叫無法運作

**注意：**&#x200B;具有相同名稱但不同引數的多個ajax [!DNL Target]呼叫無法在同一頁面上運作。 只進行第一次呼叫。

+++

</br>

+++ 活動轉換後，訪客沒有任何體驗

在極少數的情況下，如果符合體驗訪客資格的活動的轉換量度是在與活動資格相同的請求中傳送，則訪客在傳送請求後可能沒有任何體驗。 在此情況下，訪客會看到預設內容，而透過權杖擷取的體驗ID為–1。 [!DNL Adobe]不建議在同一[!DNL Target]要求中傳送活動資格和轉換。

如果您想要在相同要求中傳送這兩個量度，您可以使用&#x200B;**[!UICONTROL 進階設定]**&#x200B;來指定訪客在轉換後仍維持相同的體驗。

+++
