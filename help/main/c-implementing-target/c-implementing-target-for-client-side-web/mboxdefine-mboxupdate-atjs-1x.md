---
keywords: mboxDefine;mboxdefine;mbox 定義;mboxUpdate;mboxupdate;mbox 更新;at.js;函數;函數
description: 使用mboxDefine()和mboxUpdate()函式進行Adobe [!DNL Target] at.js JavaScript庫以定義或更新mbox。 (at.js 1.x)
title: 如何使用mboxDefine()和mboxUpdate()函式？
feature: at.js
role: Developer
exl-id: 48261be0-c4d0-4961-9712-ef7e0d2cb1c0
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 75%

---

# mboxDefine() 和 mboxUpdate() - at.js 1.x

在 Adobe Target 中定義和更新 mbox。

>[!NOTE]
>
>這些函數僅適用於 at.js 1.*x* 版。自 at.js 2.x 版起已棄用這些函數。如果與 at.js 2.x 搭配使用，這些函數會傳回預設內容。

`mboxDefine()` 和 `mboxCreate()` 已與 HTML DIV 元素綁定，這些元素應會顯示選件。這些 HTML DIV 元素應該具有 `mboxDefault` 類別。如果 HTML 元素沒有附加此類別，您會看到一些顯著的閃爍。

## mboxDefine {#section_134BAAE8EE9D49D8BAFEA5E7EAB93BA7}

在 nodeId 與 mbox 名稱之間建立內部對應，但是不會執行要求。用來結合 `mboxUpdate()`。內置 [!DNL at.js] 主要是為了緩解 [!DNL mbox.js] （現在不建議使用） [!DNL at.js]。

## mboxUpdate {#section_D20B3E551884452A996305C12D5959D5}

執行要求並套用選件至 `nodeId` () 中的 `mboxDefine()` 所識別的元素。也可用來更新 `mboxCreate` 起始的 mbox。內置 [!DNL at.js] 主要是為了緩解 [!DNL mbox.js] （現在不建議使用） [!DNL at.js]。 可使用選取器選項將 `mboxDefine()`/ `mboxUpdate()` 取代為 [adobe.target.getOffer()](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffer.md) 和 [adobe.target.applyOffer()](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-applyoffer.md) 

## 範例 {#section_9C1E75D9E4BA4DC7879D2B69877EB01A}

```javascript
<div id="someId" class="mboxDefault"></div> 
<script> 
 mboxDefine('someId','mboxName','param1=value1','param2=value2'); 
 mboxUpdate('mboxName','param3=value3','param4=value4'); 
</script>
```
