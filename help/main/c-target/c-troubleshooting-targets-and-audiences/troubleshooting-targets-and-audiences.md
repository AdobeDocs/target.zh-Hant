---
keywords: 疑難排解;常見問題集;FAQ;目標;對象
description: 檢視體驗鎖定目標和Adobe中使用對象的常見問題集(FAQ) [!DNL Target] 活動。
title: 我可以在哪裡找到關於目標和對象的問題和答案？
feature: Audiences
exl-id: f829bd4a-852a-4eb1-85d1-89e74c14b37e
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '950'
ht-degree: 64%

---

# 鎖定目標和對象常見問題集

關於體驗鎖定目標和對象常見問題集 (FAQ) 的清單。

## 如何 [!DNL Target] 評估目標定位中的URL? {#url}

Target會根據您在建立活動時是否使用對象URL鎖定目標，或您在建立對象時是否使用URL鎖定目標，以不同方式評估URL。

請考量下列URL:

`http://www.example.com/path1/path2/path3?queryStringParam1=test123&queryStringParam2=test7`

### 對象URL目標定位

若要套用對象URL鎖定目標，在建立活動時，請在「體驗」頁面（三步驟引導式工作流程的步驟一）上，按一下齒輪圖示，按一下「頁面傳送」，然後指定想要的URL。

![頁面傳送URL](/help/main/c-target/c-troubleshooting-targets-and-audiences/assets/activity-url.png)

對象URL目標定位會尋找完全相符的URL。 如果URL相符，Target就不會考慮進一步邏輯。 在上述URL中，如果活動設為開啟 `www.example.com`，則URL會與下列URL相符，因為對象URL鎖定目標不受任何限制：

* `www.example.com?query=something`
* `www.example.com?query=anything`
* `www.example.com?query=nothing&qa=true&stuff=random&product=shoes&height=superTall`

除了URL上的對象鎖定目標，您也可以指定查詢中可以的特定值。

### URL目標定位

若要套用URL鎖定目標，在建立對象時，按一下「新增規則」、按一下「網站頁面」、從第一個下拉式清單（「目前頁面」、「上一頁」或「登陸頁面」）中選取選項、從第二個下拉式清單中選取「URL」、指定求值器，然後指定所要的URL。

![網頁>目前頁面> URL](/help/main/c-target/c-troubleshooting-targets-and-audiences/assets/site-url.png)

URL定位會將URL轉換為一組要評估的規則：

* URL網域= `example.com`
* Path = path1/path2/path3
* queryStringParam1 = test123
* queryStringParam2 = test7

## 建立複雜URL字串時，會 [!DNL Target] 評估整個URL?

如果您在URL字串中使用相同參數名稱多次，HTTP會考量第一個參數名稱，並忽略具有相同名稱的後續參數。

例如，在下列URL字串中：

`https://www.adobe.com/SearchResults.aspx?sc=BM&fi=1&fr=1&ps=0&av=0&Category=C0010438&Category=C000047`

的第一個例項 `Category` 參數被評估，第二個 `Category` 參數會遭到忽略。

最佳實務是有多個值與單一類別相關聯，如下所示：

`https://www.adobe.com/SearchResults.aspx?sc=BM&fi=1&fr=1&ps=0&av=0&Category=C0010438,C000047`

## 建置對象時，為什麼在 [!DNL Target] 資料庫下預先建置的對象會出現在其他類別中? {#section_9EBF5B0F9DF94168A15B92B905CCF7E0}

Target 資料庫類別中預先建置的對象為舊版對象，並且存在於其他類別。舉例來說，舊版「Target 資料庫 > 新訪客」對象有更新的對應項:「訪客設定檔 > 新訪客」。

最佳做法是使用較新的對象，因為效能更好。部分客戶使用的可能是舊版、預先建立的對象，因此尚未從 Target 介面中移除。

## 如何知道對象之間如何分割流量? {#section_067EEFB956E7465CBF77EC86834470AB}

