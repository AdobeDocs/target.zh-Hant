---
keywords: Recommendations
description: 瀏覽常見方案，這些方案顯示在Visual Experience Composer(VEC)中對頁面所做的更改如何影響Adobe Target顯示體驗的能力。
title: 哪些常見頁面修改方案？
feature: Visual Experience Composer (VEC)
exl-id: 7a05fbf9-3427-436e-a54f-4f1dd16d885a
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 90%

---

# 頁面修改案例

本主題中的方案顯示對頁面所做的更改如何影響Adobe Target顯示體驗的能力。

Target 選取器會決定在何處顯示體驗。如果在 Target 外修改頁面，變更可能會造成 Target 無法顯示體驗。

使用選取器時，唯一類別不等同於 ID。選取器一律只使用唯一類別。如果未將類別指派給元素，選取器會計算先前具有相同標記名稱的同層級項目數。

>[!NOTE]
>
>雖然這些案例使用清單項目當作範例，但概念適用於任何元素。

## 情節: 在選取的元素前面，插入具有不同類別名稱的元素 {#section_298F661F72384F6AB957D5885A99D822}

在此範例中，會插入一個新元素作為 Target 選取器中元素的同層級項目。

JavaScript 有可能會新增元素上出現的第一個類別。在此情況下，傳送會失敗，也不會套用動作。

**插入的元素:**

```html
<li class="kids-section">Kids</li>
```

**已選取:**

`<li class="women-section">Women</li>`

選取器: `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**結果:**

因為 `li.women-section:eq(0)` 不受影響，選取器會正常運作。

在可以記錄:

```html
<div id="wrap">
     <ul class="nav">
        <li class="men-section"> Men</li> <li class="women-section">Women</li>
     </ul> 
</div>
```

之後:

```html
<div id="wrap">
    <ul class="nav">
        <li class="kids-section">Kids</li>
        <li class="men-section"> Men</li>       <li class="women-section">Women</li>
    </ul> 
</div>
```

## 情節: 插入與所選元素的類別名稱相同的元素 {#section_0969B88C2F154E648D9969C8C85EF55A}

在此情節中，會嘗試在已選取清單中的項目時插入清單。

**插入的元素:**

```html
<ul class="nav"> 
   <li class="item"> Sale </li> 
   <li> class="item"> Offers </li> 
</ul>
```

**已選取**

`<li class="women-section">Women</li>`

選取器: `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**結果:**

因為 `ul.nav:eq(0)` 提供了動態新增的元素，選取器無法運作。無法使用元素，也不會套用動作。在建立活動之後，動態或手動新增具有相同類別的類似清單項目時，第一個位置上會建立新元素。這會使選取器失去作用。

在可以記錄:

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section"> Men</li>       <li class="women-section">Women</li>
    </ul> 
</div>
```

之後 (理想結果):

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

## 情節: 在選取的元素後面插入元素 {#section_15B07B84BEE94ED39D85BBBE0733E170}

在此情節中，會在選取的元素後面插入清單項目。

**插入的元素:**

```html
<ul class="nav"> 
   <li class="men-section"> Men Clothes</li> 
   <li class="women-section"> Women Clothes</li> 
</ul>
```

**已選取:**

`<li class="women-section">Women Shoes</li>`

選取器: `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**結果:**

在此情況下，在尾端是所選清單項目的清單後面再插入清單沒有問題。新元素會新增至與所選元素相同的位置 (相對於父元素)。

在可以記錄:

```html
<div id="wrap">
    <ul class="nav">
        <li class="men">Men Shoes </li>       <li class="women">Women Shoes</li>
    </ul>
</div>
```

之後:

```html
<div id="wrap">
    <ul class="nav">
        <li class="men">Men Shoes </li>
        <li class="women">Women Shoes</li>
    </ul>
      <ul class="nav">
        <li class="men-section">Men Clothes</li>
        <li class="women-section"> Women Clothes</li>
    </ul>
</div>
```

## 情節: 移除另一個元素前面緊鄰的元素 {#section_F193674F04F84AA593EAA1137C880EBA}

在此情節中，會刪除所選元素前面的清單項目。

**移除的元素:**

```html
<li class="men-section"> Men </li>
```

**已選取:**

`<li class="women-section">Women</li>`

選取器: `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**結果:**

元素已成功移除，因為所選取項目的類別未遭更改。

在可以記錄:

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-section">Women</li>
    </ul>
</div>
```

之後:

```html
<div id="wrap">
    <ul class="nav">
        <li class="women-section">Women</li>
    </ul>
</div>
```

## 情節: 移除另一個元素後面緊鄰的元素 {#section_F83B51BE54924FB58679D512DAF1EBB2}

在此情節中，會刪除所選元素後面的清單項目。

**移除的元素:**

```html
<li class="kids-section">Kids</li>
```

**已選取:**

`<li class="women-section">Women</li>`

選取器: `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**結果:**

元素已成功移除，因為所選取項目的類別未遭更改。移除的元素包含其父系樹狀子目錄內唯一的類別。

在可以記錄:

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-section">Women</li>
        <li class="kids-section">Women</li>
    </ul>
</div>
```

之後:

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-section">Women</li>
    </ul>
</div>
```

## 情節: 移除所選的元素 {#section_1989CF1E2C344CC5963084ED83C18F9C}

在此情節中，會刪除所選的清單項目。

**移除的元素:**

```html
<li class="women-shoes">Women</li>
```

**已選取:**

`<li class="women-shoes">Women</li>`

選取器: `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**結果:**

成功移除元素。

在可以記錄:

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-shoes">Women</li>
    </ul>
</div>
```

之後

```html
<div id="wrap">
    <ul class="nav">
       <li class="men-section">Men</li>
    </ul>
</div>
```

## 情節: 重新命名所選元素的類別 {#section_79D244C588BA452DB8E433D82B7F63EA}

在此情節中，會變更所選清單項目的類別。

**變更的元素:**

```html
<li class="women-section">Women</li>
```

**已選取:**

`<li class="women-section">Women</li>`

選取器: `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**結果:**

無法重新命名元素類別，因為找不到 `class`。

在可以記錄:

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-section">Women</li>
    </ul>
</div>
```

之後 (理想結果):

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-shoes">Women</li>
    </ul>
</div>
```
