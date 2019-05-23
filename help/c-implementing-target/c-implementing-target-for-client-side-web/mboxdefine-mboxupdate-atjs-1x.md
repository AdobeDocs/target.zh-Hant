---
description: 'at. js的mboxDefine()和mboxUpdate()函數的相關資訊。 '
keywords: adobe.target.notification;元素;選取器;通知;擴充功能
seo-description: 適用於Adobe Target at. js JavaScript程式庫的mboxDefine()和mboxUpdate()函數的相關資訊。
seo-title: 適用於Adobe Target at. js JavaScript程式庫的mboxDefine()和mboxUpdate()函數的相關資訊。
solution: Target
subtopic: 快速入門
title: mboxDefine() 和 mboxUpdate() - at.js 1.x
topic: Standard
translation-type: tm+mt
source-git-commit: 126f62d8966beb8157f54f87cf68b092fe976c51

---


# mboxDefine() 和 mboxUpdate() - at.js 1.x

在Adobe Target中定義及更新mbox。

>[!NOTE]
>
>這些函數僅適用於 at.js 1.*x* 版。在. js2.x發行時停用這些函數。如果與at. js2.x搭配使用，這些函數會傳回預設內容。

`mboxDefine()` 和 `mboxCreate()` 已與 HTML DIV 元素綁定，這些元素應會顯示選件。這些 HTML DIV 元素應該具有 `mboxDefault` 類別。如果 HTML 元素沒有附加此類別，您會看到一些顯著的閃爍。

## mboxDefine {#section_134BAAE8EE9D49D8BAFEA5E7EAB93BA7}

在 nodeId 與 mbox 名稱之間建立內部對應，但是不會執行要求。用來結合 `mboxUpdate()`。多半建置在 [!DNL at.js] 中，以便從 [!DNL mbox.js] 移轉至 [!DNL at.js]。

## mboxUpdate {#section_D20B3E551884452A996305C12D5959D5}

執行要求並套用選件至 `nodeId` () 中的 `mboxDefine()` 所識別的元素。也可用來更新 `mboxCreate` 起始的 mbox。多半建置在 [!DNL at.js]，以便於從 [!DNL mbox.js] 到 [!DNL at.js] 的轉變。`mboxDefine()`/ `mboxUpdate()` 可能會由 [adobe. target. getOffer()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffer.md) 和 [adobe. target. applyOffer()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-applyoffer.md) 取代。

## 範例 {#section_9C1E75D9E4BA4DC7879D2B69877EB01A}

```
<div id="someId" class="mboxDefault"></div> 
<script> 
 mboxDefine('someId','mboxName','param1=value1','param2=value2'); 
 mboxUpdate('mboxName','param3=value3','param4=value4'); 
</script>
```