依預設，流量會在體驗之間平均分割。不過，您可以指定每個體驗的百分比目標。在這種情況下會產生亂數，使用此數字選擇顯示的體驗。結果百分比可能和指定目標不完全相同，但流量更多表示體驗分割就會更接近定位目標。

## 如果使用者符合活動的資格，而該活動包含多個體驗和多個合格對象，將會顯示哪一個體驗? {#section_94A60B11212D48FD8AB0803C6C7E7253}

使用者的資格會符合活動的 [!UICONTROL Target] 頁面上所顯示的第一個體驗/對象。

例如，在下圖中，來自加州且使用 Windows 裝置的使用者，會同時符合體驗 A (Windows 對象) 和體驗 C (加州對象) 的資格。此使用者會看到體驗 A，因為在目標頁面上，此體驗在清單中出現在體驗 C 上方。

![audiences_order image](assets/audiences_order.png)

## 在 [!DNL Target]、Audience Manager (AAM) 和核心服務中的對象程式庫中，同一對象的名稱為何不同? {#section_F67E61A607B6444C8DAA4F99C3E95AED}

對象名稱在 [!DNL Target] 中是唯一的；不過，在 [!DNL AAM] 和 [!DNL Audience Library] 中，多個對象可以有相同的名稱 (只要在不同資料夾中)。當 [!DNL Target] 遇到的對象名稱符合 [!DNL AAM] 或 [!DNL Audience Library] 對象時，[!DNL Target] 會在名稱後面附加 &quot;#&lt;number>&quot;。

例如，您可能會看到下列對象:「PC 使用者」(在 [!DNL AAM] 中) 和「PC 使用者 #1」(在 [!DNL Target] 中)。

## 為何無法重新命名對象? {#section_54E420556F534D20836E261E253D8B97}

部分 Target 對象是預先定義的，例如「新訪客」和「再度訪問的訪客」。使用者無法重新命名這些對象。

## 為何所有設定檔參數都未顯示在 [!DNL Target] 使用者介面？ {#section_3CD947D15C984EE9AD19550220E0E8BD}

[!DNL Target] 具有每個 mbox 呼叫 50 個獨特設定檔屬性的限制。如果您需要傳遞超過 50 個設定檔屬性至 [!DNL Target]，則可以使用 [!UICONTROL 設定檔更新] API 方法來傳遞它們。如需詳細資訊，請參閱 Adobe Target API 文件中的[設定檔更新](https://developers.adobetarget.com/api/#authentication-tokens)。

## 訪客在 AP 活動中為何看到不應該看到的體驗? {#section_41CECEAE0881446A8D9F3B016857914B}

在每個工作階段都會評估一次自動個人化活動。如果特定體驗有合格的使用中工作階段，且現在該體驗中已新增選件，則除了先前顯示的選件，使用者還會看到新內容。因為使用者先前已符合那些體驗的資格，所以在工作階段期間仍然會看見那些體驗。如果您想要在每次頁面造訪都進行評估，則應該改用體驗鎖定目標 (XT) 活動類型。

## 為什麼透過API建立之對象所做的變更沒有反映在 [!DNL Target] UI? {#section_6BEB237CAC004A06A290F9644E5BF0FB}

與選件和設定檔指令碼不同，API 對於 Target Standard 建立之對象所做的變更目前未同步回 Target UI。

## 代表數值的字串 (亦支援浮點數) 以數值形式比較。{#strings-that-represent-numbers}

如果等於運算式的左右兩部分可以剖析為數值，這兩個部分都會剖析為數值，而不是字串。

例如:

| 值 | 鎖定目標條件 | 結果 |
| --- | --- | --- |
| 1.0 | 等於 1 | true |
| 1 | equalsIgnoreCase 1.0 | true |
| 1.230 | 等於 1 | true |
| 1.500 | 等於 1.5 | true |
| 1.200 | 小於 2 | true |
| 2 | 大於 3.0 | false |
| 045 | 等於 45 | true |

以科學記號撰寫的數字一律會以數值形式比較。

例如，

&quot;4e-2&quot; 只等於 &quot;4e-2&quot;，*不*&#x200B;等於 &quot;0.04&quot;。
