---
keywords: 推薦
description: 探索常見案例，說明在視覺化體驗撰寫器(VEC)中對您的頁面所做的變更如何影響Adobe Target顯示體驗的功能。
title: 哪些是常見的頁面修改案例？
feature: Visual Experience Composer (VEC)
exl-id: 7a05fbf9-3427-436e-a54f-4f1dd16d885a
TQID: 'https://experienceleague.adobe.com/BI2SnUU5ilCf0auld15q1rpCrnLoPEwbe1fZO6G1quc'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '626'
ht-degree: 4%
---
# 頁面修改案例 {#vec-scenarios}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解對[!DNL Target]外部頁面所做的變更如何影響[!DNL Target]顯示體驗的能力，透過七個案例和範例。

>[!ENDSHADEBOX]

[!DNL Target]選擇器決定體驗的顯示位置。 在[!DNL Target]之外修改頁面時，變更可能會影響[!DNL Target]尋找該位置並顯示體驗的能力。

選取器一律與不重複類別搭配使用，不等同於ID。 若未將任何類別指派給元素，選取器即會計入具有相同標籤名稱的先前同層級。

>[!NOTE]
>
>案例使用清單專案作為範例，但概念適用於任何元素。

下表總結了情境。 在每個案例中，選取器都是`#wrap > ul.nav:eq(0) > li.women-section:eq(0)`。

| 藍本 | 已套用動作 | 原因 |
|---|---|---|
| 在選取的元素前面，插入具有不同類別名稱的元素 | 是 | `li.women-section:eq(0)`不受影響 |
| 插入與所選元素具有相同類別名稱的元素 | 否 | 新元素會佔據第一個位置，這會破壞選取器 |
| 在選取的元素後面插入元素 | 是 | 新元素會新增至與父元素對應的相同位置 |
| 移除所選元素前面緊鄰的元素 | 是 | 所選專案的類別未變更 |
| 移除所選元素後面緊鄰的元素 | 是 | 所選專案的類別未變更 |
| 移除選取的元素 | 是 | 元素已成功移除 |
| 重新命名所選元素的類別 | 否 | 找不到`class` |

## 在選取的元素前面，插入具有不同類別名稱的元素

新元素會插入為[!DNL Target]選取器中元素的同層級。 如果JavaScript已新增元素上的第一個類別，則傳送會失敗且不會套用動作。

**插入的元素:**

```html
<li class="kids-section">Kids</li>
```

**選取的元素：**

`<li class="women-section">Women</li>`

**選取器：** `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**結果：**&#x200B;選取器如預期般運作，因為`li.women-section:eq(0)`不受影響。

**之前：**

```html
<div id="wrap">
     <ul class="nav">
        <li class="men-section"> Men</li> <li class="women-section">Women</li>
     </ul>
</div>
```

**之後：**

```html
<div id="wrap">
    <ul class="nav">
        <li class="kids-section">Kids</li>
        <li class="men-section"> Men</li>       <li class="women-section">Women</li>
    </ul>
</div>
```

## 插入與所選元素具有相同類別名稱的元素

在選取清單專案時插入清單。

**插入的元素:**

```html
<ul class="nav">
   <li class="item"> Sale </li>
   <li class="item"> Offers </li>
</ul>
```

**選取的元素：**

`<li class="women-section">Women</li>`

**選取器：** `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**結果：**&#x200B;選取器無法運作。 `ul.nav:eq(0)`現在指向無法使用的動態新增元素，因此不會套用動作。 在建立活動後，以動態或手動方式新增具有相同類別的類似清單專案時，會將新元素放在第一個位置，這會破壞選取器。

**之前：**

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section"> Men</li>       <li class="women-section">Women</li>
    </ul>
</div>
```

**之後（嘗試）：**

```html
<div id="wrap">
     <ul class="nav">
        <li class="item"> Sale</li>
        <li> class="item"> Offers</li>
     </ul>
     <ul class="nav">
       <li class="men-section"> Men</li>
       <li class="women-section">Women</li>
    </ul>
</div>
```

## 在選取的元素後面插入元素

清單會插入在選取的清單專案之後。

**插入的元素:**

```html
<ul class="nav">
   <li class="men-section"> Men Clothes</li>
   <li class="women-section"> Women Clothes</li>
</ul>
```

**選取的元素：**

`<li class="women-section">Women Shoes</li>`

**選取器：** `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**結果：**&#x200B;在結尾為選取專案的清單後面插入清單會如預期般運作。 新元素會新增至與所選元素相同的位置（相對於父元素）。

**之前：**

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men Shoes </li>       <li class="women-section">Women Shoes</li>
    </ul>
</div>
```

**之後：**

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men Shoes </li>
        <li class="women-section">Women Shoes</li>
    </ul>
      <ul class="nav">
        <li class="men-section">Men Clothes</li>
        <li class="women-section"> Women Clothes</li>
    </ul>
</div>
```

## 移除所選元素前面緊鄰的元素

刪除所選元素之前的清單專案。

**移除的元素:**

```html
<li class="men-section"> Men </li>
```

**選取的元素：**

`<li class="women-section">Women</li>`

**選取器：** `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**結果：**&#x200B;已成功移除專案，因為未變更選取專案的類別。

**之前：**

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-section">Women</li>
    </ul>
</div>
```

**之後：**

```html
<div id="wrap">
    <ul class="nav">
        <li class="women-section">Women</li>
    </ul>
</div>
```

## 移除所選元素後面緊鄰的元素

刪除所選元素後的清單專案。

**移除的元素:**

```html
<li class="kids-section">Kids</li>
```

**選取的元素：**

`<li class="women-section">Women</li>`

**選取器：** `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**結果：**&#x200B;已成功移除專案，因為選取專案的類別未變更，而且移除的專案在其父子樹狀結構中有唯一的類別。

**之前：**

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-section">Women</li>
        <li class="kids-section">Kids</li>
    </ul>
</div>
```

**之後：**

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-section">Women</li>
    </ul>
</div>
```

## 移除選取的元素

所選的清單專案即被刪除。

**移除的元素:**

```html
<li class="women-section">Women</li>
```

**選取的元素：**

`<li class="women-section">Women</li>`

**選取器：** `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**結果：**&#x200B;已成功移除專案。

**之前：**

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-section">Women</li>
    </ul>
</div>
```

**之後：**

```html
<div id="wrap">
    <ul class="nav">
       <li class="men-section">Men</li>
    </ul>
</div>
```

## 重新命名所選元素的類別

選取清單專案的類別已變更。

**變更的元素:**

```html
<li class="women-section">Women</li>
```

**選取的元素：**

`<li class="women-section">Women</li>`

**選取器：** `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**結果：**&#x200B;無法重新命名類別，因為找不到`class`。

**之前：**

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-section">Women</li>
    </ul>
</div>
```

**之後（嘗試）：**

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-shoes">Women</li>
    </ul>
</div> 
```
