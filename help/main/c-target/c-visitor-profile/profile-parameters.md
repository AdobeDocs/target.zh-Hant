---
keywords: 配置檔案指令碼；配置檔案指令碼屬性；配置檔案指令碼最佳實踐；調試；指令碼；配置檔案指令碼；屬性；參數
description: 瞭解訪問者配置檔案中儲存的訪問者特定屬性，以提供有關可在您的Adobe中使用的資訊 [!DNL Target] 活動。
title: 什麼是配置檔案屬性？
feature: Audiences
exl-id: 6c689629-bbd3-461e-9a68-5b16d4eb4250
source-git-commit: 66c37704ba4d2fd530cf964987846bc8cb1da809
workflow-type: tm+mt
source-wordcount: '2423'
ht-degree: 48%

---

# 設定檔屬性

中的配置檔案屬性 [!DNL Adobe Target] 是特定於訪問者的參數。 這些屬性儲存於訪客的描述檔中，以提供可用於活動的訪客資訊。

用戶簡檔包含網頁訪問者的人口統計和行為資訊。 此資訊可能包括年齡、性別、購買的產品、上次訪問時間等， [!DNL Target] 用於個性化它為訪問者提供的內容。

當訪問者瀏覽您的網站或訪問者返回另一個會話時，配置檔案中保存的配置檔案屬性可用於目標內容或記錄段過濾資訊。

要設定配置檔案屬性，請執行以下操作：

1. 按一下 **[!UICONTROL 觀眾]** > **[!UICONTROL 配置檔案指令碼。]**

   ![設定檔指令碼標籤](/help/main/c-target/c-visitor-profile/assets/create-script.png)

1. 按一下 **[!UICONTROL 建立指令碼]**。

   ![建立設定檔指令碼對話方塊](/help/main/c-target/c-visitor-profile/assets/profile-script.png)

   可用的設定檔屬性類型如下:

   | 參數類型 | 說明 |
   |--- |--- |
   | mbox | 建立 mbox 時透過頁面程式碼直接傳遞。請參閱[傳遞參數至全域 mbox](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/pass-parameters-to-global-mbox.md)。<br>****&#x200B;注意:  具有每個 mbox 呼叫 50 個獨特設定檔屬性的限制。[!DNL Target]如果必須將50個以上的配置檔案屬性傳遞給 [!DNL Target]，使用Profile Update API方法傳遞它們。 有關詳細資訊，請參見 [中的配置檔案更新 [!DNL Adobe Target] API文檔](https://developers.adobetarget.com/api/#updating-profiles)。 |
   | 設定檔 | 直接以 JavaScript 程式碼片段定義。這些片段可以儲存運行總計，如消費者所花的總資金，並在每個框請求上執行。 請參閱下面的配置檔案指令碼屬性。 |

## 設定檔指令碼屬性 {#concept_8C07AEAB0A144FECA8B4FEB091AED4D2}

以相關聯的 JavaScript 程式碼片段定義設定檔指令碼屬性。

您可以使用設定檔指令碼來跨多次造訪擷取訪客屬性。配置檔案指令碼是在 [!DNL Target] 使用伺服器端JavaScript的形式。 例如，您可以使用配置檔案指令碼來捕獲訪問您站點的訪問頻率以及上次訪問該訪問者的時間。

設定檔指令碼與設定檔參數不同。配置檔案參數使用的框代碼實現捕獲訪問者的資訊 [!DNL Target]。

## 建立設定檔指令碼 {#section_CB02F8B97CAF407DA84F7591A7504810}

在 [!UICONTROL  介面的]「對象」[!DNL Target]標籤下可以使用設定檔指令碼。

要添加配置檔案指令碼，請按一下 **[!UICONTROL 配置檔案指令碼]** 頁籤 **[!UICONTROL 建立指令碼]**，然後編寫指令碼。

或

要複製現有配置檔案指令碼，請從 [!UICONTROL 配置檔案指令碼] 清單，按一下所需指令碼的省略號表徵圖，然後按一下 **[!UICONTROL 重複]**。

然後您可以編輯對象以建立類似的對象。

