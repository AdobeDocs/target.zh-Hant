---
keywords: 視覺化體驗撰寫器； VEC； WYSIWYG
description: 瞭解在Adobe Target中使用視覺化體驗撰寫器(VEC)的基本知識。 VEC是WYSIWYG編輯器，可讓您輕鬆建立個人化體驗。
title: 如何使用視覺化體驗撰寫器(VEC)？
feature: Visual Experience Composer (VEC)
exl-id: 51650f2a-1f24-40c7-8692-77f55656b4f6
TQID: 'https://experienceleague.adobe.com/X4nfYuOtD3TVusnVIIEZhXwUdCZ-dMvbZeJlrkmI9Hs'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '944'
ht-degree: 0%
---
# 開始使用[!UICONTROL 視覺化體驗撰寫器] {#vec-overview}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解如何開啟[!UICONTROL 視覺化體驗撰寫器] (VEC)、編輯體驗及管理頁面載入。

>[!ENDSHADEBOX]

[!DNL Adobe Target]中的[!UICONTROL 視覺化體驗撰寫器] (VEC)是WYSIWYG編輯器，可直接在網站和行動網頁上建立和測試個人化體驗，無需編輯程式碼。

[!DNL Target]活動的體驗和選件是透過拖放元素、交換內容及變更頁面版面配置所建立。 撰寫器也提供用於編輯HTML和JavaScript的選項。

## 瀏覽器需求 {#browser-requirements}

[!DNL Adobe Target]介面支援[!DNL Safari]。 可在[!DNL Safari]中建立表單式活動，其所有功能均可使用，但VEC和[!UICONTROL 增強體驗撰寫器] (EEC)除外。 如果在[!DNL Safari]中開啟VEC，覆蓋會提示使用者切換至[!DNL Google Chrome]以編輯體驗。

[!DNL Firefox]之類的瀏覽器可能會封鎖包含混合內容的頁面，例如安全網站內的不安全頁面，使其無法在VEC中顯示。 如果頁面未顯示，請按一下瀏覽器位址列中URL旁的圖示，然後按一下&#x200B;**[!UICONTROL 停用此頁面的保護]**。 此問題不會影響頁面向網站訪客顯示的方式。

## 開啟VEC {#open-the-vec}

若要設定預設在VEC中開啟的頁面，請在[!DNL Target] **[!UICONTROL 管理]** > **[!UICONTROL 視覺化體驗撰寫器]**&#x200B;索引標籤上輸入預設的[!UICONTROL 視覺化體驗撰寫器] URL。 若未設定預設URL，VEC會開啟一個空白頁面，您可在此指定URL。

![反白顯示視覺化體驗撰寫器標籤的管理頁面，顯示預設URL、增強體驗撰寫器和載入混合內容設定](/help/main/c-experiences/c-visual-experience-composer/assets/vec-highlight-refresh.png)

## 編輯體驗 {#edit-experiences}

### 檢視和命名體驗 {#view-and-name-experiences}

**[!UICONTROL 體驗]**&#x200B;邊欄中的索引標籤會顯示頁面向不同對象或不同體驗的顯示方式。 每個體驗的描述性名稱可讓您更輕鬆地在清單中識別。 例如，在導覽列中測試首頁連結的位置時，其最先出現的體驗可命名為「首頁連結優先」。

![先以名稱「首頁」連結重新命名體驗對話方塊，從體驗B](/help/main/c-experiences/c-visual-experience-composer/assets/rename_exp.png)的重新命名圖示開啟

### Select和修改元素 {#select-and-modify-elements}

在頁面上移動游標會醒目顯示具有內容感應方塊的個別元素。 按一下醒目提示的元素會顯示該元素型別的編輯選項。 例如，選取影像並按一下&#x200B;**[!UICONTROL 變更影像選件]**&#x200B;會取代該影像，而選取按鈕可變更其文字顏色。

![編輯選取影像上方顯示的選項](/help/main/c-experiences/c-visual-experience-composer/assets/properties-exp.png)

無法編輯內嵌在頁面中的iframe內容。 若要編輯該內容，請確定iframe檔案已啟用[!DNL Target]，然後直接在VEC中載入iframe URL。

在VEC外部變更頁面結構可能會影響活動使用的位置。 如果這些位置變更，[!DNL Target]可能無法找到已修改的元素，這可能會導致編輯體驗時發生問題。

### 瀏覽和設計 {#browse-and-design}

按一下&#x200B;**[!UICONTROL 瀏覽]**&#x200B;以瀏覽到可從目前頁面存取的頁面，例如出貨頁面或購物車，並在那裡測試變更。

![VEC中的瀏覽模式，包含URL欄位以及後退和前進箭頭](/help/main/c-experiences/c-visual-experience-composer/assets/browse_exp.png)

在「瀏覽」模式中，也可以存取懸停時顯示的元素，例如彈出式選單和迷你購物車。 到達要編輯的頁面或元素時，按一下&#x200B;**[!UICONTROL 設計]**&#x200B;以編輯體驗。

如果暫留狀態依賴JavaScript，請確定未選取&#x200B;**[!UICONTROL 停用JavaScript]**。 必須啟用JavaScript才能編輯相依於它的元素。

如需有關可用編輯選項的詳細資訊，請參閱[視覺化體驗撰寫器選項](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)。

## 管理頁面載入 {#manage-page-loading}

頁面載入時或無法載入後，某些編輯選項仍可使用。 也可以取消頁面載入以存取這些選項，而不需要等候。

### 在頁面載入時或頁面無法載入後編輯頁面 {#loading}

例如，在頁面完成VEC中的載入之前，或是在頁面無法載入之後（例如因為自訂程式碼不再有作用），可以進行某些變更。

可用的編輯選項允許下列專案：

* 進行簡單的變更，例如新增自訂程式碼或重新命名體驗
* 從無法再存取的頁面複製現有的自訂程式碼
* 對無法在VEC中載入的頁面進行簡單編輯

在頁面載入時或無法載入後，**[!UICONTROL 體驗]**&#x200B;邊欄、**[!UICONTROL 元件]**&#x200B;邊欄和&#x200B;**[!UICONTROL 設定]**&#x200B;選項仍可存取。

### 在VEC內取消載入頁面 {#cancel-loading}

在VEC中取消頁面載入可讓您編輯活動，而不需要等候頁面載入完成。 這可用於：

* 對現有修改進行微幅編輯
* 刪除一或多個現有修改
* 插入或編輯自訂程式碼
* 更正錯誤輸入的頁面URL
* 在VEC中載入頁面之前，啟用或停用JavaScript
* 將範本測試規則新增至&#x200B;**[!UICONTROL 頁面傳送]**&#x200B;條件
* 透過EEC或僅限iframe模式載入頁面時，覆寫全域[!UICONTROL 增強體驗撰寫器] (EEC)切換按鈕

取消頁面載入後，就可以在活動中的體驗之間切換，而不需要等候頁面載入。 按一下「重新載入&#x200B;****」以再次在VEC中顯示頁面。

>[!IMPORTANT]
>
>如果自訂程式碼已編輯或在頁面載入取消後進行了其他修改，請執行品質保證(QA)測試，以驗證變更是否按預期傳送。

若要停止載入頁面，請在載入頁面時按一下&#x200B;**[!UICONTROL 取消載入]**。 在目前編輯工作階段期間，除非重新載入頁面，否則此活動的頁面會維持未載入狀態。

按一下&#x200B;**[!UICONTROL 重新載入]**&#x200B;以繼續管理目前活動中的體驗，或新增修改。
