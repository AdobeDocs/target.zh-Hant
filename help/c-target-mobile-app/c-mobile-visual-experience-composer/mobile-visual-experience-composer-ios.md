---
description: Adobe Target Mobile Visual Experience Composer(CMS)可讓開發人員在其iOS行動應用程式上多次設定，並讓行銷人員使用行動應用程式CMS的功能。
keywords: 行動應用程式CMS；行動視覺體驗撰寫器；行動體驗撰寫器選項；設定；ios；apple
seo-description: Adobe Target Mobile Visual Experience Composer(CMS)可讓開發人員在其iOS行動應用程式上多次設定，並讓行銷人員使用行動應用程式CMS的功能。
seo-title: iOS - 設定行動應用程式
solution: Target
title: iOS - 設定行動應用程式
topic: Standard
uuid: 6db4f06a-d8f4-4192-af6f-917594e721e6
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# iOS - 設定行動應用程式{#ios-set-up-the-mobile-app}

Adobe Target Mobile App Visual Exposer(CMS)可讓開發人員在其iOS行動應用程式上多次設定，並讓行銷人員使用行動應用程式CMS的功能。

如需啓用Adobe Target CMS擴充功能的詳細資訊，請參閱 [Adobe Experience Platform Mobile SDK](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-target-vec) 中的Adobe *Target- Visual Experience Composer*。

## 加入Mobile SDK和Target程式庫 {#sdk-library}

1. 新增pod」 [!DNL Podfile]`ACPTargetVEC`，將程式庫新增至您的專案。
1. 在 XCode 中開啟 Objective-C 應用程式專案。
1. 前往您的專案建立設定，如果尚未設定，請將「永遠嵌入快速標準程式庫」設定為「是」。
1. 在專案建置設定中找出「其他連結器旗標」(Other linker flags)，然後新增 `$(inherited)` (如果不存在的話)。
1. 針對 objective-C 專案 - 建立 Swift 檔案以建立橋接標頭。它會為您設定 Swift 應用程式環境。
1. 新增深層連結處理常式:

   1. 在您的應用程式專案設定中，按一下**[!UICONTROL 「資訊」]**。
   1. 在 **[!UICONTROL 「URL類型]**」下方，按一下三角形以開啓它，然後按一下加號以新增欄位。
   1. 新增下列資訊:

      * 識別碼: `com.adobe.sdktest`
      * URL配置： `vectester`
      * 角色: 編輯者
   1. 按一下離開您的應用程式專案設定 &gt; **[!UICONTROL 「一般」]**。
   1. 按一下返回您的應用程式專案設定 &gt; **[!UICONTROL 「資訊」]，確保已儲存您的設定。**

      有了範例 URL 類型，您應用程式的 URL 配置將會:

      ```
      vectester://com.adobe.sdktest
      ```


1. 在 XCode 中，開啟 [!DNL AppDelegate] 檔案。
1. 在檔案頂端，在匯入的結尾新增下列文字行:

   `#import "ACPTargetVEC.h"`

   如果您正在使用 Swift，請新增以下文字行:

   `import ACPTargetVEC`

1. 在您的 [!DNL AppDelegate] 檔案中，將下列行加入 `AppDelegate::application:didFinishLaunchingWithOptions:`。如果未定義委派函式，請建立該函式，並針對 Objective-C 或 Swift 應用程式個別加入下列行:

   ```
   // CONFIGURATION LINE FOR OBJECTIVE C ONLY (Skip any framework which is not applicable for you): 
   [ACPCore configureWithAppId:@"YOUR_ADOBE_LAUNCH_APP_ID"]; 
   [ACPCore setLogLevel:ACPMobileLogLevelDebug]; 
   [ACPLifecycle registerExtension]; 
   [ACPIdentity registerExtension]; 
   [ACPUserProfile registerExtension]; 
   [ACPTarget registerExtension];
   
   [ACPTargetVEC registerExtension];
   [ACPCore start:^{
        [ACPCore lifecycleStart:nil];
   }];
   
   // CONFIGURATION LINE FOR SWIFT ONLY: 
   ACPCore.configure(withAppId: "YOUR_ADOBE_LAUNCH_APP_ID") 
   ACPCore.setLogLevel(ACPMobileLogLevel.debug) 
   ACPLifecycle.registerExtension() 
   ACPIdentity.registerExtension() 
   ACPUserProfile.registerExtension() 
   ACPTarget.registerExtension() 
   
   ACPTargetVEC.registerExtension() 
   
   ACPCore.start {
     ACPCore.lifecycleStart(nil)
   }
   ```

   例如，此方法應該類似以下範例:

   ```
   // EXAMPLE OVERRIDE METHOD FOR OBJECTIVE C ONLY: 
   - (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions { 
        // Override point for customization after application launch. 
       [ACPCore configureWithAppId:@"YOUR_ADOBE_LAUNCH_APP_ID"]; 
       [ACPCore setLogLevel:ACPMobileLogLevelDebug]; 
       [ACPLifecycle registerExtension]; 
       [ACPIdentity registerExtension]; 
       [ACPUserProfile registerExtension]; 
       [ACPTarget registerExtension]; 
   
       [ACPTargetVEC registerExtension]; 
   
       [ACPCore start:nil]; 
       [ACPCore lifecycleStart:nil]; 
   
      return YES; 
   } 
   
   // EXAMPLE OVERRIDE METHOD FOR SWIFT ONLY: 
   func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey : Any]? = nil) 
   { 
       ACPCore.configure(withAppId: "YOUR_ADOBE_LAUNCH_APP_ID") 
       ACPCore.setLogLevel(ACPMobileLogLevel.debug) 
       ACPLifecycle.registerExtension() 
       ACPIdentity.registerExtension() 
       ACPUserProfile.registerExtension() 
       ACPTarget.registerExtension() 
   
       ACPTargetVEC.registerExtension() 
   
       ACPCore.start(nil) 
       ACPCore.lifecycleStart(nil)
   
       return true 
   
   }
   ```

