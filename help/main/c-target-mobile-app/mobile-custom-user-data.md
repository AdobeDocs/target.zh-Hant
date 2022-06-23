---
keywords: 行動應用程式;行動應用程式傳送資料;target 行動應用程式;行動自訂使用者資料;行動應用程式自訂資料
description: 瞭解如何發送有關位置或用戶的其他資訊以Adobe [!DNL Target] 作為名稱 — 值對，幫助您構建自定義訪問群體。
title: 如何在iOS應用中發送自定義用戶資料？
feature: Implement Mobile
role: Developer
exl-id: c64219ec-8d60-4d05-b2b8-103e8ffcaefc
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 90%

---

# iOS - 傳送自訂使用者資料

您可以以名稱值組的方式將關於位置或使用者的其他資訊傳送至 Target。

此資訊可用來建立自訂對象 (例如，大於 25000 英里的使用者) 以及在報表中使用。

您可以使用 Target 呼叫傳送兩個類型的參數:

* mbox 參數

   Mbox 參數不會在工作階段間持續保存。
* 設定檔參數

   設定檔參數會儲存在訪客設定檔中，並且在工作階段間持續保存。Mbox 參數不會持續保存。雖然會保留一些金鑰，設定檔和 mbox 參數均可以是自訂機碼值組。

儘管有一些保留的金鑰，設定檔和 mbox 參數均可以包含自訂機碼值組。

1. 建立字典。

   首先，使用您傳送以傳遞至 Target 的值建立字典。為了方便，請在 `welcomeMessageCampaign` 方法內新增此項目，因此您不需擔心範圍。

   下列是樣本字典。您可以在 `(void)welcomeMessageCampaign` 內複製貼上這個。在此範例中，`userLevel` 和 `userMiles` 之類金鑰的值會加上硬式編碼。一般來說，您會傳入對應的變數。

   ```
   NSDictionary *targetParams = [[NSDictionary alloc] initWithObjectsAndKeys: 
                                 @"platinum",@"userLevel", 
                                 @26500,@"userMiles", 
                                 @"1067007",@"entity.id", 
                                 @"dealsapp.qa", @"host", 
                                 @"fashion",@"entity.categoryId", 
                                 @"millenial", @"profile.persona", 
                                 @"cohort_5", @"profile.cohort", 
                                 nil];
   ```

   * 具有 profile 字首的金鑰 (例如，`profile.persona`) 會儲存在使用者的設定檔上。

      您可以在不同活動和通道間使用這些設定檔屬性。

   * 沒有任何字首的金鑰 (例如，`userMiles`) 為 mbox 參數。

      這些參數只能在工作階段期間使用。

   * 具有字首 entity 的金鑰 (例如，`entity.category.id`) 則用於產品建議。

1. 驗證資料。
   1. 在應用程式 `didFinishLaunchingWithOptions` 中，取消註解或新增 `[ADBMobile setDebugLogging:YES];`。

      這會列印詳細的偵錯記錄。
   1. 建置應用程式。
   1. 驗證參數已傳入目標呼叫中。

      在您的偵錯主控台搜尋您的目標位置名稱。您將看到對 `YOUR-CLIENT-CODE.tt.omtrdc.net` 的呼叫包含剛才傳入的所有參數。

      ![](assets/mobile-debug.png)
   您可以在 Target Standard 中使用這些參數來建立對象和限制，或鎖定內容的顯示。
