---
keywords: 瀏覽器選項;類型;瀏覽器類型;瀏覽器語言;語言;版本;瀏覽器版本
description: 瞭解如何在中建立對象 [!DNL Adobe Target] 來鎖定造訪您的頁面時使用特定瀏覽器或特定瀏覽器選項的使用者。
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
>從 [!DNL Target] Standard/Premium 24.3.1 （2024年3月4日至6日）內建受眾，使用Target UI建立，例如 `Browser:iPad` 和 `Browser:iPhone` 已更新，針對下列專案執行適當的目標定位： [!DNL iPad] 和 [!DNL iPhone] 使用 `profile.mobile.deviceVendor`， `profile.mobile.isMobilePhone`、和 `profile.mobile.isTablet`.
>
>此更新不需要客戶採取任何動作。 中的標籤 [!DNL Target] UI未來將變更，並將在以下位置公告： [[!DNL Target] 發行說明（最新）](/help/main/r-release-notes/release-notes.md) 進行這些變更時。
>
>如需因應措施的設定，請參閱 [更新 [!DNL iPad] 和 [!DNL iPhone] 在 [!UICONTROL Browser] 對象屬性（2024年4月30日）](#updates) 底下。

鎖定目標瀏覽器有兩種方法:

* **預先建立的對象:**&#x200B;如果您想鎖定使用特定瀏覽器來造訪網站的對象為目標，請使用預先建立的對象。例如，如果您提供 [!DNL Chrome] 擴充功能，您只能 [!DNL Chrome] 使用者。

   1. 設定活動時，從下拉式清單中選取瀏覽器。

      此選項只會將活動的目標鎖定在使用指定瀏覽器的訪客。

      ![Target Chrome使用者](/help/main/c-target/c-audiences/c-target-rules/assets/target-chrome.png)

* **自訂瀏覽器對象規則：** 自訂對象可讓您鎖定多個瀏覽器，或針對特定瀏覽器、瀏覽器版本或瀏覽器語言設定規則或排除專案。 根據瀏覽器屬性來鎖定目標活動時，此功能可提供相當大的彈性。

   1. 在 [!DNL Target] 介面，按一下 **[!UICONTROL Audiences]** > **[!UICONTROL Create Audience]**.
   1. 為對象命名並新增選擇性說明。
   1. 拖放 **[!UICONTROL Browser]** 放入對象產生器。

      ![規則>瀏覽器](assets/target_browser.png)

   1. 按一下 **[!UICONTROL Select]**，然後選取下列其中一個選項：

      * **類型:** 將特定瀏覽器鎖定作為目標或排除。請參閱[類型](/help/main/c-target/c-audiences/c-target-rules/browser.md#section_6ADC758F23F145B3A310151546D83D56)。
      * **語言：** 將設為使用特定語言的特定瀏覽器鎖定作為目標或排除。 請參閱[語言](/help/main/c-target/c-audiences/c-target-rules/browser.md#section_7520D1AA464A45A6843EABE2D2B431A1)。
      * **版本:** 將特定瀏覽器版本鎖定作為目標或排除。請參閱[版本](/help/main/c-target/c-audiences/c-target-rules/browser.md#section_37CC8CE45DA04E8682AE6388321BA6EF)。

   1. （選用）為對象設定其他規則。
   1. 按一下 **[!UICONTROL Done]**。

  以下範例顯示包含下列專案的對象： [!DNL Microsoft Edge] 版本91或92的使用者：

  ![Target Edge 91或92](assets/target_edge.png)

## 瀏覽器選項 {#concept_221D8EEF53CC45AEACEB17CF336A3658}

根據活動加入者的瀏覽器類型、語言或版本來鎖定或排除活動加入者。

### 類型 {#section_6ADC758F23F145B3A310151546D83D56}

將特定瀏覽器鎖定作為目標或排除。

選取 **[!UICONTROL Type]**，然後選擇等於或不等於。

* [!UICONTROL Equals]：鎖定選取的瀏覽器。
* [!UICONTROL Does not equal]：排除選取的瀏覽器。

選取一或多個瀏覽器。多個選項是使用「或」連接。

### 語言 {#section_7520D1AA464A45A6843EABE2D2B431A1}

將設為使用特定語言的特定瀏覽器鎖定作為目標或排除。

例如，如果選件只有英文版，您可以會將語言設為英文的瀏覽器鎖定作為目標。或者，如果頁面未啟用雙位元組功能，您可以排除設為東亞語言的瀏覽器。

在語言比位置更重要的情況下，透過包含或排除瀏覽器語言來鎖定目標訪客，將會比根據地理來鎖定目標更準確。例如，如果您提供以英文撰寫的文章，您可以將目標鎖定在說英語的國家/地區，或將設為英文的瀏覽器作為鎖定目標。對於不以英文為母語的國家/地區中說英語的人，鎖定目標瀏覽器可讓他們閱讀這篇文章。

選取 **[!UICONTROL Language]**，然後選擇等於或不等於。

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

例如，若您的頁面在中未正確顯示 [!DNL Internet Explorer] 11版或更舊版本，您可以建立排除這些版本的對象。 在這種情況下，您可以設定瀏覽器型別等於的規則 [!DNL Internet Explorer] 並新增版本小於或等於11的第二個規則。

選取 **[!UICONTROL Version]**，然後選擇運運算元：

* [!UICONTROL Equals]
* [!UICONTROL Does not equal]
* [!UICONTROL Is greater than]
* 大於或等於
* [!UICONTROL Is less than]
* [!UICONTROL Is less than or equal to]

輸入版本號碼。 在文字欄位中僅能輸入主要版本。指定的版本包含此次發行的任何次要版本。例如，如果您指定版本10，則也會包含版本10.1的訪客。

多個選項是使用「或」連接。

## 訓練影片：建立對象 ![教學課程徽章](/help/main/assets/tutorial.png)

此影片包括關於使用對象類別的資訊。

* 建立對象
* 定義對象類別

>[!VIDEO](https://video.tv.adobe.com/v/17392)

## 更新 [!DNL iPad] 和 [!DNL iPhone] 在 [!UICONTROL Browser] 對象屬性（2024年4月30日） {#updates}

[!DNL Adobe Target] 可讓您 [鎖定任一類別屬性](/help/main/c-target/c-audiences/c-target-rules/target-rules.md)，包括造訪您的頁面時使用特定瀏覽器或瀏覽器選項的使用者。

從 [!DNL Target] Standard/Premium 24.3.1 （2024年3月4日至6日）內建受眾，使用Target UI建立，例如 `Browser:iPad` 和 `Browser:iPhone` 已更新，針對下列專案執行適當的目標定位： [!DNL iPad] 和 [!DNL iPhone] 使用 `profile.mobile.deviceVendor`， `profile.mobile.isMobilePhone` 和 `profile.mobile.isTablet`.

使用建立的內建對象 [!DNL Target] UI，例如 `Browser:iPad` 和 `Browser:iPhone`，會自動移至新的對象定義，客戶不需要採取任何動作。 不過日後，您應使用設定 [如下所述](#ui).

如果您使用 `user.browserType` 在任何設定檔指令碼中檢查它是否為 [!DNL iPhone] 或 [!DNL iPad] (例如， `user.browserType == 'iphone'` 或 `user.browserType != 'ipad'`)，這些設定檔指令碼應變更為 [指示如下](#profile-scripts) 2024年4月30日之前，確保這些對象能繼續如預期般運作。

JavaScript受眾是舊版受眾，使用 [!DNL Target] 已被取代的運算式 [!DNL Target Classic] UI。 這些對象只能透過API修改。 客戶必須更新這些對象，才能繼續在活動中使用舊版對象。

### 使用建立的對象 [!DNL Target] UI {#ui}

您之後可能會使用下列設定：

* **用於瀏覽器比對[!DNL Apple]**： [!UICONTROL Mobile] > [!UICONTROL Device Vendor] [!UICONTROL matches] [!DNL Apple]

  ![Apple](/help/main/r-release-notes/assets/apple.png)

* **適用於瀏覽器相符平板電腦**： [!UICONTROL Mobile] > [!UICONTROL is Tablet] > [!UICONTROL true]

  ![行動裝置是平板電腦](/help/main/r-release-notes/assets/is-tablet.png)

* **瀏覽器比對結果為iPad**： [!UICONTROL Mobile] > [!UICONTROL Device Marketing Name] [!UICONTROL matches] [!DNL iPad] 具有And容器，具有 [!UICONTROL Mobile] > [!UICONTROL Is Tablet] 是 [!DNL true]

  ![iPad](/help/main/r-release-notes/assets/ipad.png)

* **瀏覽器比對結果為iPhone**： [!UICONTROL Mobile] > [!UICONTROL Device Marketing Name] [!UICONTROL matches] [!DNL iPhone] 具有And容器，具有 [!UICONTROL Mobile] > [!UICONTROL Is Mobile Phone] 是 [!DNL true]

  ![iPhone](/help/main/r-release-notes/assets/iphone.png)

有許多其他可能的設定可供使用，例如當條件被否定時。 否定條件的範例可能如下所示：

* **針對瀏覽器不符合iPhone**： [!UICONTROL Mobile] > [!UICONTROL Device Vendor] [!UICONTROL does not match] [!UICONTROL Apple] 具有Or容器，具有 [!UICONTROL Mobile] > [!UICONTROL Is Mobile Phone] 是 [!UICONTROL false]

  ![非行動電話](/help/main/r-release-notes/assets/mobile-phone-false.png)

* **針對瀏覽器不符合iPad**： [!UICONTROL Mobile] > [!UICONTROL Device Vendor] [!UICONTROL does not match] [!UICONTROL Apple] 具有Or容器，具有 [!UICONTROL Mobile] > [!UICONTROL Is Tablet] 是 [!UICONTROL false].

  ![不是平板電腦](/help/main/r-release-notes/assets/tablet-false.png)

### 使用個人資料指令碼建立的對象 {#profile-scripts}

如果您使用 `user.browserType` 在舊版 [!DNL Target Classic] 對象或在個人資料指令碼中，變更應包括下列內容：

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