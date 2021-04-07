---
keywords: 實施；實施；設定；設定；指令碼配置檔案屬性
description: 使用指令碼描述檔屬性將資料匯入Target。
title: 如何使用指令碼描述檔屬性將資料匯入Target?
feature: 實施
role: Developer
translation-type: tm+mt
source-git-commit: 70d4c5b4166081751246e867d90d43b67efa5469
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 83%

---

# 指令碼設定檔屬性

指令碼描述檔屬性是[!DNL Adobe Target]解決方案中定義的名稱／值對。 值取決於每次伺服器呼叫在 Target 的伺服器上執行 JavaScript 片段。

使用者撰寫較小的程式碼片段，在每次 mbox 呼叫時執行，以及在評估訪客的對象和活動成員資格之前執行。

## 格式

指令碼設定檔屬性是在 Target 的「對象」區段中建立。任何屬性名稱都有效，值是 Target 使用者撰寫的 JavaScript 函式的結果。在 Target 中，屬性名稱開頭自動加上 &quot;user.&quot;，以方便與頁面內設定檔屬性有所區別。

程式碼片段以 Rhino JS 語言撰寫，可參考 Token 和其他值。

## 範例使用案例

* **購物車放棄**: 當訪客到達購物車時，將設定檔指令碼設為 1。當訪客轉換時，重設為 0。如果值 = 1，表示訪客在購物車中有一件項目。
* **造訪計數**: 每次新的造訪時，計數就增加 1，以追蹤訪客每隔多久回到網站。

## 方法的優點

不需要更新頁面程式碼。

在決定對象和活動成員資格之前執行，因此，這些設定檔指令碼屬性在單次伺服器呼叫上就可影響成員資格。

可能非常強大。每個指令碼最多可執行 2,000 個指令。

## 注意事項

需要 JavaScript 知識。

無法保證設定檔指令碼的執行順序，因此無法彼此依賴。

可能很難偵錯。

## 程式碼範例

設定檔指令碼相當有彈性:

`user.purchase_recency: var dayInMillis = 3600 * 24 * 1000; if (mbox.name == 'orderThankyouPage') {  user.setLocal('lastPurchaseTime', new Date().getTime()); } var lastPurchaseTime = user.getLocal('lastPurchaseTime'); if (lastPurchaseTime) {  return ((new Date()).getTime()-lastPurchaseTime)/dayInMillis; }`

### 相關資訊的連結

[設定檔指令碼屬性](/help/c-target/c-visitor-profile/profile-parameters.md#concept_8C07AEAB0A144FECA8B4FEB091AED4D2)