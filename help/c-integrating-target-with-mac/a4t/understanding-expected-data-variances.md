---
description: 有關不使用 Analytics 作為報表來源 (A4T) 時 (其可完全消弭資料差異)，Target 和 Adobe Analytics 之間預期資料差異的資訊。
keywords: 資料差異;analytics;差異;差別;a4t;analytics for target;analytics 作為報表來源
seo-description: 有關不使用 Analytics 作為報表來源 (A4T) 時 (其可完全消弭資料差異)，Target 和 Adobe Analytics 之間預期資料差異的資訊。
seo-title: 不使用 A4T 時的預期資料差異
solution: Target
title: 不使用 A4T 時的預期資料差異
topic: 進階
uuid: 61bef460-8613-4251-b1b2-b6226ec86d9b
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# 使用和不使用 A4T 時，Target 與 Analytics 之間的預期資料差異{#expected-data-variances-when-not-using-a-t}

關於使用Analytics做為報告來源 [!DNL Target] (A4T) [!DNL Analytics] 時 *，與* Adobe ** 之間預期之資料差異的資訊。A4T 可大幅減少資料差異.

## 使用A4T時預期的資料差異 {#expected-using-a4t}

若使用 A4T，活動的 Analytics 與 Target 報表皆僅使用 Analytics 資料，因此 Target 活動報表中的解決方案之間沒有差異。但是，在某些情況下，客戶可能會將 Target 資料與 A4T 整合範圍以外的 Analytics 資料進行比較，因此，請體驗下列所述的差異問題。

以下是您可能遇到預期資料差異的幾個案例：

* A4T允許Target點擊(頁面頂端)發生，但沒有Analytics點擊(頁面底部)。例如，如果使用者載入頁面，但在觸發Analytics呼叫之前關閉瀏覽器。在這種情況下，A4T會排除來自資料的Target點擊。原因在於，允許Target點擊(又同樣於頁面頂端)計數為Analytics點擊時，會產生與Analytics中的資料集不一致(訪客膨脹等)的不一致。

   如果Target中的重新導向測試設定為分割流量50/50(或25/25/25/25等)，使用者行為可能不會平均分割。如果您看到不一致的分割，表示一組使用者無法在著陸頁面上執行Analytics呼叫，而非其他群組的執行。如果無法對某個群組執行Analytics呼叫，將會排除該使用者的Target點擊，因而造成不知情。

   我們希望在Adobe Experience Platform上推出A4T時，未來能解決這個問題。我們的團隊正在研究如何最佳處理不同時間在頁面上發生的不同事件。

* 假設您為特定頁面的所有訪客建立「自動分配」活動。由於「自動分配」活動不支援 A4T，因此 [!DNL Target] 會收集所有活動資料。您可能希望 [!DNL Target] 報表中的活動訪客數與相同日期範圍內 [!DNL Analytics] 報表中該頁面的訪客數相符。這是下列所述之預期差異的案例。

   如需支援 A4T 的活動類型完整清單，請參閱[支援的活動類型](../../c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA)。

## *不使用* A4T 時的預期資料差異 {#expected-not-using-a4t}

即使是使用相似的資料集，有 15-20% 的差異也是正常的。算法不同的系統可能會導致更高的資料差異，高達 35-50%。在某些情況下，差異可能還會更高。

雖然實際的資料可能會大幅不同，但趨勢通常會是一致的。只要差異與趨勢保持一致，這些資料還是十分重要而且非常有用。如果差異與趨勢不一致，可能表示某個設定不正確。此時請連絡您的帳戶代表以取得協助。

[!DNL Analytics] 使用的系統是根據瀏覽次數與交易，但是 使用的是以訪客為主的度量。[!DNL Target]這表示無論訪客何時開啟頁面，都會將其計入 [!DNL Analytics] 中的瀏覽數，但在符合活動中設定的條件之前，[!DNL Target] 不會計算瀏覽數。

[!DNL Target] 中的報表根據定義活動時選取的轉換 mbox 顯示成效，但此轉換 mbox 資料不會傳送到 [!DNL Analytics]，其專用的轉換變數是由您的 [!DNL Analytics] 標籤實作所定義。在您預期會有相同資料的情況下 (例如，如果零售商的訂購確認頁面同時包含轉換 mbox 和 [!DNL Analytics] 購買事件)，資料可能會因這些標籤的位置而有所不同。一般而言，兩種產品報表中的趨勢應該是類似的。

預期的資料差異可能是因為技術與業務差異所致。

### 技術差異的範例 {#section_C3B50ED2E2F9416FAC91437CF1A87369}

下列的技術差異可能造成資料差異:

* [!DNL Target] 訪客必須同意允許 Cookie 與 JavaScript
* 第一方和第三方 Cookie 的處理方式不同；因此，這些 Cookie 類型的資料不相符
* 頁面上標記的相關位置，以及因訪客在頁面尚未完全載入前離開此頁面所造成的「資料流失」
* 時區考量
* 可計算的裝置差異

### 業務差異的範例 {#section_2E1EB5E15BB64A1A80E4CDB1A5062AEE}

下列的業務差異可能造成資料差異:

* 訪客與瀏覽度量之間的差異
* 鎖定目標的活動不包括某些訪客
* 可將單一 mbox 放在多個頁面上，計算其中每個頁面上的訪客
* 活動優先順序可能包括某些訪客，且排除頁面上的其他訪客
* 轉換過一次的訪客在重新進入活動時可以再次計入
* [!DNL Analytics] 會計算所有瀏覽和訪客的所有轉換次數，但 [!DNL Target] 僅會計算活動中包含之瀏覽和訪客的轉換次數。