設定檔指令碼會針對每個位置請求，執行設定檔屬性「捕捉器」。當收到位置請求時， [!DNL Target] 確定應運行哪些活動並顯示適合該活動和該體驗的內容。 [!DNL Target] 還跟蹤活動的成功並運行任何相關配置檔案指令碼。 通過此過程，您可以跟蹤有關訪問的資訊，如訪問者的位置、時間、訪問者到站點的次數（如果他們以前購買過）等。 這些資訊會接著加到該訪客的描述檔中，以便您更有效追蹤訪客在您網站上的活動。

設定檔指令碼屬性會將 `user.` 標籤插入在屬性名稱前。例如:

```
if (mbox.name == 'Track_Interest') { 
    if (profile.get('model') == "A5" &&; profile.get('subcat') == "KS6") { 
        return (user.get('A5KS6') || 0) + 1; 
    } 
}
```

請牢記以下資訊：

* 請參閱代碼中的配置檔案指令碼屬性（包括自身） `user.get('parameterName')`。
* 保存可在下次運行指令碼時（在下一個框請求上）訪問的變數 `user.setLocal('variable_name', 'value')`。 參考包含 `user.getLocal('variable_name')` &#39;) 的變數。此流程對於您要引用上次請求的日期和時間的情況非常有用。

   這些值與配置檔案指令碼一樣保持不變，但您只能在設定的指令碼中訪問它們。

* 參數和值區分大小寫。 匹配在活動或test期間接收的參數和值的大小寫。
* 如需更多 JavaScript 語法，請參閱以下「指令碼設定檔參數的 JavaScript 參考資料」一節。
* 禁用指令碼後，參數將保留在配置檔案中。 其配置檔案已包含在活動受眾中使用的參數的用戶在該活動中符合條件。
* 配置檔案指令碼在活動中使用時無法刪除。
* 建議不要建立使用另一個配置檔案指令碼中一個配置檔案指令碼的結果的從屬配置檔案指令碼。 配置檔案指令碼的執行順序未得到保證。

## 檢視設定檔指令碼資訊卡 {#section_18EA3B919A8E49BBB09AA9215E1E3F17}

您可以檢視設定檔指令碼資訊快顯卡，這類似選件資訊卡片。您可以透過設定檔指令碼資訊卡，檢視參考特定設定檔指令碼的活動，及其他實用中繼資料。

例如，通過按一下 [!UICONTROL 資訊] 表徵圖([!UICONTROL 觀眾] > [!UICONTROL 配置檔案指令碼])。

的 [!UICONTROL 指令碼資訊] 頁籤包含以下資訊：名稱、說明和指令碼代碼。

![設定檔指令碼資訊卡](assets/profile_script_info_card.png)

按一下 **[!UICONTROL 查看完整詳細資訊]** 查看引用所選配置檔案指令碼的受眾和活動。

![設定檔指令碼資訊卡 > 指令碼使用方式標籤](assets/profile_script_info_card_usage_tab.png)

>[!NOTE]
>
>的 [!UICONTROL 指令碼用法] 頁籤不顯示在以下情況下引用所選配置檔案指令碼的活動：
>
> * 活動位於 [!UICONTROL 草稿] 狀態。
> * 活動中使用的內容或選件使用指令碼變數 (活動中的內嵌選件或「選件」資料庫中的選件)。


## Target 在某些情況下會停用設定檔指令碼 {#section_C0FCB702E60D4576AD1174D39FBBE1A7}

[!DNL Target] 在某些情況下自動禁用配置檔案指令碼，例如，執行指令碼的時間太長或指令太多。

設定檔指令碼停用時，Target UI 中的設定檔指令碼旁邊會出現黃色警示圖示，如下所示:

![](assets/profile_script_invalid.png)

暫留時，會出現有關錯誤的詳細資料，如下所示:

![](assets/profile_script_hover.png)

系統停用設定檔指令碼的常見原因包括:

