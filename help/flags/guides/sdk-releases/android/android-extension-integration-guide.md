---
title: Android整合指南的旗標擴充功能
description: 瞭解如何在Android上將Flags擴充功能與Adobe Experience Platform Mobile SDK整合。
badge: label="Beta" type="Informative"
hide: true
exl-id: 683ef4d4-e637-4b7b-b694-689c7e65a99e
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
source-git-commit: c1fafcfcd7d5d22781abdd10e6eb3c2b84136c2d
workflow-type: tm+mt
source-wordcount: '1379'
ht-degree: 4%
---
# 標示Android的擴充功能 {#android-extension-integration-guide}

本指南說明如何在Android上將Flags擴充功能與Adobe Experience Platform Mobile SDK整合。

## 先決條件 {#prerequisites}

在實作Flags擴充功能之前，請確定您擁有：

* 在[Adobe Experience Platform Data Collection](https://experience.adobe.com/#/data-collection)中設定的行動屬性
* 在您的行動屬性中安裝並設定的Adobe Flags擴充功能
* Adobe Experience Cloud組織ID
* 在行動屬性中設定的Edge Network資料流，用於接收曝光度分析
* Android API 21 (Android 5.0 Lollipop)或更新版本
* 行動核心3.6.0或更新版本（`sdk-bom` 3.17.0或更新版本所包含）

## 擴充功能相依性 {#extension-dependencies}

Flags擴充功能需要下列Adobe Experience Platform擴充功能：

| 延伸 | 說明 | 必要 |
|---|---|---|
| [行動核心](https://developer.adobe.com/client-sdks/home/base/mobile-core/) | 提供設定、事件處理和SDK初始化 | 是 |
| [生命週期](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/) | 應用程式移至前景或背景時製作報表 | 是 |
| [Edge Network](https://developer.adobe.com/client-sdks/edge/edge-network/) | 將曝光度分析傳送至Adobe Experience Platform | 是 |
| Edge Network的[身分](https://developer.adobe.com/client-sdks/edge/identity-for-edge-network/) | 提供用於將使用者指派給變體的身分 | 是 |

請確認這些擴充功能已安裝在您的資料收集行動屬性中，並包含在您的應用程式相依性中。

## 在資料收集中設定標幟副檔名 {#configure}

### 安裝擴充功能 {#install-extension}

1. 登入[Adobe Experience Platform資料彙集](https://experience.adobe.com/#/data-collection)。

1. 選取&#x200B;**[!UICONTROL 標籤]**&#x200B;功能表，然後選擇您的行動裝置屬性。

1. 瀏覽至&#x200B;**[!UICONTROL 擴充功能]** > **[!UICONTROL 目錄]**。

1. 搜尋&#x200B;**[!DNL Adobe Flags]**&#x200B;並選取&#x200B;**[!UICONTROL 安裝]**。

   ![](../assets/extension-install.png)

1. 設定擴充功能設定：

   * **[!UICONTROL 沙箱]**：包含您的Flags設定的Adobe Experience Platform沙箱。
   * **[!UICONTROL 應用程式識別碼]**：旗標中的應用程式識別碼。

1. 選取&#x200B;**[!UICONTROL 儲存]**。

1. 依照[發佈程式](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview)更新您的設定。

### 取得環境檔案ID {#environment-file-id}

1. 在您的行動屬性中，瀏覽至&#x200B;**[!UICONTROL 環境]**。

1. 在您選取環境的&#x200B;**[!UICONTROL 安裝]**&#x200B;欄中選取方塊圖示。

   ![](../assets/extension-install-2.png)

1. 在&#x200B;**[!UICONTROL 行動安裝指示]**&#x200B;對話方塊中，複製&#x200B;**[!UICONTROL 環境檔案識別碼]**。

   ![](../assets/extension-install-3.png)

## 將Flags擴充功能新增至您的應用程式 {#add-to-app}

### 新增相依性 {#add-dependencies}

>[!IMPORTANT]
>
>Flags擴充功能不是Mobile SDK BOM的一部分。 將`<latest-version>`取代為Maven Central的最新版本。 若沒有版本，Gradle將無法解析相依性。
>
></br>
&gt;對於生產應用程式，Adobe建議使用明確版本編號，而非動態版本，例如「3.+」。 如需詳細資訊，請參閱[管理Gradle相依性](https://docs.gradle.org/current/userguide/dependency_management.html)。

將下列相依性新增至應用程式的`build.gradle.kts` (Kotlin)或`build.gradle` (Groovy)檔案：

>[!BEGINTABS]

>[!TAB Kotlin]

```kotlin
dependencies {
    // Adobe Experience Platform Mobile SDK BOM (3.17.0 or later)
    implementation(platform("com.adobe.marketing.mobile:sdk-bom:3.+"))

    // Required extensions (versions managed by the BOM)
    implementation("com.adobe.marketing.mobile:core")
    implementation("com.adobe.marketing.mobile:lifecycle")
    implementation("com.adobe.marketing.mobile:edge")
    implementation("com.adobe.marketing.mobile:edgeidentity")

    // Flags extension (not managed by the BOM; specify the version)
    implementation("com.adobe.marketing.mobile:flags:<latest-version>")
}
```

>[!TAB Groovy]

```groovy
dependencies {
    // Adobe Experience Platform Mobile SDK BOM (3.17.0 or later)
    implementation platform('com.adobe.marketing.mobile:sdk-bom:3.+')

    // Required extensions (versions managed by the BOM)
    implementation 'com.adobe.marketing.mobile:core'
    implementation 'com.adobe.marketing.mobile:lifecycle'
    implementation 'com.adobe.marketing.mobile:edge'
    implementation 'com.adobe.marketing.mobile:edgeidentity'

    // Flags extension (not managed by the BOM; specify the version)
    implementation 'com.adobe.marketing.mobile:flags:<latest-version>'
}
```

>[!ENDTABS]

### 初始化SDK {#initialize-sdk}

>[!IMPORTANT]
>
>對於生產應用程式，僅使用`LoggingMode.ERROR`。 請勿在發行版本組建中使用`DEBUG`或`VERBOSE`。

呼叫任何Flags擴充功能API之前，請先初始化`Application`類別中的Mobile SDK。 使用您行動屬性中的環境檔案ID，讓應用程式挑選您在Data Collection中發佈的旗標設定。

`MobileCore.initialize`會註冊您Gradle相依性中包含的每個Adobe擴充功能，包括Flags擴充功能。

請注意，當您使用`MobileCore.initialize`時，請勿同時呼叫`MobileCore.registerExtensions`、`MobileCore.lifecycleStart`或`MobileCore.lifecyclePause`。 系統會為您處理這些專案。

>[!BEGINTABS]

>[!TAB Kotlin]

```kotlin
import android.app.Application
import com.adobe.marketing.mobile.LoggingMode
import com.adobe.marketing.mobile.MobileCore

class MainApplication : Application() {

    override fun onCreate() {
        super.onCreate()

        MobileCore.setLogLevel(LoggingMode.ERROR)

        // Initialize with your Environment File ID from Data Collection
        MobileCore.initialize(this, "YOUR_ENVIRONMENT_FILE_ID")
    }
}
```

>[!TAB Java]

```java
import android.app.Application;
import com.adobe.marketing.mobile.LoggingMode;
import com.adobe.marketing.mobile.MobileCore;

public class MainApplication extends Application {

    @Override
    public void onCreate() {
        super.onCreate();

        MobileCore.setLogLevel(LoggingMode.ERROR);

        // Initialize with your Environment File ID from Data Collection
        MobileCore.initialize(this, "YOUR_ENVIRONMENT_FILE_ID");
    }
}
```

>[!ENDTABS]

### 註冊Application類別 {#register-application}

在`AndroidManifest.xml`中註冊您的`Application`類別：

```xml
<application
    android:name=".MainApplication"
    ... >
</application>
```

### 如果您手動註冊擴充功能 {#register-manually}

如果您的應用程式無法使用`MobileCore.initialize`並向`MobileCore.registerExtensions`註冊副檔名，請新增`Flag.EXTENSION`至清單。 使用Edge Network類別`com.adobe.marketing.mobile.edge.identity.Identity`的身分識別，而非舊版`com.adobe.marketing.mobile.Identity`。

```kotlin
import com.adobe.marketing.mobile.Edge
import com.adobe.marketing.mobile.Lifecycle
import com.adobe.marketing.mobile.MobileCore
import com.adobe.marketing.mobile.edge.identity.Identity
import com.adobe.marketing.mobile.flags.Flag

MobileCore.setApplication(this)
MobileCore.configureWithAppID("YOUR_ENVIRONMENT_FILE_ID")
MobileCore.registerExtensions(
    listOf(Lifecycle.EXTENSION, Identity.EXTENSION, Edge.EXTENSION, Flag.EXTENSION)
) { }
```

在此設定中，不會自動追蹤生命週期。 呼叫其`onPause`中每個活動的`onResume`和`MobileCore.lifecyclePause()`中的`MobileCore.lifecycleStart(null)`。 如果沒有這些呼叫，擴充功能會在應用程式於背景時持續重新整理標幟，曝光分析則會在稍後傳送。

## 評估內容 {#evaluation-context}

`FeatureEvaluationContext`保留您的標幟規則所使用的目標定位屬性。 您不會傳遞身分：每次評估時，擴充功能都會從Edge Network的身分中讀取身分。 請參閱[自訂身分](#custom-identity)。

| 方法 | 必要 | 說明 |
|---|---|---|
| `withAttributes(map)` | 否 | `Map<String, List<String>>`. 每個索引鍵都是標籤規則所使用的屬性名稱（例如，`locale`或`appVersion`）。 每個值都是目前使用者的值清單（例如，`["en_US"]`）。 |

* 每次評估都需要上下文。 如果您沒有屬性，請傳遞`FeatureEvaluationContext.builder().build()`。
* 每個產生器最多呼叫`withAttributes`一次。
* 無法變更內建的前後關聯，因此您可以在評估中重複使用它。

### 使用情況 {#evaluation-context-usage}

>[!BEGINTABS]

>[!TAB Kotlin]

```kotlin
import com.adobe.marketing.mobile.flags.FeatureEvaluationContext

val ctx = FeatureEvaluationContext.builder()
    .withAttributes(
        mapOf(
            "locale" to listOf("en_US"),
            "platform" to listOf("ANDROID")
        )
    )
    .build()
```

>[!TAB Java]

```java
import com.adobe.marketing.mobile.flags.FeatureEvaluationContext;
import java.util.Arrays;
import java.util.HashMap;
import java.util.List;
import java.util.Map;

Map<String, List<String>> attrs = new HashMap<>();
attrs.put("locale", Arrays.asList("en_US"));
attrs.put("platform", Arrays.asList("ANDROID"));

FeatureEvaluationContext ctx = FeatureEvaluationContext.builder()
        .withAttributes(attrs)
        .build();
```

>[!ENDTABS]

### 目標屬性範例 {#sample-attributes}

| 屬性 | 說明 | 範例值 |
|---|---|---|
| `locale` | 使用者的地區設定 | `["en_US"]`, `["fr_FR"]` |
| `platform` | 平台 | `["ANDROID"]` |
| `appVersion` | 應用程式版本 | `["3.0.0"]` |
| `deviceType` | 裝置類型 | `["phone"]`, `["tablet"]` |

屬性名稱和值必須符合標幟規則中使用的名稱和值。

## 自訂身分 {#custom-identity}

Flags擴充功能使用[Edge Network擴充功能](https://developer.adobe.com/client-sdks/edge/identity-for-edge-network/)的身分識別，以進行身分解析。 功能標幟可以群組在自訂身分上（例如CRM ID或忠誠度ID），以便變體拆分和分析繫結至對您的應用程式重要的身分。

編寫功能標幟時，必須在標幟UI中選取自訂身分名稱空間。 若要根據該身分評估旗標，裝置上的Edge身分`identityMap`中必須存在相同的身分，使用相符的名稱空間。 在執行階段提供Edge Network `updateIdentities` API的身分識別。

### 將自訂身分新增至身分對應 {#add-identity}

在您評估標幟之前，在功能標幟上設定的相同名稱空間下新增身分。

新增身分時，請注意下列事項：

* 名稱空間必須完全相符，包括大小寫。
* 如果名稱空間有多個身分，系統會使用標示為主要身分的身分。 否則，會使用第一個。
* 評估標幟時若缺少身分，系統會以臨時ID指派使用者，此臨時ID會在每次應用程式啟動時變更。 之後，使用者的變體即可在應用程式啟動之間變更。 在評估使用身分的旗標之前，請務必先設定身分識別。

>[!BEGINTABS]

>[!TAB Kotlin]

```kotlin
import com.adobe.marketing.mobile.edge.identity.AuthenticatedState
import com.adobe.marketing.mobile.edge.identity.Identity
import com.adobe.marketing.mobile.edge.identity.IdentityItem
import com.adobe.marketing.mobile.edge.identity.IdentityMap

val identityMap = IdentityMap()
identityMap.addItem(
    IdentityItem("1111", AuthenticatedState.AUTHENTICATED, true),
    "userCRMId" // must match the namespace configured on the feature flag
)
Identity.updateIdentities(identityMap)
```

>[!TAB Java]

```java
import com.adobe.marketing.mobile.edge.identity.AuthenticatedState;
import com.adobe.marketing.mobile.edge.identity.Identity;
import com.adobe.marketing.mobile.edge.identity.IdentityItem;
import com.adobe.marketing.mobile.edge.identity.IdentityMap;

IdentityMap identityMap = new IdentityMap();
identityMap.addItem(
        new IdentityItem("1111", AuthenticatedState.AUTHENTICATED, true),
        "userCRMId"); // must match the namespace configured on the feature flag
Identity.updateIdentities(identityMap);
```

>[!ENDTABS]

## API 參考資料 {#api-reference}

### 回呼和錯誤處理 {#callbacks-errors}

這些規則適用於`isFeatureEnabled`和`getFeature`：

* 永遠提供預設體驗。 傳遞`AdobeCallbackWithError`並在`fail`中顯示您的預設體驗。 若使用純`AdobeCallback`，則發生錯誤時不會呼叫任何專案。

* 擴充功能會在應用程式啟動時預先載入標幟定義。 之後，會在裝置上評估標幟。

* 其他錯誤： `fail`是以`AdobeError.UNEXPECTED_ERROR`呼叫，當：

  * 功能金鑰是空的，
  * 發佈的設定中缺少旗標設定或Experience Cloud組織ID，或
  * 應用程式啟動時（例如裝置離線），無法下載標幟定義。 擴充功能會在下次設定更新時重試，通常是下次應用程式啟動。

### isFeatureEnable {#is-feature-enabled}

傳回是否為目前使用者啟用功能。

**簽章**

>[!BEGINTABS]

>[!TAB Kotlin]

```kotlin
Flag.isFeatureEnabled(
    featureKey: String,
    evaluationContext: FeatureEvaluationContext,
    callback: AdobeCallback<Boolean>
)
```

>[!TAB Java]

```java
Flag.isFeatureEnabled(
    String featureKey,
    FeatureEvaluationContext evaluationContext,
    AdobeCallback<Boolean> callback);
```

>[!ENDTABS]

**參數**

| 參數 | 類型 | 說明 |
|---|---|---|
| `featureKey` | 字串 | 要評估的功能鍵 |
| `evaluationContext` | FeatureEvaluationContext | 目標定位屬性。 如果您沒有，請使用`FeatureEvaluationContext.builder().build()`。 請參閱[評估內容](#evaluation-context)。 |
| `callback` | AdobeCallback&lt;Boolean> | 如果使用者已啟用此功能，則使用`true`呼叫。 如果找不到功能、目標規則不符或使用者在控制組中，則使用`false`呼叫。 傳遞`AdobeCallbackWithError<Boolean>`以也接收錯誤。 |

**範例**

>[!BEGINTABS]

>[!TAB Kotlin]

```kotlin
import com.adobe.marketing.mobile.AdobeCallbackWithError
import com.adobe.marketing.mobile.AdobeError
import com.adobe.marketing.mobile.flags.Flag

Flag.isFeatureEnabled(
    "new-checkout",
    ctx,
    object : AdobeCallbackWithError<Boolean> {
        override fun call(isEnabled: Boolean?) {
            runOnUiThread {
                if (isEnabled == true) showNewCheckout() else showDefaultCheckout()
            }
        }

        override fun fail(error: AdobeError?) {
            runOnUiThread { showDefaultCheckout() }
        }
    }
)
```

>[!TAB Java]

```java
import com.adobe.marketing.mobile.AdobeCallbackWithError;
import com.adobe.marketing.mobile.AdobeError;
import com.adobe.marketing.mobile.flags.Flag;

Flag.isFeatureEnabled(
    "new-checkout",
    ctx,
    new AdobeCallbackWithError<Boolean>() {
        @Override
        public void call(Boolean isEnabled) {
            runOnUiThread(() -> {
                if (Boolean.TRUE.equals(isEnabled)) {
                    showNewCheckout();
                } else {
                    showDefaultCheckout();
                }
            });
        }

        @Override
        public void fail(AdobeError error) {
            runOnUiThread(() -> showDefaultCheckout());
        }
    }
);
```

>[!ENDTABS]

### getFeature {#get-feature}

傳回目前使用者的評估功能，包括其中繼資料。 當您需要更多啟用或停用功能時，請使用此API。

**簽章**

>[!BEGINTABS]

>[!TAB Kotlin]

```kotlin
Flag.getFeature(
    featureKey: String,
    evaluationContext: FeatureEvaluationContext,
    callback: AdobeCallback<FeatureEvaluationResult>
)
```

>[!TAB Java]

```java
Flag.getFeature(
    String featureKey,
    FeatureEvaluationContext evaluationContext,
    AdobeCallback<FeatureEvaluationResult> callback);
```

>[!ENDTABS]

**參數**

| 參數 | 類型 | 說明 |
|---|---|---|
| `featureKey` | 字串 | 要評估的功能鍵 |
| `evaluationContext` | FeatureEvaluationContext | 目標定位屬性。 如果您沒有，請使用`FeatureEvaluationContext.builder().build()`。 請參閱[評估內容](#evaluation-context)。 |
| `callback` | AdobeCallback&lt;FeatureEvaluationResult> | 以評估的功能呼叫，或當功能未提供給使用者時以`null`呼叫：索引鍵未知、不符合目標定位准則，或使用者在控制同類群組中。 `null`是正常結果，不是錯誤。 控制同類群組暴露風險仍會報告給Analytics。 傳遞`AdobeCallbackWithError<FeatureEvaluationResult>`以接收`fail(...)`的真正失敗，例如逾時。 |

將`null`結果視為「功能關閉」，並顯示您的預設體驗。 在呼叫`fail`時也顯示預設體驗，這僅在真正失敗（例如逾時）時發生。

**回應**

*FeatureEvaluationResult*

| 欄位 | 類型 | 說明 |
|---|---|---|
| `id` | 整數 | 功能ID |
| `key` | 字串 | 功能鍵 |
| `featureGroupKey` | 字串？ | 功能群組金鑰（如果功能屬於群組） |
| `meta` | 字串？ | 為功能設定的中繼資料，以純文字顯示，若未設定，則為`null`。 如果您已儲存JSON，請在應用程式中剖析字串。 |
| `analyticsParam` | AnalyticsParam？ | 評估的Analytics詳細資料 |

*AnalyticsParam*

| 欄位 | 類型 | 說明 |
|---|---|---|
| `featureGroupId` | 整數 | 功能群組識別碼 |
| `featureId` | 整數 | 功能ID |
| `variantId` | 字串？ | 指派使用者的變體ID |

**範例**

>[!BEGINTABS]

>[!TAB Kotlin]

```kotlin
import com.adobe.marketing.mobile.AdobeCallbackWithError
import com.adobe.marketing.mobile.AdobeError
import com.adobe.marketing.mobile.flags.FeatureEvaluationResult
import com.adobe.marketing.mobile.flags.Flag

Flag.getFeature(
    "new-checkout",
    ctx,
    object : AdobeCallbackWithError<FeatureEvaluationResult> {
        override fun call(feature: FeatureEvaluationResult?) {
            val meta = feature?.meta
            runOnUiThread {
                if (!meta.isNullOrEmpty()) applyExperience(meta) else showDefaultExperience()
            }
        }

        override fun fail(error: AdobeError?) {
            runOnUiThread { showDefaultExperience() }
        }
    }
)
```

>[!TAB Java]

```java
import com.adobe.marketing.mobile.AdobeCallbackWithError;
import com.adobe.marketing.mobile.AdobeError;
import com.adobe.marketing.mobile.flags.FeatureEvaluationResult;
import com.adobe.marketing.mobile.flags.Flag;

Flag.getFeature(
    "new-checkout",
    ctx,
    new AdobeCallbackWithError<FeatureEvaluationResult>() {
        @Override
        public void call(FeatureEvaluationResult feature) {
            final String meta = feature != null ? feature.getMeta() : null;
            runOnUiThread(() -> {
                if (meta != null && !meta.isEmpty()) {
                    applyExperience(meta);
                } else {
                    showDefaultExperience();
                }
            });
        }

        @Override
        public void fail(AdobeError error) {
            runOnUiThread(() -> showDefaultExperience());
        }
    }
);
```

>[!ENDTABS]

### extensionVersion {#extension-version}

傳回Flags擴充功能的版本。

**語法**

```kotlin
Flag.extensionVersion(): String
```

**範例**

*Kotlin*

```kotlin
val version = Flag.extensionVersion()
```

*Java*

```java
String version = Flag.extensionVersion();
```

## API摘要 {#api-summary}

| API | 傳回值 |
|---|---|
| `isFeatureEnabled(featureKey, evaluationContext, callback)`. 請參閱[isFeatureEnabled](#is-feature-enabled)。 | 布林值（透過callback） |
| `getFeature(featureKey, evaluationContext, callback)`. 請參閱[getFeature](#get-feature)。 | 透過回呼的FeatureEvaluationResult |
| `extensionVersion()` | 字串 |

## 除錯 {#debugging}

若要偵錯，請在偵錯組建中設定`MobileCore.setLogLevel(LoggingMode.DEBUG)`，並依`Flags`篩選Logcat。 您應該會看到來自MobileCore的`com.adobe.marketing.mobile.flags.FlagExtension`的`Discovered extension`訊息。


