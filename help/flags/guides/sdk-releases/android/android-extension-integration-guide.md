---
title: Android整合指南的旗標擴充功能
description: 瞭解如何在Android上將Flags擴充功能與Adobe Experience Platform Mobile SDK整合。
badge: label="Beta" type="Informative"
hide: true
exl-id: 683ef4d4-e637-4b7b-b694-689c7e65a99e
source-git-commit: 8fffd619232b2cae2f5dd0aa1e0a55183c4be698
workflow-type: tm+mt
source-wordcount: '984'
ht-degree: 5%

---

# 標示Android的擴充功能 {#android-extension-integration-guide}

本指南說明如何在Android上將Flags擴充功能與Adobe Experience Platform Mobile SDK整合。

## 先決條件 {#prerequisites}

在實作Flags擴充功能之前，請確定您擁有：

* 在[Adobe Experience Platform Data Collection](https://experience.adobe.com/#/data-collection)中設定的行動屬性
* 在您的行動屬性中安裝並設定的Flags擴充功能
* Adobe Experience Cloud組織ID
* 最低SDK： API 21 (Android 5.0 Lollipop)

## 擴充功能相依性 {#extension-dependencies}

Flags擴充功能需要下列Adobe Experience Platform擴充功能：

| 延伸 | 說明 | 必要 |
|---|---|---|
| 行動核心 | 提供核心功能，包括設定和事件處理 | 是 |
| Lifecycle | 收集行動SDK的應用程式生命週期和工作階段資料 | 是 |
| Edge Network | 啟用與Adobe Experience Platform Edge Network的通訊 | 是 |
| Edge身分 | 使用Edge Network擴充功能時，啟用行動應用程式的身分管理 | 是 |

請確認這些擴充功能已安裝在您的資料收集行動屬性中，並包含在您的應用程式相依性中。

## 在資料收集中設定標幟副檔名 {#configure}

### 安裝擴充功能 {#install-extension}

1. 登入[Adobe Experience Platform資料彙集](https://experience.adobe.com/#/data-collection)。
1. 選取&#x200B;**標籤**&#x200B;標籤，然後選擇您的行動裝置屬性。
1. 瀏覽至&#x200B;**擴充功能** > **目錄**。
1. 搜尋&#x200B;**標籤延伸模組**&#x200B;並選取&#x200B;**安裝**。
1. 設定擴充功能設定：

   | 設定 | 說明 |
   |---|---|
   | 應用程式 ID | 旗標中應用程式的唯一識別碼 |

1. 選取&#x200B;**儲存**。
1. 依照[發佈程式](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview)更新您的設定。

### 取得環境檔案ID {#environment-file-id}

1. 在您的行動屬性中，瀏覽至&#x200B;**環境**。
1. 為您的環境選取&#x200B;**安裝**&#x200B;欄下的方塊圖示。
1. 在&#x200B;**行動安裝指示**&#x200B;對話方塊中，複製&#x200B;**環境檔案識別碼**。

## 將Flags擴充功能新增至您的應用程式 {#add-to-app}

### 新增相依性 {#add-dependencies}

將行動SDK相依性新增至您的專案。 Flags擴充功能需要行動核心及下列與Edge相關的擴充功能。

#### 搭配BOM使用Gradle （建議） {#gradle-bom}

將下列相依性新增至應用程式的`build.gradle.kts`檔案：

```kotlin
dependencies {
    // Adobe Experience Platform Mobile SDK BOM
    implementation(platform("com.adobe.marketing.mobile:sdkbom:3.+"))

    // Required extensions
    implementation("com.adobe.marketing.mobile:core")
    implementation("com.adobe.marketing.mobile:lifecycle")
    implementation("com.adobe.marketing.mobile:edge")
    implementation("com.adobe.marketing.mobile:edgeidentity")
}
```

#### 使用Gradle (Groovy) {#gradle-groovy}

```groovy
dependencies {
    // Adobe Experience Platform Mobile SDK BOM
    implementation platform('com.adobe.marketing.mobile:sdkbom:3.+')

    // Required extensions
    implementation 'com.adobe.marketing.mobile:core'
    implementation 'com.adobe.marketing.mobile:lifecycle'
    implementation 'com.adobe.marketing.mobile:edge'
    implementation 'com.adobe.marketing.mobile:edgeidentity'
}
```

>[!IMPORTANT]
>
>對於生產應用程式，Adobe建議使用明確版本編號，而非動態版本。 如需詳細資訊，請參閱[管理Gradle相依性](https://docs.gradle.org/current/userguide/dependency_management.html)。

### 新增旗標相依性 {#add-flags-dependency}

#### 使用託管的Maven存放庫（建議） {#hosted-maven}

將Flags Maven存放庫新增到`settings.gradle.kts`中的`repositories`區塊：

```kotlin
maven {
    url = uri("<HTTPS Flags Maven repository URL>")
}
```

針對Groovy `settings.gradle`檔案：

```groovy
maven {
    url = uri('<HTTPS Flags Maven repository URL>')
}
```

以為Flags副檔名提供的安全存放庫URL取代`<HTTPS Flags Maven repository URL>`。

然後將已建立版本的旗標相依性新增到應用程式的`build.gradle.kts`：

```kotlin
implementation("com.adobe.marketing.mobile:flags:<version>")
```

針對Groovy `build.gradle`檔案：

```groovy
implementation 'com.adobe.marketing.mobile:flags:<version>'
```

將`<version>`取代為您發行版本提供的精確Flags延伸功能版本。

#### 使用Flags散發套件 {#distribution-package}

Flags擴充功能發佈套件包括：

* `flags-3.x.aar`
* `flags-3.x.module`
* `flags-3.x.pom`

請使用下列其中一種方法，讓您的Android專案可使用此擴充功能：

* 將發佈套件中的所有檔案發佈到本機或私人Maven存放庫，並設定您的專案以使用該存放庫。
* 將`flags-3.x.aar`直接新增至您的專案，並宣告`flags-3.x.pom`中指定的可傳遞相依性。

### 新增許可權 {#add-permissions}

將下列許可權新增至您的`AndroidManifest.xml`檔案：

```xml
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
```

### 初始化SDK {#initialize-sdk}

呼叫任何Flags擴充功能API之前，請先初始化`Application`類別中的Mobile SDK。 使用您行動屬性中的環境檔案識別碼搭配`MobileCore.initialize`，讓應用程式挑選您在Data Collection中發佈的Flags設定。

#### 使用MobileCore.initialization {#mobile-core-initialize}

自Android BOM 3.8.0版開始，此API便可使用您的資料收集環境檔案初始化SDK。

>[!IMPORTANT]
>
>對於生產應用程式，僅使用`LoggingMode.ERROR`；請勿在發行組建中使用`DEBUG`或`VERBOSE`。

**Kotlin**

```kotlin
import android.app.Application
import com.adobe.marketing.mobile.LoggingMode
import com.adobe.marketing.mobile.MobileCore

class MainApplication : Application() {

    override fun onCreate() {
        super.onCreate()

        // Production: use LoggingMode.ERROR only. Do not use DEBUG or VERBOSE in release builds.
        MobileCore.setLogLevel(LoggingMode.ERROR)

        // Initialize with your Environment File ID from Data Collection
        MobileCore.initialize(this, "YOUR_ENVIRONMENT_FILE_ID")
    }
}
```

**Java**

```java
import android.app.Application;
import com.adobe.marketing.mobile.LoggingMode;
import com.adobe.marketing.mobile.MobileCore;

public class MainApplication extends Application {

    @Override
    public void onCreate() {
        super.onCreate();

        // Production: use LoggingMode.ERROR only. Do not use DEBUG or VERBOSE in release builds.
        MobileCore.setLogLevel(LoggingMode.ERROR);

        // Initialize with your Environment File ID from Data Collection
        MobileCore.initialize(this, "YOUR_ENVIRONMENT_FILE_ID", null);
    }
}
```

### 註冊Application類別 {#register-application}

在`AndroidManifest.xml`中註冊您的`Application`類別：

```xml
<application
    android:name=".MainApplication"
    ... >
</application>
```

## 評估內容 {#evaluation-context}

`FeatureEvaluationContext`類別包含目標屬性（用於旗標規則比對）。

| 方法 | 必要 | 說明 |
|---|---|---|
| `withAttributes(map)` | 否 | `Map<String, List<String>>`. 索引鍵是旗標規則所使用的內容屬性名稱（例如`locale`、`platform`、`appVersion`、`deviceType`）。 值是目前使用者/工作階段之索引鍵的候選屬性值清單（例如`["en_US"]`或`["phone"]`）。 |

**Kotlin**

```kotlin
import com.adobe.marketing.mobile.flags.FeatureEvaluationContext

val attrs = mapOf(
    "locale" to listOf("en_US"),
    "platform" to listOf("ANDROID")
)

val ctx = FeatureEvaluationContext.builder()
    .withAttributes(attrs)
    .build()
```

**Java**

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

### 自訂身分 {#custom-identity}

Flags擴充功能會使用Edge Network的身分擴充功能來進行身分解析。 功能標幟可以在自訂身分上分組（例如CRM ID或忠誠度ID），以便變數拆分和分析繫結到對您的應用程式重要的身分。

編寫功能標幟時，必須在標幟UI中選取自訂身分名稱空間。 若要根據該身分評估旗標，裝置上的Edge身分`identityMap`中必須存在相同的身分，使用相符的名稱空間。 在執行階段提供Edge Network `updateIdentities` API的身分識別。

#### 將自訂身分新增至身分對應 {#add-identity}

在功能標幟上設定的相同名稱空間下新增身分。

**Kotlin**

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

**Java**

```java
import com.adobe.marketing.mobile.edge.identity.AuthenticatedState;
import com.adobe.marketing.mobile.edge.identity.Identity;
import com.adobe.marketing.mobile.edge.identity.IdentityItem;
import com.adobe.marketing.mobile.edge.identity.IdentityMap;

final IdentityItem item = new IdentityItem("1111", AuthenticatedState.AUTHENTICATED, true);
final IdentityMap identityMap = new IdentityMap();
identityMap.addItem(item, "userCRMId"); // must match the namespace configured on the feature flag
Identity.updateIdentities(identityMap);
```

## API 參考資料 {#api-reference}

### isFeatureEnable {#is-feature-enabled}

`isFeatureEnabled`會傳回指定內容的旗標功能是開啟還是關閉。 傳遞`featureKey`、`FeatureEvaluationContext` （選擇性目標定位屬性）及回呼。 請參閱[評估內容](#evaluation-context)。

**簽章**

*Kotlin*

```kotlin
Flag.isFeatureEnabled(
    featureKey: String,
    evaluationContext: FeatureEvaluationContext,
    callback: AdobeCallback<Boolean>
)
```

*Java*

```java
Flag.isFeatureEnabled(
    String featureKey,
    FeatureEvaluationContext evaluationContext,
    AdobeCallback<Boolean> callback);
```

**參數**

| 參數 | 類型 | 說明 |
|---|---|---|
| `featureKey` | 字串 | 要在旗標中評估的功能索引鍵 |
| `evaluationContext` | FeatureEvaluationContext | 視需要包含目標屬性；針對空白內容使用`FeatureEvaluationContext.builder().build()`。 請參閱[評估內容](#evaluation-context)。 |
| `callback` | AdobeCallback&lt;Boolean> | 如果功能已啟用，則使用`true`叫用，否則使用`false`。 您也可以傳遞`AdobeCallbackWithError<Boolean>`以處理`fail(...)`。 |

**範例**

*Kotlin*

```kotlin
import com.adobe.marketing.mobile.AdobeCallback
import com.adobe.marketing.mobile.flags.Flag

Flag.isFeatureEnabled(
    "new-flag",
    ctx,
    object : AdobeCallback<Boolean> {
        override fun call(isEnabled: Boolean?) {
            if (isEnabled == true) {
                // run the feature-specific behavior
            } else {
                // fall back to the default behavior
            }
        }
    }
)
```

*Java*

```java
import com.adobe.marketing.mobile.AdobeCallback;
import com.adobe.marketing.mobile.flags.Flag;

Flag.isFeatureEnabled(
    "new-flag",
    ctx,
    new AdobeCallback<Boolean>() {
        @Override
        public void call(Boolean isEnabled) {
            if (Boolean.TRUE.equals(isEnabled)) {
                // run the feature-specific behavior
            } else {
                // fall back to the default behavior
            }
        }
    }
);
```

### getFeature {#get-feature}

`getFeature`會針對提供的內容傳回評估的功能裝載。 當您需要更多已啟用/已停用，並且想要功能中繼資料或值時，請使用此API。

**簽章**

*Kotlin*

```kotlin
Flag.getFeature(
    featureKey: String,
    evaluationContext: FeatureEvaluationContext,
    callback: AdobeCallback<FeatureEvaluationResult>
)
```

*Java*

```java
Flag.getFeature(
    String featureKey,
    FeatureEvaluationContext evaluationContext,
    AdobeCallback<FeatureEvaluationResult> callback);
```

**參數**

| 參數 | 類型 | 說明 |
|---|---|---|
| `featureKey` | 字串 | 要在旗標中評估的功能索引鍵 |
| `evaluationContext` | FeatureEvaluationContext | 視需要包含目標屬性；針對空白內容使用`FeatureEvaluationContext.builder().build()`。 請參閱[評估內容](#evaluation-context)。 |
| `callback` | AdobeCallback&lt;FeatureEvaluationResult> | 以評估的功能裝載叫用；找不到功能時，可能是`null`。 您也可以傳遞`AdobeCallbackWithError<FeatureEvaluationResult>`以處理`fail(...)`。 |

**回應**

*FeatureEvaluationResult*

| 欄位 | 類型 | 說明 |
|---|---|---|
| `id` | 整數 | 數值功能識別碼 |
| `key` | 字串 | 功能鍵 |
| `featureGroupKey` | 字串？ | 功能群組索引鍵（可用時） |
| `meta` | 字串？ | 可用時以JSON字串形式顯示功能中繼資料 |
| `analyticsParam` | AnalyticsParam？ | 已評估功能的Analytics詳細資料 |

*AnalyticsParam*

| 欄位 | 類型 | 說明 |
|---|---|---|
| `featureGroupId` | 整數 | 數值功能群組識別碼 |
| `featureId` | 整數 | 數值功能識別碼 |
| `variantId` | 字串？ | 變體識別碼 |

**範例**

*Kotlin*

```kotlin
import com.adobe.marketing.mobile.AdobeCallback
import com.adobe.marketing.mobile.flags.FeatureEvaluationResult
import com.adobe.marketing.mobile.flags.Flag

Flag.getFeature(
    "new-flag",
    ctx,
    object : AdobeCallback<FeatureEvaluationResult> {
        override fun call(feature: FeatureEvaluationResult?) {
            val meta = feature?.meta
            if (!meta.isNullOrEmpty()) {
                // Feature metadata is available: use it to drive the feature behavior
            } else {
                // No metadata available: fall back to the default behavior
            }
        }
    }
)
```

*Java*

```java
import com.adobe.marketing.mobile.AdobeCallback;
import com.adobe.marketing.mobile.flags.FeatureEvaluationResult;
import com.adobe.marketing.mobile.flags.Flag;

Flag.getFeature(
    "new-flag",
    ctx,
    new AdobeCallback<FeatureEvaluationResult>() {
        @Override
        public void call(FeatureEvaluationResult feature) {
            String meta = feature != null ? feature.getMeta() : null;
            if (meta != null && !meta.isEmpty()) {
                // Feature metadata is available: use it to drive the feature behavior
            } else {
                // No metadata available: fall back to the default behavior
            }
        }
    }
);
```

### extensionVersion {#extension-version}

傳回Flags副檔名的版本字串。

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
| `isFeatureEnabled(featureKey, evaluationContext, callback)`. `FeatureEvaluationContext`攜帶規則的鎖定目標屬性。 請參閱[功能評估](#is-feature-enabled)。 | 布林值（透過callback） |
| `getFeature(featureKey, evaluationContext, callback)`. 傳回給定內容的評估功能裝載。 請參閱[getFeature](#get-feature)。 | 透過回呼的FeatureEvaluationResult |
| `extensionVersion()` | 字串 |

## 另請參閱 {#see-also}

* [行動應用程式](../../integrate/mobile-applications.md)
* [SDK](../../integrate/sdks.md)

<!-- -->