1. 將下列行加入 `AppDelegate:application:openURL`。如果未定義委派函式，請建立該函式，並加入下列行。

   ```
   // URL HANDLER LINE FOR OBJECTIVE C ONLY: 
   [ACPTargetVEC handleDeepLink:url];
   
   // URL HANDLER LINE FOR SWIFT ONLY: 
   ACPTargetVEC.handleDeepLink(url)
   ```

   例如，此方法應該類似以下範例:

   ```
   // EXAMPLE OVERRIDE METHOD FOR OBJECTIVE C ONLY:
   -  (BOOL)application:(UIApplication *)application openURL:(NSURL *)url options:(NSDictionary<NSString *, id> *)options {
    [ACPTargetVEC handleDeepLink:url];
    return YES;
   }
   
   // EXAMPLE OVERRIDE METHOD FOR SWIFT ONLY:
   func application(_ app: UIApplication, open url: URL, options: [UIApplication.OpenURLOptionsKey : Any] = [:]) -> Bool {
      ACPTargetVEC.handleDeepLink(url)
      return true;
   }
   ```

1. 建立並執行您的應用程式，並使用它來測試Mobile App CMS功能。

## 在行動應用程式上設定Target檢視 {#views}

Adobe Mobile SDK 公開一種新方法，供開發人員在每次呈現新檢視時觸發。請參閱一般准則，瞭解如何正確插入iOS應用程式的Target檢視API呼叫。在 iOS 中，所有「目標檢視」都是按它們出現的 `UIViewController` 所定義。因此，不同於 Android，`TargetViews` 的插入僅限於下列呼叫。

Adobe Mobile App CMS Extension會根據子類別的類別名稱，自動產生您 `UIViewControllers` 在Mobile App `UIViewController`CMS架構中互動的名稱。如果您要覆寫這些名稱，可以在其中呼叫下列 `viewWillAppear` 方法 `ViewController`。

```
// TARGET VIEW LINE FOR OBJECTIVE C ONLY 
[ACPTargetVEC setTargetView:@"exampleViewController"]; 
   
// TARGET VIEW LINE FOR SWIFT ONLY 
ACPTargetVEC.setTargetView("exampleViewController")
```

Adobe Mobile SDK 也公開一種替代方法，供開發人員在執行階段鎖定自訂檢視。身為開發人員，您必須確保檢視已命名唯一名稱。請先呼叫下列方法，再將檢視新增 `superview`至：

```
// EXAMPLE TARGET VIEW FOR A CUSTOM VIEW IN OBJECTIVE C 
CustomPopupView *popupView = [[CustomPopupView alloc] initWithFrame:CGRectMake(0, 0, 300, 200)]; 
[ACPTargetVEC setTargetView:@"myCustomPopupView" forView:popupView];

// EXAMPLE TARGET VIEW FOR A CUSTOM VIEW IN SWIFT 
let popupView = CustomPopupView.init(frame: CGRect(x: 0, y: 0, width: 300, height: 200)) 
ACPTargetVEC.setTargetView("myCustomPopupView", for: popupView)
```

## 設定描述檔參數和其他全域參數 {#parameters}