* 參照了未定義的變數。
* 參照了無效的值。此錯誤通常是由於引用URL值和其他用戶輸入的資料而沒有正確驗證而導致的。
* 使用了太多 JavaScript 指令。[!DNL Target] 每個指令碼的JavaScript指令數限制為2,000個，但無法通過手動讀取JavaScript來計算此限制。 例如，Rhino 將所有函數呼叫和「新的」呼叫視為 100 個指示。對任何函式的任何調用都會佔用100條指令。 此外，任何輸入資料的大小，例如 URL 值，皆可能影響指示計數。
* 請注意下節[最佳做法](/help/main/c-target/c-visitor-profile/profile-parameters.md#section_64AFE5D2B0C8408A912FC2A832B3AAE0)中醒目提示的項目。

## 最佳實務 {#best}

下列準則主要是為了協助您撰寫儘可能不會出錯或失敗的簡化描述檔指令檔，透過撰寫適當失效的程式碼處理指令碼，而無須強迫系統或指令碼暫停。這些準則是最佳實務的結果，經證明最有執行效率。您可以套用這些準則並搭配由 Rhino 開發社群所擬的原則與建議。

* 將當前指令碼值設定為用戶指令碼中的本地變數，將故障轉移設定為空字串。
* 藉由確保本地變數不是空白字串來驗證此變數。
* 使用基於字串的操作函式與規則運算式。
* 使用限制迴圈與開放端或 while 迴圈。
* 請勿超過 1,300 個字元或 50 個迴圈反覆。
* 請勿超過 2,000 個 JavaScript 指令。[!DNL Target] 每個指令碼的JavaScript指令數限制為2,000個，但無法通過手動讀取JavaScript來計算此限制。 例如，Rhino 將所有函數呼叫和「新的」呼叫視為 100 個指示。此外，任何輸入資料的大小，例如 URL 值，皆可能影響指示計數。
* 不僅要注意指令碼效能，還要注意所有指令碼的綜合效能。作為最佳實踐， [!DNL Adobe] 建議的指令總數少於5,000條。 計算指令數目並不明顯，但需要注意的是，超過2,000條指令的指令碼會自動禁用。 活動配置檔案指令碼的數量不應超過300個。 每個指令碼都與每個單盒調用一起執行。 視需要執行多個指令碼。
* 在regex中，在開頭有點星(例如： `/.*match/`。 `/a|.*b/`)幾乎從不需要。 規則運算式搜尋會從字串中的所有位置開始 (除非受到 `^` 限制)，因此已假設點星號。如果此類規則運算式符合長度足夠的輸入資料 (可能至少有數百個字元)，指令碼執行可能會中斷。
* 如果全部失敗，將指令碼包覆在 try/catch 中。
* 以下建議可幫助您限制配置檔案指令碼的複雜性。 配置檔案指令碼可以執行有限數量的指令。

   作為最佳做法：

   * 保持配置檔案指令碼的小小和盡可能簡單。
   * 避免規則運算式或僅使用簡單的規則運算式。 即使是簡單的表達式，也可能需要很多指令來計算。
   * 避免遞歸。
   * 配置檔案指令碼在添加到 [!DNL Target]。 所有配置檔案指令碼在每個框請求上執行。 如果配置檔案指令碼未正確執行，則mbox請求的執行時間會更長，這可能會影響通信和轉換。
   * 如果配置檔案指令碼變得太複雜，請考慮使用 [響應令牌](/help/main/administrating-target/response-tokens.md) 的雙曲餘切值。

* 有關詳細資訊，請參閱JS Rhino引擎文檔。

## 偵錯設定檔指令碼 {#section_E9F933DE47EC4B4E9AF2463B181CE2DA}

以下方法可用於偵錯設定檔指令碼:

>[!NOTE]
>
>使用 [!DNL console.log] 配置檔案指令碼中不輸出配置檔案值，因為配置檔案指令碼執行伺服器端。

* **將配置檔案指令碼作為響應令牌添加到調試配置檔案指令碼：**

   在 [!DNL Target]按一下 **[!UICONTROL 管理]**&#x200B;按一下 **[!UICONTROL 響應令牌]**，然後啟用要調試的配置檔案指令碼。

   每次您載入網站的頁面時 [!DNL Target] 在上面，部分回復來自 [!DNL Target] 包含給定配置檔案指令碼的值，如下所示：

   ![](assets/debug_profile_script_1.png)

* **使用mboxTrace調試工具調試配置檔案指令碼。**

   此方法需要通過按一下 **[!UICONTROL 目標]** > **[!UICONTROL 管理]** > **[!UICONTROL 實施]** > **[!UICONTROL 生成授權令牌]** 的 [!UICONTROL 調試器工具] 的子菜單。

   然後，在「？」之後，將這兩個參數添加到頁面URL: `mboxTrace=window&authorization=YOURTOKEN`。

   添加這些參數比響應標籤更具說明性，因為您會獲得配置檔案的未執行快照和後快照。 它還顯示所有可用的配置檔案。

   ![](assets/debug_profile_script_2.png)

## 設定檔指令碼常見問題集 {#section_1389497BB6D84FC38958AE43AAA6E712}

**是否能夠使用設定檔指令碼從資料層中的頁面擷取資訊?**

由於設定檔指令碼於伺服器端執行，因此其無法直接讀取頁面。必須透過 mbox 要求或其他[將資料傳入 Target 的方法](/help/main/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md#concept_0069C0EFB56C4700BB33F2F35C2B9B17)傳遞資料。資料輸入後 [!DNL Target]，配置檔案指令碼可以將資料作為mbox參數或配置檔案參數讀取。

## 指令碼設定檔參數的 JavaScript 參考資料

要有效使用指令碼配置檔案參數，需要簡單的Javascript知識。 本節可做為快速參考資料，只需要幾分鐘，就能讓您提高使用此功能的效率。

您可以在 mbox/設定檔標籤下找到指令碼設定檔參數。您可以撰寫傳回任何 Javascript 類型 (字串、整數、陣列等) 的 Javascript 程式。

### 指令碼設定檔參數範例 {#examples}

**名稱:** *user.recency*

```
var dayInMillis = 3600 * 24 * 1000;
if (mbox.name == 'orderThankyouPage') {
    user.setLocal('lastPurchaseTime', new Date().getTime());
}
var lastPurchaseTime = user.getLocal('lastPurchaseTime');
if (lastPurchaseTime) {
    return ((new Date()).getTime() - lastPurchaseTime) / dayInMillis;
}
```

建立一個日的變數 (以毫秒為測量單位)。如果框名稱為 `orderThankyouPage`，設定名為的本地（不可見）用戶配置檔案屬性 `lastPurchaseTime` 顯示當前日期和時間的值。 讀取上次購買時間的值，如果定義， [!DNL Target] 返回自上次採購時間以來經過的時間，除以一天中的毫秒數（這將導致自上次採購以來的天數）。

**名稱:** *user.frequency*

```
var frequency = user.get('frequency') || 0;
if (mbox.name == 'orderThankyouPage') {
    return frequency + 1;
}
```

建立名為 `frequency`，如果沒有上一個值，則將其初始化為上一個值或0。 如果 mbox 名稱為 `orderThankyouPage`，則會傳回遞增的值。

**名稱:** *user.monetaryValue*

```
var monetaryValue = user.get('monetaryValue') || 0;
if (mbox.name == 'orderThankyouPage') {
    return monetaryValue + parseInt(mbox.param('orderTotal'));
}
```

建立稱為 `monetaryValue` 的變數，查詢指定訪客目前的值 (或如果沒有先前的值，則設為 0)。如果 mbox 名稱為 `orderThankyouPage`，系統會將先前的值與傳遞給 mbox 的 `orderTotal` 參數的值相加，以傳回新貨幣值。

**名稱：** adobeQA

```
if (page.param("adobeQA"))
     return page.param("adobeQA");
else if (page.param("adobeqa"))
     return page.param("adobeqa");
else if (mbox.param("adobeQA"))
     return mbox.param("adobeQA");
```

建立名為 `adobeQA` 跟蹤用戶 [活動QA](/help/main/c-activities/c-activity-qa/activity-qa.md)。

### 物件和方法 {#objects}

指令碼配置檔案參數可以引用以下對象和方法：

| 物件或方法 | 詳細資料 |
| --- | --- |
| `page.url` | 目前的 URL。 |
| `page.protocol` | 用於頁面的通訊協定 (http 或 https)。 |
| `page.domain` | 目前的 URL 網域 (第一個正斜線之前的所有內容)。例如，`http://www.acme.com/categories/men_jeans?color=blu e&size=small` 中的 `www.acme.com`。 |
| `page.query` | 目前頁面的查詢字串。‘?’ 之後的所有內容。例如，`http://www.acme.com/categories/mens_jeans?color=blue&size=small` 中的 `blue&size=small`。 |
| `page.param(‘<par_name>’)` | 由 `<par_name>` 指示之參數的值。如果您目前的 URL 是 Google 的搜尋頁面，而您已經輸入 `page.param('hl')`，則就 URL `http://www.google.com/search?hl=en& q=what+is+asdf&btnG=Google+Search` 而言會得到「en」。 |
| `page.referrer` | 與上述操作集相同的操作適用於引用和登錄（即，referrer.url是引用者的url地址）。 |
| `landing.url`, `landing.protocol`, `landing.query`, 和 `landing.param` | 與頁面的該項目類似，但適用於登陸頁面。 |
| `mbox.name` | 使用中的 mbox 名稱。 |
| `mbox.param(‘<par_name>’)` | 根據使用中 mbox 的指定名稱的 mbox 參數。 |
| `profile.get(‘<par_name>’)` | 根據 `<par_name>` 名稱之由用戶端建立的使用者設定檔參數。例如，如果使用者設定名為「性別」的設定檔參數，可使用「profile.gender」擷取此值。傳回為目前訪客設定的「`profile.<par_name>`」的值；如果沒有設定任何值，則會傳回 null。請注意 `profile.get(<par_name>)` 被限定為函式調用。 |
| `user.get(‘<par_name>’)` | 傳回為目前訪客設定的「`user.<par_name>`」的值；如果沒有設定任何值，則會傳回 null。 |
| `user.categoryAffinity` | 傳回最佳類別的名稱。 |
| `user.categoryAffinities` | 傳回具有最佳類別的陣列。 |
| `user.isFirstSession` | 如果這是訪客的第一個工作階段，則會傳回 true。 |
| `user.browser` | 傳回 HTTP 標頭中的使用者代理程式。舉例來說，您可以建立只將目標鎖定於 Safari 使用者的運算式目標: `if (user.browser != null && user.browser.indexOf('Safari') != -1) { return true; }` |

### 常見運算子


所有標準 JavaScript 運算子皆存在且可供使用。JavaScript運算子可用於字串和數字（以及其他資料類型）。 快速簡短說明:

| 運算元 | 說明 |
| --- | --- |
| `==` | 代表相等。當兩側運算元相等時，則為 true。 |
| `!=` | 代表不相等。當兩側運算元不相等時，則為 true。 |
| `<` | 代表左側的變數小於右側的變數。如果變數相等，則計算為false。 |
| `>` | 代表左側的變數大於右側的變數。如果變數相等，則計算為false。 |
| `<=` | 與 `<` 如果變數相等，則計算結果為true。 |
| `>=` | 與 `>` 如果變數相等，則計算結果為true。 |
| `&&` | 邏輯上，「AND」左側和右側的運算式，只有在兩側皆為 true 時，才會是 true (否則則為 false)。 |
| `||` | 邏輯上，「OR」左側和右側的運算式，只有在其中一側為 true 時，才會是 true (否則則為 false)。 |
| `//` | 檢查來源是否包含目標布林值包含的所有元素 (陣列來源、陣列目標)。<br>`//` 會從目標擷取子字串 (對應 regexp)，然後將其解碼 `Array/*String*/ decode(String encoding, String regexp, String target)`。<br>此功能也支援使用常數字串值、分組 (`condition1 || condition2) && condition3`，以及規則運算式 (`/[^a-z]$/.test(landing.referring.url)`。 |

## 培訓視頻：配置檔案指令碼 ![教程徽章](/help/main/assets/tutorial.png)

此影片包含使用和建立設定檔指令碼的相關資訊。

* 解釋什麼是設定檔指令碼
* 解釋設定檔指令碼和設定檔參數有何不同
* 建立簡單的設定檔指令碼
* 使用「可用 Token」功能表來存取可用的選項
* 啟用和停用設定檔指令碼

>[!VIDEO](https://video.tv.adobe.com/v/17394)
