---
description: 關於體驗鎖定目標和對象常見問題集 (FAQ) 的清單。
keywords: 疑難排解;常見問題集;FAQ;目標;對象
seo-description: 關於體驗鎖定目標和對象常見問題集 (FAQ) 的清單。
seo-title: 鎖定目標和對象常見問題集
solution: Target
title: 鎖定目標和對象常見問題集
topic: Standard
uuid: 4a8d977a-aa98-4aff-843e-ace32b8eed53
translation-type: tm+mt
source-git-commit: 98902870c9949302eecfffc4da31b662651c4f8b

---


# 鎖定目標和對象常見問題集{#targets-and-audiences-faq}

關於體驗鎖定目標和對象常見問題集 (FAQ) 的清單。

## 建置對象時，為什麼在 Target 資料庫下預先建置的對象會出現在其他類別中? {#section_9EBF5B0F9DF94168A15B92B905CCF7E0}

Target 資料庫類別中預先建置的對象為舊版對象，並且存在於其他類別。舉例來說，舊版「Target 資料庫 &gt; 新訪客」對象有更新的對應項:「訪客設定檔 &gt; 新訪客」。

最佳做法是使用較新的對象，因為效能更好。部分客戶使用的可能是舊版、預先建立的對象，因此尚未從 Target 介面中移除。

## 如何知道對象之間如何分割流量?  {#section_067EEFB956E7465CBF77EC86834470AB}

依預設，流量會在體驗之間平均分割。不過，您可以指定每個體驗的百分比目標。在這種情況下會產生亂數，使用此數字選擇顯示的體驗。結果百分比可能和指定目標不完全相同，但流量更多表示體驗分割就會更接近定位目標。

## 如果使用者符合活動的資格，而該活動包含多個體驗和多個合格對象，將會顯示哪一個體驗?  {#section_94A60B11212D48FD8AB0803C6C7E7253}

使用者的資格會符合活動的 [!UICONTROL Target] 頁面上所顯示的第一個體驗/對象。

例如，在下圖中，來自加州且使用 Windows 裝置的使用者，會同時符合體驗 A (Windows 對象) 和體驗 C (加州對象) 的資格。此使用者會看到體驗 A，因為在目標頁面上，此體驗在清單中出現在體驗 C 上方。

![](assets/audiences_order.png)

## 在 Target、Audience Manager (AAM) 和核心服務中的對象程式庫中，同一對象的名稱為何不同? {#section_F67E61A607B6444C8DAA4F99C3E95AED}

對象名稱 [!DNL Target] 是唯一的；但是，您 [!DNL AAM] 可以 [!DNL Audience Library]對多個對象擁有相同的名稱(如果它們位於不同資料夾中)。 [!DNL Target] 遇到對應至某 [!DNL AAM] 或 [!DNL Audience Library] 對象的對象名稱時， [!DNL Target] 會附加「#&lt; number&gt;」至名稱。

例如，您可能會看到下列對象:「PC 使用者」(在 [!DNL AAM] 中) 和「PC 使用者 #1」(在 [!DNL Target] 中)。

## 為何無法重新命名對象? {#section_54E420556F534D20836E261E253D8B97}

部分 Target 對象是預先定義的，例如「新訪客」和「再度訪問的訪客」。使用者無法重新命名這些對象。

## Target 使用者介面中為何不顯示所有設定檔參數?  {#section_3CD947D15C984EE9AD19550220E0E8BD}

[!DNL Target] 具有每個 mbox 呼叫 50 個獨特設定檔屬性的限制。如果您需要傳遞超過 50 個設定檔屬性至 [!DNL Target]，則可以使用 [!UICONTROL 設定檔更新] API 方法來傳遞它們。如需詳細資訊，請參閱 Adobe Target API 文件中的[設定檔更新](https://developers.adobetarget.com/api/#authentication-tokens)。

## 訪客在 AP 活動中為何看到不應該看到的體驗? {#section_41CECEAE0881446A8D9F3B016857914B}

在每個工作階段都會評估一次自動個人化活動。如果特定體驗有合格的使用中工作階段，且現在該體驗中已新增選件，則除了先前顯示的選件，使用者還會看到新內容。因為使用者先前已符合那些體驗的資格，所以在工作階段期間仍然會看見那些體驗。如果您想要在每次頁面造訪都進行評估，則應該改用體驗鎖定目標 (XT) 活動類型。

## 為什麼透過 API 建立之對象所做的變更未反映在 Target UI 中?  {#section_6BEB237CAC004A06A290F9644E5BF0FB}

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

以科學注釋撰寫的數字一律會與字串做比較。

例如，

&quot;4e-2&quot; 只等於 &quot;4e-2&quot;，*不*等於 &quot;0.04&quot;。