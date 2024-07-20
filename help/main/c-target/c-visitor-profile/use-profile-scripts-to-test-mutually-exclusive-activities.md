---
keywords: 設定檔指令碼；設定檔指令碼屬性；互斥活動
description: 瞭解如何使用設定檔屬性來設定Adobe [!DNL Target] 中的測試，這些測試會比較多個活動但不讓相同的訪客參與每個活動。
title: 我可以使用個人資料指令碼來測試互斥活動嗎？
feature: Audiences
exl-id: b0b23887-3339-411e-9f5c-64f9d1ba778c
source-git-commit: 34db233e0790f8ef04309c3f4b5acd12b7cdd5ad
workflow-type: tm+mt
source-wordcount: '708'
ht-degree: 74%

---

# 使用用來測試互斥活動的設定檔指令碼

您可以在[!DNL Adobe Target]中使用設定檔屬性來設定比較兩個或多個活動的測試，但不讓相同的訪客參與每個活動。

測試互斥的活動可避免某個活動中的訪客影響到其他活動的測試結果。當訪客同時參與多個活動時，很難判斷正提升或負提升是否來自訪客在某個活動中的體驗，或者，多個活動之間的互動是否影響一個或多個活動的結果。

例如，您可以測試您電子商務系統的兩個區域。您可能會想要測試，讓您的「加入購物車」按鈕變成紅色而非藍色。 您也想要測試一套新的結帳程序，以將結帳的程序從五個步驟減為兩個步驟。如果兩個活動都有相同的成功事件（完成購買），就很難判斷紅色按鈕是否會改善轉換，或是這些相同的轉換是否也因改善結帳程式而增加。 透過將測試分成互斥的活動，您可以單獨測試每個變更。

使用下列其中一個設定檔指令碼時，請注意下列資訊:

* 設定檔指令碼必須在活動啟動之前執行，而指令碼在活動期間必須保持不變。
* 此技巧可減少活動中的流量量，而這可能需要活動執行更長的時間。 當預估活動的持續時間，您必須考量此事實。

## 設定兩個活動

如果要將訪客分組，讓各組看到不同的活動，則您必須建立設定檔屬性。描述檔屬性可將訪客分到兩個或多個群組中的其中一個群組。若要設定稱為 twogroups 的描述檔屬性，您可以建立以下指令碼:

```javascript
if (!user.get('twogroups')) { 
    var ran_number = Math.floor(Math.random() * 100); 
    if (ran_number <= 49) { 
        return 'GroupA'; 
    } else { 
        return 'GroupB'; 
    } 
}
```

* `if (!user.get('twogroups'))` 決定了 *twogroups* 描述檔屬性是否設定為目前訪客。如果他們是目前訪客，則無需採取任何進一步的動作。

* `var ran_number=Math.floor(Math.random() *100)` 會宣告名稱為 ran_number 的新變數，將值設為 0 到 1 之間的隨機小數，然後乘以 100 並無條件捨去，以建立一個 100 (0-100) 的範圍，這很適合用來指定看到此活動的訪客百分比。

* `if (ran_number <= 49)` 開始了決定訪客會屬於哪個群組的常式。如果傳回的數字是 0-49，那麼此位訪客會被指定至 GroupA。如果該數字是 50-100，那麼此位訪客會被指定至 GroupB。群組會決定訪客可看到的活動。

建立設定檔屬性之後，請設定第一個活動，要求使用者設定檔引數`user.twogroups`符合為GroupA指定的值，以目標定位所需母體。

>[!NOTE]
>
>在頁面上方的位置選擇一個 mbox。此程式碼會判斷訪客是否體驗到活動。 只要瀏覽器會在先處理 mbox 的情況下，您便可以使用代碼來設定此值。

設定第二個促銷活動，以便使用者描述檔參數 `user.twogroups` 可以符合指定給 GroupB 的值。

## 設定三個或更多個活動

設定三個或更多個互斥活動類似於設定兩個互斥活動，但您必須變更設定檔屬性 JavaScript，為每個活動建立單獨群組，並決定哪個群組會看到哪個活動。產生隨機數字的方式有所不同，這取決於您是建立奇數個還是偶數個群組。

例如，若要建立四個群組，請使用下列 JavaScript:

```javascript
if (!user.get('fourgroups')) { 
    var ran_number = Math.floor​(Math.random() * 100); 
    if (ran_number <= 24) { 
        return 'GroupA'; 
    } else if (ran_number <= 49) { 
        return 'GroupB'; 
    } else if (ran_number <= 74) { 
        return 'GroupC'; 
    } else { 
        return 'GroupD'; 
    } 
}
```

在此範例中，用來產生隨機數字 (可將訪客指定至群組) 的算術會與只有兩個群組的情況下完全相同。若隨機產生一個小數，那麼請將它無條件捨去後取整數。

如果您建立了奇數個群組，或是 100 無法除盡的任何數字，那麼您不應該將小數無條件捨去後取整數。不將小數四捨五入的情況可讓您指定一個非整數的範圍。您可以變更此行來執行此作業:

`var ran_number=Math.floor(Math.random()*100);`

到:

`var ran_number=Math.random()*100;`

例如，若要將訪客平均放在三個群組中，請使用下列程式碼:

```javascript
if (!user.get('threegroups')) { 
    var ran_number = Math.random() * 100; 
    if (ran_number <= 32.33) { 
        return 'GroupA'; 
    } else if (ran_number <= 65.66) { 
        return 'GroupB'; 
    } else { 
        return 'GroupC'; 
    } 
}
```
