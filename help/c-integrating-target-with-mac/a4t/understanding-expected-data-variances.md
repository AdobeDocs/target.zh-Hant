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
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# 使用和不使用 A4T 時，Target 與 Analytics 之間的預期資料差異{#expected-data-variances-when-not-using-a-t}

有關*使用*和*不使用* Analytics 做為報表來源 (A4T) 時，[!DNL Target] 和 Adobe [!DNL Analytics] 之間預期資料差異的資訊。A4T 可大幅減少資料差異.

## 使用 A4T 時的預期資料差異 {#expected-using-a4t}

若使用 A4T，活動的 Analytics 與 Target 報表皆僅使用 Analytics 資料，因此 Target 活動報表中的解決方案之間沒有差異。但是，在某些情況下，客戶可能會將 Target 資料與 A4T 整合範圍以外的 Analytics 資料進行比較，因此，請體驗下列所述的差異問題。

以下是一些您可能會遇到預期資料差異的案例:

* A4T 允許 Target 點擊 (頁面頂端) 發生的可能性，但不允許 Analytics 點擊 (頁面底部) 發生。舉例來說，如果使用者載入頁面，但瀏覽器在觸發 Analytics 呼叫前關閉。在這些案例中，A4T 會從我們的資料中排除 Target 點擊。原因在於，若允許在沒有實際 Analytics 呼叫的情況下，將 Target 點擊 (同樣位於頁面頂端) 計算為 Analytics 點擊，則會產生與 Analytics 中的資料集不一致的情況 (訪客膨脹等)。

   若已在 Target 中將重新導向測試設定為分割流量 50/50 (或 25/25/25/25 等)，使用者行為可能無法除盡。如果您看到不平均的分割，這就表示相較於其他群組，某個使用者群組無法在登陸頁面上執行 Analytics 呼叫。這種某個群組無法執行 Analytics 呼叫的情況導致了該使用者的 Target 點擊遭到排除，產生不平均的問題。

   這是我們希望在 Adobe Experience Platform 上邁向 A4T 的同時，能在未來處理的問題。我們的團隊正在努力尋找在不同時間點發生的這些頁面上的不同事件的最佳處理方法。

* 假設您建立了一個在特定頁面開放給所有訪客的自動分配活動。由於「自動分配」活動不支援 A4T，因此 [!DNL Target] 會收集所有活動資料。您可能希望 [!DNL Target] 報表中的活動訪客數與相同日期範圍內 [!DNL Analytics] 報表中該頁面的訪客數相符。這是下列所述之預期差異的案例。

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