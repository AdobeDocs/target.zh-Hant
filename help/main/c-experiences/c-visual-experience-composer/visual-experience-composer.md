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
source-git-commit: 140a7287246905d47bf02a84348627017a619386
workflow-type: tm+mt
source-wordcount: '889'
ht-degree: 0%
---
# [!UICONTROL 視覺化體驗撰寫器] (VEC)

[!DNL Adobe Target]中的[!UICONTROL 視覺化體驗撰寫器] (VEC)是WYSIWYG編輯器，可直接在網站和行動網頁上建立和測試個人化體驗，無須編輯程式碼。

拖放元素、交換內容及變更頁面配置，以建立[!DNL Target]活動的體驗和選件。 撰寫器也提供用於編輯HTML和JavaScript的選項。

## 瀏覽器需求 {#browser-requirements}

[!DNL Adobe Target]介面支援[!DNL Safari]。 您可以在[!DNL Safari]中建立表單式活動，並使用除VEC和[!UICONTROL 增強體驗撰寫器] (EEC)以外的所有功能。 如果您在[!DNL Safari]中開啟視覺化體驗撰寫器，覆蓋會提示您切換至[!DNL Google Chrome]以編輯體驗。

[!DNL Firefox]之類的瀏覽器可能會封鎖包含混合內容的頁面，例如安全網站內的不安全頁面，使其無法在VEC中顯示。 如果頁面未顯示，請按一下瀏覽器位址列中URL旁的圖示，然後按一下&#x200B;**[!UICONTROL 停用此頁面的保護]**。 此問題不會影響頁面向網站訪客顯示的方式。

## 開啟VEC {#open-the-vec}

若要設定預設在VEC中開啟的頁面，請在[!DNL Target] **[!UICONTROL 管理]** > **[!UICONTROL 視覺化體驗撰寫器]**&#x200B;索引標籤上輸入預設的[!UICONTROL 視覺化體驗撰寫器] URL。

如果您未設定預設URL，VEC會以空白頁面開啟，您可以在其中指定URL。

![醒目提示 VEC](/help/main/c-experiences/c-visual-experience-composer/assets/vec-highlight-refresh.png)

## 編輯體驗 {#edit-experiences}

### 檢視和命名體驗 {#view-and-name-experiences}

使用[!UICONTROL 體驗]邊欄中的索引標籤，檢視您的頁面在不同對象或不同體驗中的顯示方式。 為每個體驗提供描述性名稱，以便於在清單中識別。

例如，在導覽列中測試「首頁」連結的位置時，將其顯示在首位的體驗命名為「首頁連結在前」。

![重新命名體驗邊欄中的體驗](/help/main/c-experiences/c-visual-experience-composer/assets/rename_exp.png)

### 選取和修改元素 {#select-and-modify-elements}

將游標移至頁面上，以使用內容感應方塊反白顯示個別元素。

按一下醒目提示的元素以顯示該元素型別的編輯選項。 例如，選取影像並按一下&#x200B;**[!UICONTROL 變更影像來源]**&#x200B;以取代該影像，或選取按鈕以變更其文字顏色。

![編輯選取專案的選項](/help/main/c-experiences/c-visual-experience-composer/assets/properties-exp.png)

您無法編輯內嵌於頁面中的iframe內容。 若要編輯該內容，請確定iframe檔案已啟用[!DNL Target]，然後直接在VEC中載入iframe URL。

在VEC外部變更頁面結構可能會影響活動使用的位置。 如果這些位置變更，[!DNL Target]可能無法找到您修改的元素，這可能會導致編輯體驗時發生問題。

### 瀏覽和設計 {#browse-and-design}

按一下&#x200B;**[!UICONTROL 瀏覽]**&#x200B;以瀏覽到可從目前頁面存取的頁面，例如出貨頁面或購物車，並在那裡測試變更。

VEC中的![瀏覽模式](/help/main/c-experiences/c-visual-experience-composer/assets/browse_exp.png)

在「瀏覽」模式中，您也可以存取游標停留時顯示的元素，例如彈出式選單和迷你購物車。 當您到達要編輯的頁面或元素時，請按一下[設計] **[!UICONTROL 來編輯體驗。]**

如果暫留狀態依賴JavaScript，請確定未選取&#x200B;**[!UICONTROL 停用JavaScript]**。 必須啟用JavaScript才能編輯相依於它的元素。

如需有關可用編輯選項的詳細資訊，請參閱[視覺化體驗撰寫器選項](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#reference_3BD1BEEAFA584A749ED2D08F14732E81)。

## 管理頁面載入 {#manage-page-loading}

頁面載入時或無法載入後，某些編輯選項仍可使用。 您也可以取消頁面載入以存取這些選項，而不需要等候。

### 在頁面載入時或頁面無法載入後編輯頁面 {#loading}

您可以在VEC中的頁面載入完成前或無法載入後（例如，因為自訂程式碼已無法運作）進行一些變更。

使用可用的編輯選項來執行下列作業：

* 進行簡單的變更，例如新增自訂程式碼或重新命名體驗
* 從無法再存取的頁面複製現有的自訂程式碼
* 對無法在VEC中載入的頁面進行簡單編輯

在頁面載入時或無法載入後，[!UICONTROL 體驗]邊欄、[!UICONTROL 元件]邊欄和[!UICONTROL 設定]選項仍可存取。

### 在VEC內取消載入頁面 {#cancel-loading}

在VEC中取消頁面載入以編輯活動，而不等待頁面完成載入。

當您需要以下工作時，取消頁面載入會很有用：

* 對現有修改進行微幅編輯
* 刪除一或多個現有修改
* 插入或編輯自訂程式碼
* 更正錯誤輸入的頁面URL
* 在VEC中載入頁面之前，啟用或停用JavaScript
* 將範本測試規則新增至[!UICONTROL 頁面傳送]條件
* 透過EEC或僅限iframe模式載入頁面時，覆寫全域[!UICONTROL 增強體驗撰寫器] (EEC)切換按鈕

取消頁面載入後，您可以在活動中的體驗之間切換，而不需要等候頁面載入。 按一下「重新載入&#x200B;****」以再次在VEC中顯示頁面。

>[!IMPORTANT]
>
>如果您在取消頁面載入後編輯自訂程式碼或進行其他修改，請執行品質保證(QA)測試，以驗證您的變更是否如預期般傳送。

若要停止載入頁面，請在載入頁面時按一下&#x200B;**[!UICONTROL 取消載入]**。 除非您重新載入頁面，否則此活動在目前編輯工作階段期間會保持未載入頁面。

按一下&#x200B;**[!UICONTROL 重新載入]**&#x200B;以繼續管理目前活動中的體驗，或新增修改。
