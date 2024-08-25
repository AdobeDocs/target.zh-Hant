---
keywords: 瀏覽器選項;類型;瀏覽器類型;瀏覽器語言;語言;版本;瀏覽器版本
description: 瞭解如何在 [!DNL Adobe Target] 中建立受眾，以鎖定造訪您的頁面時使用特定瀏覽器或特定瀏覽器選項的使用者。
title: 我可以根據瀏覽器型別鎖定訪客嗎？
feature: Audiences
exl-id: 8420bbe3-b58a-4ddb-89bb-0265dab6b5fc
source-git-commit: 784f41a73941877135a5902f2331972ba9d0e880
workflow-type: tm+mt
source-wordcount: '1015'
ht-degree: 33%

---

# [!UICONTROL Browser]

您可以鎖定造訪您的頁面時使用特定瀏覽器或特定瀏覽器選項的使用者。

下列瀏覽器可鎖定作為目標:

* [!UICONTROL Chrome]
* [!UICONTROL Firefox]
* [!UICONTROL Safari]
* [!UICONTROL Internet Explorer]
* [!UICONTROL Microsoft Edge]
* [!UICONTROL Opera]
* [!DNL iPad]
* [!DNL iPhone]

>[!IMPORTANT]
>
>從[!DNL Target] Standard/Premium 24.3.1 （2024年3月4至6日）開始，使用Target UI建立的內建對象（例如`Browser:iPad`和`Browser:iPhone`）已更新，以便使用`profile.mobile.deviceVendor`、`profile.mobile.isMobilePhone`和`profile.mobile.isTablet`針對[!DNL iPad]和[!DNL iPhone]執行適當的鎖定目標。
>
>此更新不需要客戶採取任何動作。 [!DNL Target] UI中的標籤未來將會變更，而且會在進行這些變更時，在[[!DNL Target] 發行說明（最新）](/help/main/r-release-notes/release-notes.md)中宣佈。
>
>如需因應措施，請參閱下列[!UICONTROL Browser]對象屬性（2024年4月30日）](#updates)中的[更新 [!DNL iPad] 及 [!DNL iPhone] 。

鎖定目標瀏覽器有兩種方法:

* **預先建立的對象:**&#x200B;如果您想鎖定使用特定瀏覽器來造訪網站的對象為目標，請使用預先建立的對象。例如，如果您提供[!DNL Chrome]副檔名，則只會針對[!DNL Chrome]位使用者。

   1. 設定活動時，從下拉式清單中選取瀏覽器。

      此選項只會將活動的目標鎖定在使用指定瀏覽器的訪客。

      ![目標Chrome使用者](/help/main/c-target/c-audiences/c-target-rules/assets/target-chrome.png)

* **自訂瀏覽器對象規則：**&#x200B;自訂對象可讓您鎖定多個瀏覽器，或針對特定瀏覽器、瀏覽器版本或瀏覽器語言設定規則或排除專案。 根據瀏覽器屬性來鎖定目標活動時，此功能可提供相當大的彈性。

   1. 在[!DNL Target]介面中，按一下&#x200B;**[!UICONTROL Audiences]** > **[!UICONTROL Create Audience]**。
   1. 為對象命名並新增選擇性說明。
   1. 將&#x200B;**[!UICONTROL Browser]**&#x200B;拖放至對象產生器。

      ![規則>瀏覽器](assets/target_browser.png)

   1. 按一下&#x200B;**[!UICONTROL Select]**，然後選取下列其中一個選項：

      * **類型:** 將特定瀏覽器鎖定作為目標或排除。請參閱[類型](/help/main/c-target/c-audiences/c-target-rules/browser.md#section_6ADC758F23F145B3A310151546D83D56)。
      * **語言：**&#x200B;目標或排除設定為使用特定語言的特定瀏覽器。 請參閱[語言](/help/main/c-target/c-audiences/c-target-rules/browser.md#section_7520D1AA464A45A6843EABE2D2B431A1)。
      * **版本:** 將特定瀏覽器版本鎖定作為目標或排除。請參閱[版本](/help/main/c-target/c-audiences/c-target-rules/browser.md#section_37CC8CE45DA04E8682AE6388321BA6EF)。

   1. （選用）為對象設定其他規則。
   1. 按一下 **[!UICONTROL Done]**。

  下列範例顯示包含[!DNL Microsoft Edge]位版本91或92使用者的對象：

  ![目標Edge 91或92](assets/target_edge.png)

## 瀏覽器選項 {#concept_221D8EEF53CC45AEACEB17CF336A3658}

根據活動加入者的瀏覽器類型、語言或版本來鎖定或排除活動加入者。

### 類型 {#section_6ADC758F23F145B3A310151546D83D56}

將特定瀏覽器鎖定作為目標或排除。

選取&#x200B;**[!UICONTROL Type]**，然後選擇等於或不等於。

* [!UICONTROL Equals]：鎖定選取的瀏覽器。
* [!UICONTROL Does not equal]：排除選取的瀏覽器。

選取一或多個瀏覽器。多個選項是使用「或」連接。

### 語言 {#section_7520D1AA464A45A6843EABE2D2B431A1}

將設為使用特定語言的特定瀏覽器鎖定作為目標或排除。

例如，如果選件只有英文版，您可以會將語言設為英文的瀏覽器鎖定作為目標。或者，如果頁面未啟用雙位元組功能，您可以排除設為東亞語言的瀏覽器。

在語言比位置更重要的情況下，透過包含或排除瀏覽器語言來鎖定目標訪客，將會比根據地理來鎖定目標更準確。例如，如果您提供以英文撰寫的文章，您可以將目標鎖定在說英語的國家/地區，或將設為英文的瀏覽器作為鎖定目標。對於不以英文為母語的國家/地區中說英語的人，鎖定目標瀏覽器可讓他們閱讀這篇文章。

選取&#x200B;**[!UICONTROL Language]**，然後選擇等於或不等於。

* [!UICONTROL Equals]：鎖定選取的瀏覽器語言。
* [!UICONTROL Does not equal]：排除選取的瀏覽器語言。

選取一或多種語言。多個選項是使用「或」連接。

下列瀏覽器語言可鎖定作為目標或排除:

* 英文
* 法語
* 德文
* 日文
* 韓文
* 葡萄牙語
* 俄文
* 西班牙語
* 繁體中文

### 版本 {#section_37CC8CE45DA04E8682AE6388321BA6EF}

將特定瀏覽器版本鎖定作為目標或排除。

例如，如果您的頁面在[!DNL Internet Explorer]版本11或更早版本中無法正確顯示，您可以建立排除這些版本的對象。 在這種情況下，您可以設定瀏覽器型別等於[!DNL Internet Explorer]的規則，並新增版本小於或等於11的第二個規則。

選取&#x200B;**[!UICONTROL Version]**，然後選擇運運算元：

* [!UICONTROL Equals]
* [!UICONTROL Does not equal]
* [!UICONTROL Is greater than]
* 大於或等於
* [!UICONTROL Is less than]
* [!UICONTROL Is less than or equal to]

輸入版本號碼。 在文字欄位中僅能輸入主要版本。指定的版本包含此次發行的任何次要版本。例如，如果您指定版本10，則也會包含版本10.1的訪客。

多個選項是使用「或」連接。

## 訓練影片：建立對象![教學課程徽章](/help/main/assets/tutorial.png)

此影片包括關於使用對象類別的資訊。

* 建立客群
* 定義對象類別

>[!VIDEO](https://video.tv.adobe.com/v/17392)

## [!UICONTROL Browser]對象屬性（2024年4月30日）中[!DNL iPad]和[!DNL iPhone]的更新 {#updates}

[!DNL Adobe Target]可讓您[鎖定數個類別屬性中的任何一個](/help/main/c-target/c-audiences/c-target-rules/target-rules.md)，包括使用特定瀏覽器或瀏覽器選項造訪您頁面的使用者。

從[!DNL Target] Standard/Premium 24.3.1 （2024年3月4至6日）開始，使用Target UI建立的內建對象（例如`Browser:iPad`和`Browser:iPhone`）已更新，以便使用`profile.mobile.deviceVendor`、`profile.mobile.isMobilePhone`和`profile.mobile.isTablet`針對[!DNL iPad]和[!DNL iPhone]執行適當的鎖定目標。

使用[!DNL Target] UI （例如`Browser:iPad`和`Browser:iPhone`）建立的內建對象，會自動移至新的對象定義，而客戶不需要採取任何動作。 不過，您以後應該使用下述設定[](#ui)。

如果您在任何設定檔指令碼中使用`user.browserType`來檢查它是[!DNL iPhone]或[!DNL iPad] （例如，`user.browserType == 'iphone'`或`user.browserType != 'ipad'`），在2024年4月30日之前，這些設定檔指令碼應該變更為[以下](#profile-scripts)的指示，以確保這些對象繼續如預期般運作。

JavaScript對象是使用[!DNL Target]運算式的舊版對象，這些運算式已在[!DNL Target Classic] UI中棄用。 這些對象只能透過API修改。 客戶必須更新這些對象，才能繼續在活動中使用舊版對象。

### 使用[!DNL Target] UI建立的對象 {#ui}

您之後可能會使用下列設定：

* **對於瀏覽器符合[!DNL Apple]**： [!UICONTROL Mobile] > [!UICONTROL Device Vendor] [!UICONTROL matches] [!DNL Apple]

  ![Apple](/help/main/r-release-notes/assets/apple.png)

* **對於符合平板電腦的瀏覽器**： [!UICONTROL Mobile] > [!UICONTROL is Tablet] > [!UICONTROL true]

  ![行動裝置是平板電腦](/help/main/r-release-notes/assets/is-tablet.png)

* **對於符合iPad**&#x200B;的瀏覽器： [!UICONTROL Mobile] > [!UICONTROL Device Marketing Name] [!UICONTROL matches] [!DNL iPad]具有包含[!UICONTROL Mobile] > [!UICONTROL Is Tablet]的And容器為[!DNL true]

  ![iPad](/help/main/r-release-notes/assets/ipad.png)

* **對於符合iPhone**&#x200B;的瀏覽器： [!UICONTROL Mobile] > [!UICONTROL Device Marketing Name] [!UICONTROL matches] [!DNL iPhone]具有包含[!UICONTROL Mobile] > [!UICONTROL Is Mobile Phone]的And容器為[!DNL true]

  ![iPhone](/help/main/r-release-notes/assets/iphone.png)

有許多其他可能的設定可供使用，例如當條件被否定時。 否定條件的範例可能如下所示：

* **若瀏覽器不符合iPhone**： [!UICONTROL Mobile] > [!UICONTROL Device Vendor] [!UICONTROL does not match] [!UICONTROL Apple]若其Or容器為[!UICONTROL Mobile] > [!UICONTROL Is Mobile Phone]，則為[!UICONTROL false]

  ![不是行動電話](/help/main/r-release-notes/assets/mobile-phone-false.png)

* **若瀏覽器不符合iPad**： [!UICONTROL Mobile] > [!UICONTROL Device Vendor] [!UICONTROL does not match] [!UICONTROL Apple]若其Or容器為[!UICONTROL Mobile] > [!UICONTROL Is Tablet]，則為[!UICONTROL false]。

  ![不是平板電腦](/help/main/r-release-notes/assets/tablet-false.png)

### 使用個人資料指令碼建立的對象 {#profile-scripts}

如果您在舊版[!DNL Target Classic]對象或設定檔指令碼中使用`user.browserType`，則變更應包括下列專案：

* **BrowserType是iPhone**：

  取代：

  `user.browserType=="iphone"`

  替換為：

  `profile.mobile.deviceVendor == "Apple" && profile.mobile.isMobilePhone`

* **BrowserType不是iPhone**：

  取代：

  `user.browserType!="iphone"`

  替換為：

  `profile.mobile.deviceVendor != "Apple" || !profile.mobile.isMobilePhone`

* **BrowserType是iPad**：

  取代：

  `user.browserType=="ipad"`

  替換為：

  `profile.mobile.deviceVendor == "Apple" && profile.mobile.isTablet`

* **BrowserType不是iPad**：

  取代：

  `user.browserType!="ipad"`

  替換為：

  `profile.mobile.deviceVendor != "Apple" || !profile.mobile.isTablet`