我們現在支援設定每個API呼叫中傳遞的全域參數，以及將mbox/檢視參數傳遞至對應檢視。

參數包括:

* mbox/檢視參數
* 設定檔參數
* 產品參數
* 訂單參數

**全域參數支援:**

```
//For Objective-c 
NSDictionary *mboxParams = @{@"mboxparam1":@"mboxvalue1"}; //mbox or view params 
NSDictionary *profileParams = @{@"profilekey1":@"profilevalue1"}; //profile params 
  
ACPTargetProduct *product = [ACPTargetProduct targetProductWithId:@"1234" categoryId:@"furniture"]; 
ACPTargetOrder *order = [ACPTargetOrder targetOrderWithId:@"12343" total:@(123.45) purchasedProductIds:@[@"100",@"200"]]; 
ACPTargetParameters *targetParams = [ACPTargetParameters targetParametersWithParameters:mboxParams 
                                                                      profileParameters:profileParams 
                                                                                product:product 
                                                                                  order:order]; 
[ACPTargetVEC setGlobalRequestParameters:targetParams];

//For Swift 
var mboxParams = ["mboxparam1":"mboxvalue1"] 
var profileParams = ["profilekey1":"profilevalue1"] 
var product : ACPTargetProduct = ACPTargetProduct.init(id: "1234", categoryId: "furniture") 
var order : ACPTargetOrder = ACPTargetOrder.init(id: "12345", total: 123.45, purchasedProductIds: ["100", "200"]) 
var targetParams : ACPTargetParameters = ACPTargetParameters.init(parameters: mboxParams, profileParameters: profileParams, product: product, order: order) 
ACPTargetVEC.setGlobalRequest(targetParams)
```

**傳遞下一個檢視觸發的參數:**

我們已根據預設提供一些自動檢視，例如「應用程式`AUTO_<viewControllerName>`中顯示的每個檢視控制器」。若要傳遞這些參數，您可以呼叫下列 API:

```
//For Objective-c 
NSDictionary *mboxParams = @{@"viewparam1":@"viewvalue1"}; //mbox or view params 
NSDictionary *profileParams = @{@"profilekeyforview1":@"profilevalueforview1"}; //profile params 
  
ACPTargetProduct *product = [ACPTargetProduct targetProductWithId:@"1234" categoryId:@"furniture"]; 
ACPTargetOrder *order = [ACPTargetOrder targetOrderWithId:@"12343" total:@(123.45) purchasedProductIds:@[@"100",@"200"]]; 
ACPTargetParameters *targetParams = [ACPTargetParameters targetParametersWithParameters:mboxParams 
                                                                      profileParameters:profileParams 
                                                                                product:product 
                                                                                  order:order]; 
[ACPTargetVEC setGlobalRequestParameters:targetParams];

//For Swift 
var mboxParams = ["mboxparam1":"mboxvalue1"] 
var profileParams = ["profilekey1":"profilevalue1"] 
var product : ACPTargetProduct = ACPTargetProduct.init(id: "1234", categoryId: "furniture") 
var order : ACPTargetOrder = ACPTargetOrder.init(id: "12345", total: 123.45, purchasedProductIds: ["100", "200"]) 
var targetParams : ACPTargetParameters = ACPTargetParameters.init(parameters: mboxParams, profileParameters: profileParams, product: product, order: order) 
ACPTargetVEC.setRequest(targetParams)
```

**將參數傳遞至特定檢視:**

We have seen the API trigger Views via `TargetVEC.targetView("view_name")`. 您也可以傳遞專屬於特定檢視的參數，如下所示:

```
//For Objective-c 
[ACPTargetVEC setTargetView:@"VIEW_NAME" withParameters:TARGET_PARAMS];

//FOR SWIFT 
ACPTargetVEC.setTargetView("VIEW_NAME", with: TARGET_PARAMS)
```

## 明確呼叫預先擷取API {#section_373DB4527FC649C58FBA3DF0C18C9836}

在某些情況下，您可能會想再次呼叫預先擷取 API，以重新整理快取中儲存的選件。下列已公開的 API 為:

**預先擷取選件:**

```
/** 
 * Prefetch all offers for all views in the cache. It will remove existing offers and changes for the current view will be 
 refreshed only when the view is triggered. This call happens on the main thread blocking the UI. 
 */ 
+ (void) prefetchOffers;
```

**在背景預先擷取選件:**

```
/** 
 * Prefetch all offers for all views in the cache. It will remove existing offers and changes for the current view will be 
 refreshed only when the view is triggered. This call happens on the background thread so doesn't block UI. 
 */ 
+ (void) prefetchOffersBackground;
```

