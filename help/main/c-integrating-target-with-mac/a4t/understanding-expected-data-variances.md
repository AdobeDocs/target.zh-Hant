---
keywords: 資料差異;analytics;差異;差別;a4t;analytics for target;analytics 作為報表來源
description: 瞭解Adobe [!DNL Target] 與Analytics之間未使用Analytics for [!DNL Target] (A4T)時的預期資料差異，其可完全消弭資料差異。
title: Analytics和A4T之間的預期資料差異為何？
feature: Analytics for Target (A4T)
exl-id: 9e63f309-8ec1-4ed5-a1f9-6c3098a7b8f6
source-git-commit: 4abd24f63dd65e65a1d8b07647630eeb640e7a1d
workflow-type: tm+mt
source-wordcount: '730'
ht-degree: 45%

---

# 使用和不使用A4T時，Adobe[!DNL Target]和Adobe Analytics之間的預期資料差異

有關&#x200B;*使用*&#x200B;和&#x200B;*不使用* Analytics 做為報表來源 (A4T) 時，[!DNL Target] 和 Adobe [!DNL Analytics] 之間預期資料差異的資訊。A4T 可大幅減少資料差異.

## 使用A4T時的預期資料差異 {#expected-using-a4t}

若使用 A4T，活動的 Analytics 與 Target 報表皆僅使用 Analytics 資料，因此 Target 活動報表中的解決方案之間沒有差異。但是，在某些情況下，客戶會將Target資料與A4T整合範圍以外的Analytics資料進行比較，因此，請體驗下列所述的差異問題。

以下是一些您可能會遇到預期資料差異的案例：

* A4T 允許 Target 點擊 (頁面頂端) 發生的可能性，但不允許 Analytics 點擊 (頁面底部) 發生。例如，假設訪客載入頁面，但在觸發Analytics呼叫之前關閉瀏覽器。 在這些情況下，A4T會從資料中排除Target點選。 若允許Target點選（同樣位於頁面頂端）在沒有實際Analytics呼叫的情況下計為Analytics點選，則會產生與Analytics中的資料集不一致的情況（訪客膨脹等）。

  如果Target中將重新導向測試設定為分割流量50/50 （或25/25/25/25/25等），使用者行為可能無法平均分割。 如果您看到不平均的分割，這就表示相較於其他群組，某個使用者群組無法在登陸頁面上執行Analytics呼叫。 這種某個群組無法執行 Analytics 呼叫的情況導致了該使用者的 Target 點擊遭到排除，產生不平均的問題。

  Adobe希望在Adobe團隊致力於Adobe Experience Platform上的A4T的同時，能在未來解決這個問題。 Adobe團隊正在決定如何處理頁面上不同時間發生的這些不同事件。

## *不使用* A4T 時的預期資料差異 {#expected-not-using-a4t}

即使是使用相似的資料集，有 15-20% 的差異也是正常的。算法不同的系統可能會導致更高的資料差異，高達 35-50%。有時候，差異可能更高。

雖然實際的資料可能會大幅不同，但趨勢通常會是一致的。只要差異與趨勢保持一致，這些資料還是十分重要而且非常有用。如果差異與趨勢不一致，可能表示某個設定不正確。此時請連絡您的帳戶代表以取得協助。

[!DNL Analytics] 使用的系統是根據瀏覽次數與交易，但是 使用的是以訪客為主的度量。[!DNL Target]無論訪客何時開啟頁面，都會將其計為[!DNL Analytics]中的一次造訪，但在符合活動中設定的條件之前，[!DNL Target]不會計算該次造訪。

[!DNL Target]中的報表根據定義活動時選取的轉換mbox來顯示效能。 不過，此轉換mbox資料不會傳送至[!DNL Analytics]，其專用的轉換變數是由您的[!DNL Analytics]標籤實作所定義。 在您預期會有相同資料的地方（例如，如果零售商的訂單確認頁面同時包含轉換mbox和[!DNL Analytics]購買事件），資料可能會因這些標籤的位置而有所不同。 一般而言，這兩種產品報表中的趨勢都類似。

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
* 多個頁面上的單一mbox，計算每個頁面上的訪客
* 活動優先順序可包含頁面上的一些訪客，並排除其他訪客
* 重新進入活動時，轉換一次的訪客可再次計算
* [!DNL Analytics] 會計算所有瀏覽和訪客的所有轉換次數，但 [!DNL Target] 僅會計算活動中包含之瀏覽和訪客的轉換次數。
