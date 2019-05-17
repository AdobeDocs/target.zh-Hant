---
description: Target 的全新 SDK 資料庫可讓開發人員只要設定一次 Android 行動應用程式，便能讓行銷人員使用行動版可視化體驗撰寫器 (VEC)。
keywords: 行動版 vec;行動版可視化體驗撰寫器;行動版體驗撰寫器選項;設定;android
seo-description: Target 的全新 SDK 資料庫可讓開發人員只要設定一次 Android 行動應用程式，便能讓行銷人員使用行動版可視化體驗撰寫器 (VEC)。
seo-title: Android - 設定行動應用程式
solution: Target
title: Android - 設定行動應用程式
topic: Standard
uuid: 39938ec2-b12e-44cf-9218-69195fba0ff7
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Android - 設定行動應用程式{#android-set-up-the-mobile-app}

Adobe Target Mobile App Visual Exposer(CMS)可讓開發人員在其Android行動應用程式上多次設定，並讓行銷人員使用行動應用程式CMS的功能。

如需啓用Adobe Target CMS擴充功能的詳細資訊，請參閱 [Adobe Experience Platform Mobile SDK](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-target-vec) 中的Adobe *Target- Visual Experience Composer*。

## 加入Mobile SDK和Target程式庫 {#sdk-library}

1. 如需 SDK V5 初始化的相關資訊，請參閱[初始化 SDK 和設定追蹤](https://aep-sdks.gitbook.io/docs/getting-started/initialize-the-sdk)。
1. 將下列行新增至「相依性」區段:

   ```
   implementation 'com.adobe.marketing.mobile:target-vec:1.+'
   ```

1. 行動應用程式CMS需要將下列的人工水印納入為相依性 `build.gradle`。

   ```
    implementation 'com.google.code.gson:gson:2.8.2'
    implementation 'android.arch.lifecycle:extensions:1.1.1'
    implementation('io.github.sac:SocketclusterClientJava:1.7.5')
    implementation 'com.android.support:support-annotations:28.0.0'
    implementation 'com.android.support:support-compat:28.0.0'
    implementation 'com.android.support:design:28.0.0'
   ```

1. 在 `AndroidManifest.XML` 檔案中新增意圖篩選，為Mobile App CMS編寫選擇唯一的深層連結配置(例如) `[sdkbetabus://com.adobe.sdkbetabus](sdkbetabus://com.adobe.sdkbetabus)`：

   ```
   <activity 
       android:name=".listing.MoviesListingActivity" 
       android:launchMode="singleTask"> 
       <intent-filter> 
           <action android:name="android.intent.action.VIEW" /> 
   
           <category android:name="android.intent.category.DEFAULT" /> 
           <category android:name="android.intent.category.BROWSABLE" /> 
   
           <data 
               android:host="com.adobe.sdkbetabus" 
               android:scheme="sdkbetabus" /> 
       </intent-filter> 
   </activity>
   ```

1. 前往您的行動專案，並在 `Application::onCreate override` 結尾處插入下列行:

   ```
   public class SDKTest extends MultiDexApplication { 
   
       @Override 
       public void onCreate() { 
           /* Put Your App's implementation */ 
           MobileCore.setApplication(this); 
           MobileCore.setLogLevel(LoggingMode.DEBUG); 
           MobileCore.configureWithAppID("YOUR_ADOBE_LAUNCH_APP_ID"); 
   
           ... 
           try { 
               TargetVEC.registerExtension(); //Single line code to initialize TargetVEC
               Target.registerExtension();
               Identity.registerExtension();
               Lifecycle.registerExtension();
               Signal.registerExtension();
               MobileCore.start(new AdobeCallback () {
                  @Override
                  public void call(Object o) {
                     MobileCore.configureWithAppID("launch-EN4e833d644d1949e39e985ddad4f52bd4-development");
                  }
               });
           } catch (InvalidInitException e) { 
             .. 
           }
       }
   
   /* Rest of Application test goes here ... */
   ```

1. 如果您的建置無法正常運作，請檢閱以下提供的專案範例是否為立即可用，並檢閱以下位置的變更:

   1. `Application::OnCreate override`
   1. `AndroidManifest.XML`
   1. `build.gradle` Android應用程式

## 在行動應用程式上設定Target檢視 {#views}

Adobe Mobile SDK 公開一種新方法，供開發人員在每次呈現新檢視時觸發。作為開發人員，您必須確保檢視已命名唯一名稱，而且 `targetView` 呼叫位於 UI 主要執行緒上。在本節中，我們將先示範如何使用兩種不同的展示應用程式插入這些呼叫，並討論如何正確插入適用於任何Android應用程式的Target檢視API呼叫。

>[!NOTE]
>
>如果未觸發， `targetView function` 則CMS擴充功能會嘗試從Android活動中識別「檢視」。對於沒有動態檢視的應用程式，這可以是選用步驟。

可以使用函數呼叫觸發「目標檢視」。任何定位參數可選擇性地隨檢視提供。

```
public class TargetVEC { 
   
   /** 
    * Marks a view hierarchy for editing in Mobile App VEC.  Call must insert when the view hierarchy 
    * is memory and committed to being shown, but not yet shown on the screen. 
    * 
    * @param viewName the unique Target View Name 
    */ 
   public static void targetView(String viewName); 
  
  /** 
   * Trigger Target view 
   * Triggering a Target view may cause Target offers to be applied on the current container component. 
   * Note that Target offers are applied from local Target cache, so flicker should be negligible. 
   * 
   * @param viewName Mandatory Target View name, which must be unique at app level 
   * @param parameters Parameters to be included in the next Target call 
   */ 
  
    public static void targetView(String viewName, TargetParameters parameters); 
}
```

我們第一個專案範例是簡單的匯流排排程應用程式的模型。若要設定此應用程式以用於Mobile App CMS：

1. 在 Android Studio 中開啟專案，該專案包含封裝子目錄 `build.gradle` 中的 `BusBooking` 檔案。
1. 在 `DemoApplication::OnCreate` 方法中，新增 `TargetVEC.registerExtension()` 以註冊 Target VEC 擴充功能以及其他擴充功能。
1. 建立並執行應用程式
1. 若要進入Mobile App CMS編寫模式，請使用 [!DNL sdkbetabus://com.adobe.sdkbetabus] 作為其URL配置的格式，然後開啓裝置上產生的深層連結(請參閱下面的指示)。

透過這個簡單的匯流排預訂應用程式，我們使用與活動生命週期相關聯之所有自動產生的「目標檢視」。此外，我們藉由在點擊隱藏按鈕 (螢幕上的商品影像) 時，在動態新增的自訂檢視元素上，呼叫「目標檢視 API」來示範 API 的靈活性。這個新「目標檢視」的實作方法是透過在 `OfferDetailsActivity.java:40` 的程式碼中插入 API 呼叫。點擊隱藏按鈕時，會觸發名為 &quot;SURPRISE_VIEW&quot; 的新「目標檢視」事件，讓行銷人員可以更精確地鎖定應用程式體驗的變更作為目標。

鎖定動態檢視插入作為目標:

```
package com.adobe.target.examples.bus; 
   
import android.app.DialogFragment; 
import android.os.Bundle; 
import android.os.Handler; 
import android.support.v7.app.AppCompatActivity; 
import android.support.v7.widget.Toolbar; 
import android.view.View; 
import android.view.ViewGroup; 
import android.widget.LinearLayout; 
import android.widget.Toast; 
   
import com.adobe.target.mobile.TargetVEC; 
   
/** 
 * This activity class is responsible to show offer details 
 */ 
public class OfferDetailsActivity extends AppCompatActivity { 
    @Override 
    protected void onCreate(Bundle savedInstanceState) { 
        super.onCreate(savedInstanceState); 
        setContentView(R.layout.activity_offer_details); 
        setUpToolBar(); 
        final Handler mainHandler = new Handler(getApplicationContext().getMainLooper()); 
   
        final View surpriseView = getLayoutInflater().inflate(R.layout.suprise_layout, 
                (ViewGroup) findViewById(android.R.id.content), false); 
   
        final View imagePresentView = this.findViewById(R.id.image_present); 
        final LinearLayout currentLayout = this.findViewById(R.id.offer_layout); 
   
        imagePresentView.setOnClickListener(new View.OnClickListener() { 
            @Override 
            public void onClick(View v) { 
                Toast.makeText(getApplicationContext(),"Surprise!", Toast.LENGTH_SHORT).show(); 
                mainHandler.post(new Runnable() { 
                    @Override 
                    public void run() { 
                        currentLayout.addView(surpriseView); 
                        TargetVEC.targetView("SURPRISE_VIEW"); 
                        currentLayout.invalidate(); 
                    } 
                }); 
                // One-shot.  Remove clicker afterwards. 
                imagePresentView.setOnClickListener(null); 
            } 
        }); 
    } 
   
    private void setUpToolBar() { 
        Toolbar toolbar = findViewById(R.id.toolbar); 
        toolbar.setNavigationIcon(R.drawable.abc_ic_ab_back_material); 
        toolbar.setTitle("Buy 1 Get 1"); 
        toolbar.setNavigationOnClickListener(new View.OnClickListener() { 
            @Override 
            public void onClick(View v) { 
                onBackPressed(); 
            } 
        }); 
    } 
   
    @Override 
    protected void onPause() { 
        super.onPause();
        MobileCore.lifecyclePause();
    } 
   
    @Override 
    protected void onResume() { 
        super.onResume();
        MobileCore.lifecycleStart(null);
    } 
}
```

## 設定描述檔參數和其他全域參數 {#parameters}

我們現在支援設定將傳入每個API呼叫中的全域參數，以及將mbox/檢視參數傳遞至對應檢視。

參數包括:

* mbox/檢視參數
* 設定檔參數
* 產品參數
* 訂單參數

**全域參數支援:**

```
Map<String, String> mboxParams = new HashMap<>();  //Mbox or view params 
mboxParams.put("mboxparam1", "mboxvalue1"); 
Map<String, String> profileParams = new HashMap<>();  //Profile params 
profileParams.put("profilekey1", "profilevalue1"); 
  
TargetVEC.setGlobalRequestParameters(new TargetParameters.Builder() 
        .parameters(mboxParams) 
        .profileParameters(profileParams) 
        .product(new TargetProduct("1234", "furniture")) 
        .order(new TargetOrder("12343", 123.45, Arrays.asList("100", "200"))) 
        .build());
```

**傳遞下一個檢視觸發的參數:**

我們已根據預設提供一些自動檢視，例如「`AUTO_<activity|fragment name>`應用程式中的每個活動和片段」。若要傳遞這些參數，您可以呼叫下列 API:

```
Map<String, String> mboxParams = new HashMap<>();  //Mbox or view params 
mboxParams.put("viewKey1", "viewparam1"); 
Map<String, String> profileParams = new HashMap<>();  //Profile params 
profileParams.put("profilekeyforview1", "profilevalueforview1"); 
  
TargetVEC.setRequestParameters(new TargetParameters.Builder() 
        .parameters(mboxParams) 
        .profileParameters(profileParams) 
        .product(new TargetProduct("1234", "furniture")) 
        .order(new TargetOrder("12343", 123.45, Arrays.asList("100", "200"))) 
        .build());
```

**傳遞參數至特定檢視：**

We have seen the API trigger Views via `TargetVEC.targetView("view_name")`. 您也可以傳遞專屬於特定檢視的參數，如下所示:

```
Map<String, String> profileParams = new HashMap<>(); 
profileParams.put("surprisekey1", "surprisevalue1");  //ProfileParams 
TargetVEC.targetView("SURPRISE_VIEW", 
        new TargetParameters.Builder() 
                .profileParameters(profileParams) 
                .product(new TargetProduct("3354", "kitchen")) 
                .build());
```

## 明確呼叫預先擷取API {#section_2D02B74558474D3BA9F25E4D25E7C7E3}

在某些情況下，您可能會想再次呼叫預先擷取 API，以重新整理快取中儲存的選件。下列已公開的 API 為:

* **prefetchOffers**

   ```
   /** 
    * Prefetch Target offers. 
    * Note that calling this will pre-hide the current layout, until Target offers are prefetched 
    * and applied to currently visible Target views, possibly causing flicker, thus it's recommended 
    * to call this method inside the containing component's onCreate() lifecycle method 
    */ 
   public static void prefetchOffers();
   ```

* **prefetchOffersBackground**

   ```
   /** 
    * Prefetch Target offers in the background. 
    * Note, that in contrast to prefetchOffers(), calling this method will NOT pre-hide 
    * the current layout, instead prefetched Target offers will be only be cached and will subsequently 
    * be applied as Target Views are being triggered. 
    */ 
   public static void prefetchOffersBackground();
   ```

