---
title: iOS整合指南的旗標擴充功能
description: 瞭解如何在iOS上將Flags擴充功能與Adobe Experience Platform Mobile SDK整合。
badge: label="Beta" type="Informative"
hide: true
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
source-git-commit: c1fafcfcd7d5d22781abdd10e6eb3c2b84136c2d
workflow-type: tm+mt
source-wordcount: '1313'
ht-degree: 3%
---
# 標示iOS的擴充功能 {#ios-extension-integration-guide}

本指南說明如何在iOS上將Flags擴充功能與Adobe Experience Platform Mobile SDK整合。 原始程式碼可在[aepsdk-flags-ios](https://github.com/adobe/aepsdk-flags-ios)存放庫中取得。

## 先決條件 {#prerequisites}

開始之前，請確定您擁有：

* iOS 12.0或更新版本，以及Swift 5.7或更新版本
* [Adobe Experience Platform Data Collection](https://experience.adobe.com/#/data-collection)中的行動屬性
* 這些擴充功能已安裝並設定於行動屬性中：

  | 延伸 | 說明 | 最低SDK版本 |
  |---|---|---|
  | [行動核心](https://developer.adobe.com/client-sdks/home/base/mobile-core/) | 設定和事件處理 | AEPCore 5.8.0 |
  | [生命週期](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/) | 應用程式生命週期資料 | 與AEPCore相同 |
  | [Edge Network](https://developer.adobe.com/client-sdks/edge/edge-network/) | 與Adobe Experience Platform Edge Network的通訊。 需要資料串流。 | AEPEdge 5.0.2 |
  | Edge Network的[身分](https://developer.adobe.com/client-sdks/edge/identity-for-edge-network/) | Edge Network的身分管理 | AEPEdgeIdentity 5.0.0 |
  | [旗標](https://experienceleague.adobe.com/en/docs/target/flags/home) | 功能標幟評估 | 請參閱[安裝](#installation) |

## 在資料收集中設定標幟 {#configure}

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

## 安裝 {#installation}

使用Swift Package Manager或XCFramework新增擴充功能。 針對每個應用程式目標使用一個方法。

### Swift封裝管理程式 {#swift-package-manager}

在Xcode中：

1. 選取&#x200B;**檔案** > **新增套件相依性**。

1. 輸入封裝URL： `https://github.com/adobe/aepsdk-flags-ios.git`

1. 針對版本規則，請選取&#x200B;**確切版本**，並從[發行頁面](https://github.com/adobe/aepsdk-flags-ios/releases)輸入最新版本。

1. 將`AEPFlags`資料庫新增至您的應用程式目標。

1. 新增擴充功能所依賴的Adobe套件，並將其程式庫新增至您的應用程式目標：

   * `https://github.com/adobe/aepsdk-core-ios.git`： `AEPCore`、`AEPLifecycle`和`AEPServices`
   * `https://github.com/adobe/aepsdk-edge-ios.git`: `AEPEdge`
   * `https://github.com/adobe/aepsdk-edgeidentity-ios.git`: `AEPEdgeIdentity`

如果您的專案使用`Package.swift`檔案，請在該處新增相依性。 以發行頁面的最新版本取代`<latest-version>`。

```swift
dependencies: [
    .package(url: "https://github.com/adobe/aepsdk-flags-ios.git", exact: "<latest-version>"),
    .package(url: "https://github.com/adobe/aepsdk-core-ios.git", .upToNextMajor(from: "5.8.0")),
    .package(url: "https://github.com/adobe/aepsdk-edge-ios.git", .upToNextMajor(from: "5.0.2")),
    .package(url: "https://github.com/adobe/aepsdk-edgeidentity-ios.git", .upToNextMajor(from: "5.0.0"))
],
targets: [
    .target(
        name: "YourTarget",
        dependencies: [
            .product(name: "AEPFlags", package: "aepsdk-flags-ios"),
            .product(name: "AEPCore", package: "aepsdk-core-ios"),
            .product(name: "AEPLifecycle", package: "aepsdk-core-ios"),
            .product(name: "AEPServices", package: "aepsdk-core-ios"),
            .product(name: "AEPEdge", package: "aepsdk-edge-ios"),
            .product(name: "AEPEdgeIdentity", package: "aepsdk-edgeidentity-ios")
        ]
    )
]
```

### XCFramework {#xcframework}

1. 從[發行頁面](https://github.com/adobe/aepsdk-flags-ios/releases)，下載`AEPFlags-<version>.xcframework.zip`並將其解壓縮。

1. 從每個存放庫的發行頁面下載擴充功能相依的XCFramework：

   * [aepsdk-core-ios版本](https://github.com/adobe/aepsdk-core-ios/releases)： `AEPCore`、`AEPServices`、`AEPLifecycle`和`AEPRulesEngine`
   * [aepsdk-edge-ios版本](https://github.com/adobe/aepsdk-edge-ios/releases)： `AEPEdge`
   * [aepsdk-edgeidentity-ios發行版本](https://github.com/adobe/aepsdk-edgeidentity-ios/releases)： `AEPEdgeIdentity`

1. 在Xcode中，選取您的應用程式目標，然後開啟&#x200B;**一般** > **架構、資料庫和內嵌內容**。

1. 新增`AEPFlags.xcframework`和所有相依的XCFramework。

1. 將每個框架設定為&#x200B;**嵌入與簽署**。

## 初始化SDK {#initialize-sdk}

註冊Flags擴充功能，然後使用行動屬性中的環境檔案ID初始化SDK。 `MobileCore.initialize`不會為您註冊Flags副檔名，所以請先註冊它。

>[!BEGINTABS]

>[!TAB Swift]

```swift
import AEPCore
import AEPFlags
import UIKit

class AppDelegate: UIResponder, UIApplicationDelegate {
    func application(
        _ application: UIApplication,
        didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?
    ) -> Bool {
        MobileCore.registerExtensions([Flag.self])
        MobileCore.initialize(appId: "<your-environment-file-id>")
        return true
    }
}
```

>[!TAB Objective-C]

```objc
@import AEPCore;
@import AEPFlags;

- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {
    [AEPMobileCore registerExtensions:@[AEPMobileFlag.class] completion:nil];
    [AEPMobileCore initializeWithAppId:@"<your-environment-file-id>" completion:nil];
    return YES;
}
```

>[!ENDTABS]

### 手動註冊擴充功能 {#register-manually}

如果您自行註冊擴充功能，請先註冊所有擴充功能。 應用程式進入前景時呼叫`MobileCore.lifecycleStart`，應用程式進入背景時呼叫`MobileCore.lifecyclePause`。

如果您的應用程式使用場景，請改在`sceneWillEnterForeground(_:)`和`sceneDidEnterBackground(_:)`中進行這些呼叫。

>[!BEGINTABS]

>[!TAB Swift]

```swift
import AEPCore
import AEPEdge
import AEPEdgeIdentity
import AEPFlags
import AEPLifecycle
import UIKit

class AppDelegate: UIResponder, UIApplicationDelegate {
    func application(
        _ application: UIApplication,
        didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?
    ) -> Bool {
        MobileCore.registerExtensions([
            Lifecycle.self,
            Edge.self,
            AEPEdgeIdentity.Identity.self,
            Flag.self
        ]) {
            MobileCore.configureWith(appId: "<your-environment-file-id>")
            DispatchQueue.main.async {
                if application.applicationState != .background {
                    MobileCore.lifecycleStart(additionalContextData: nil)
                }
            }
        }
        return true
    }

    func applicationWillEnterForeground(_ application: UIApplication) {
        MobileCore.lifecycleStart(additionalContextData: nil)
    }

    func applicationDidEnterBackground(_ application: UIApplication) {
        MobileCore.lifecyclePause()
    }
}
```

>[!TAB Objective-C]

```objc
@import AEPCore;
@import AEPEdge;
@import AEPEdgeIdentity;
@import AEPFlags;
@import AEPLifecycle;

- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {
    [AEPMobileCore registerExtensions:@[
        AEPMobileLifecycle.class,
        AEPMobileEdge.class,
        AEPMobileEdgeIdentity.class,
        AEPMobileFlag.class
    ] completion:^{
        [AEPMobileCore configureWithAppId:@"<your-environment-file-id>"];
        dispatch_async(dispatch_get_main_queue(), ^{
            if (application.applicationState != UIApplicationStateBackground) {
                [AEPMobileCore lifecycleStart:nil];
            }
        });
    }];
    return YES;
}

- (void)applicationWillEnterForeground:(UIApplication *)application {
    [AEPMobileCore lifecycleStart:nil];
}

- (void)applicationDidEnterBackground:(UIApplication *)application {
    [AEPMobileCore lifecyclePause];
}
```

>[!ENDTABS]

## 評估內容 {#evaluation-context}

每個評估呼叫都需要`FeatureEvaluationContext`。 它保有旗標的目標規則所使用的屬性。

| 參數 | 必填 | 說明 |
|---|---|---|
| `attributes` | 否 | `[String: [String]]`. 每個索引鍵都是您的標幟鎖定目標規則所使用的屬性名稱。 每個值都是目前使用者的值清單。 |

* 使用與您在「旗標」中定義的鎖定目標規則相符的屬性名稱和值。
* 每個產生器最多呼叫`withAttributes`一次。 第二個呼叫會終止應用程式。
* 若要評估不含屬性，請呼叫`build()`而不呼叫`withAttributes`。

>[!BEGINTABS]

>[!TAB Swift]

```swift
import AEPFlags

let context = FeatureEvaluationContext.builder()
    .withAttributes([
        "locale": ["en_US"],
        "appVersion": ["3.0.0"]
    ])
    .build()
```

>[!TAB Objective-C]

```objc
@import AEPFlags;

AEPFeatureEvaluationContext *context = [[[AEPFeatureEvaluationContext builder]
    withAttributes:@{
        @"locale": @[@"en_US"],
        @"appVersion": @[@"3.0.0"]
    }]
    build];
```

>[!ENDTABS]

## 自訂身分 {#custom-identity}

Flags擴充功能會使用Edge Network的身分擴充功能來進行身分解析。 功能標幟可以在自訂身分上分組（例如CRM ID或忠誠度ID），以便變數拆分和分析繫結到對您的應用程式重要的身分。

編寫功能標幟時，必須在標幟UI中選取自訂身分名稱空間。 若要根據該身分評估旗標，裝置上的Edge身分`identityMap`中必須存在相同的身分，使用相符的名稱空間。 在執行階段提供Edge Network `updateIdentities` API的身分識別。

### 將自訂身分新增至身分對應 {#add-identity}

在功能標幟上設定的相同名稱空間下新增身分。

請注意下列行為：

* 名稱空間必須與標幟上設定的名稱空間完全相符，包括大寫和小寫字母。
* 如果名稱空間中有數個身分，系統會使用標示為主要身分的身分。 如果沒有任何專案標示為主要，則會使用第一個專案。
* 如果缺少身分，呼叫不會失敗。 系統只會針對目前應用程式工作階段隨機將使用者指派給變體，且可在應用程式重新啟動後將使用者指派給其他變體。 在評估使用身分的旗標之前，請先設定身分識別。

>[!BEGINTABS]

>[!TAB Swift]

```swift
import AEPEdgeIdentity

let identityMap = IdentityMap()
identityMap.add(
    item: IdentityItem(id: "1111", authenticatedState: .authenticated, primary: true),
    withNamespace: "userCRMId" // must match the namespace configured on the feature flag
)
Identity.updateIdentities(with: identityMap)
```

>[!TAB Objective-C]

```objc
@import AEPEdgeIdentity;

AEPIdentityItem *item = [[AEPIdentityItem alloc] initWithId:@"1111"
                                         authenticatedState:AEPAuthenticatedStateAuthenticated
                                                    primary:YES];
AEPIdentityMap *identityMap = [[AEPIdentityMap alloc] init];
[identityMap addItem:item withNamespace:@"userCRMId"]; // must match the namespace configured on the feature flag
[AEPMobileEdgeIdentity updateIdentities:identityMap];
```

>[!ENDTABS]


## API 參考資料 {#api-reference}

### isFeatureEnable {#is-feature-enabled}

檢查功能是否為目前使用者啟用。 當功能存在、使用者符合其目標規則，且使用者不在控制組時，結果為`true`。 否則，結果為`false`。

>[!BEGINTABS]

>[!TAB Swift]

```swift
static func isFeatureEnabled(
    _ featureKey: String,
    evaluationContext: FeatureEvaluationContext,
    completion: @escaping (Bool) -> Void,
    errorCallback: ((AEPError) -> Void)?
)
```

>[!TAB Objective-C]

```objc
+ (void)isFeatureEnabled:(NSString *)featureKey
       evaluationContext:(AEPFeatureEvaluationContext *)evaluationContext
              completion:(void (^)(BOOL))completion
           errorCallback:(void (^ _Nullable)(enum AEPError))errorCallback;
```

>[!ENDTABS]

**參數**

| 參數 | 類型 | 說明 |
|---|---|---|
| `featureKey` | 字串 | 要在旗標中評估的功能索引鍵 |
| `evaluationContext` | FeatureEvaluationContext | 視需要包含目標屬性；針對空白內容使用`FeatureEvaluationContext.builder().build()`。 請參閱[評估內容](#evaluation-context)。 |
| `completion` | `(Bool) -> Void` | 如果功能已啟用，則使用`true`呼叫，否則使用`false`。 |
| `errorCallback` | `((AEPError) -> Void)?` | 選填。 僅針對真正失敗呼叫，例如空白金鑰、遺失設定、評估失敗或逾時。 |

**範例**

>[!BEGINTABS]

>[!TAB Swift]

```swift
Flag.isFeatureEnabled("new-flag", evaluationContext: context) { isEnabled in
    DispatchQueue.main.async {
        if isEnabled {
            // Run the feature-specific behavior
        } else {
            // Run the default behavior
        }
    }
} errorCallback: { _ in
    DispatchQueue.main.async {
        // Run the default behavior
    }
}
```

>[!TAB Objective-C]

```objc
[AEPMobileFlag isFeatureEnabled:@"new-flag"
              evaluationContext:context
                     completion:^(BOOL isEnabled) {
    dispatch_async(dispatch_get_main_queue(), ^{
        if (isEnabled) {
            // Run the feature-specific behavior
        } else {
            // Run the default behavior
        }
    });
} errorCallback:^(enum AEPError error) {
    dispatch_async(dispatch_get_main_queue(), ^{
        // Run the default behavior
    });
}];
```

>[!ENDTABS]

### getFeature {#get-feature}

>[!IMPORTANT]
>
>舊版在功能未提供時，使用`AEPError.unexpected`呼叫錯誤回呼。 如果您的應用程式將該錯誤視為「功能遺失」，請在完成中改為處理`nil`。

傳回目前使用者的功能詳細資訊，包括其中繼資料和指派給使用者的變體。 當您需要更多啟用或停用時，請使用該功能。

只有在向使用者提供功能時，才會呼叫完成並產生結果。 如果未提供此功能，則會使用`nil`呼叫完成。 這是正常結果，而不是錯誤，而且不會呼叫錯誤回呼。 當發生下列情況時，使用`nil`呼叫完成：

* 沒有功能有此索引鍵。
* 使用者不符合目標規則。
* 使用者是在控制組。

只有在發生錯誤時，才會使用`AEPError.unexpected` （或其他`AEPError`）呼叫錯誤回呼：功能金鑰為空白、缺少必要的設定值、評估失敗、無法讀取回應，或要求逾時。

>[!BEGINTABS]

>[!TAB Swift]

```swift
static func getFeature(
    _ featureKey: String,
    evaluationContext: FeatureEvaluationContext,
    completion: @escaping (FeatureEvaluationResult?) -> Void,
    errorCallback: ((AEPError) -> Void)?
)
```

>[!TAB Objective-C]

```objc
+ (void)getFeature:(NSString *)featureKey
 evaluationContext:(AEPFeatureEvaluationContext *)evaluationContext
        completion:(void (^)(AEPFeatureEvaluationResult * _Nullable))completion
     errorCallback:(void (^ _Nullable)(enum AEPError))errorCallback;
```

>[!ENDTABS]

**參數**

| 參數 | 類型 | 說明 |
|---|---|---|
| `featureKey` | 字串 | 要在旗標中評估的功能索引鍵 |
| `evaluationContext` | FeatureEvaluationContext | 視需要包含目標屬性；針對空白內容使用`FeatureEvaluationContext.builder().build()`。 請參閱[評估內容](#evaluation-context)。 |
| `completion` | `(FeatureEvaluationResult?) -> Void` | 使用評估的功能裝載呼叫。 當功能未提供給使用者（未知索引鍵、目標不匹配或控制組）時，使用`nil`呼叫。 `nil`不是錯誤。 |
| `errorCallback` | `((AEPError) -> Void)?` | 選填。 僅針對真正失敗呼叫，例如空白金鑰、遺失設定、評估失敗或逾時。 未提供功能時不會呼叫。 |

**回應**

*FeatureEvaluationResult*

| 欄位 | 類型 | 說明 |
|---|---|---|
| `id` | 整數 | 功能ID |
| `key` | 字串 | 功能鍵 |
| `featureGroupKey` | 字串？ | 包含特徵的特徵群組的鍵 |
| `meta` | 字串？ | 為功能設定的中繼資料，如文字。 如果您的中繼資料是JSON，請在應用程式中將其解碼。 |
| `analyticsParam` | AnalyticsParam？ | 功能和使用者變體的識別碼 |

**範例**

>[!BEGINTABS]

>[!TAB Swift]

```swift
Flag.getFeature("new-flag", evaluationContext: context) { feature in
    DispatchQueue.main.async {
        guard let meta = feature?.meta, !meta.isEmpty else {
            // The feature is not served to this user (feature is nil), or it has no metadata.
            // Run the default behavior
            return
        }
        // Use the metadata to drive the feature behavior
    }
} errorCallback: { _ in
    DispatchQueue.main.async {
        // A genuine failure occurred. Run the default behavior
    }
}
```

>[!TAB Objective-C]

```objc
[AEPMobileFlag getFeature:@"new-flag"
        evaluationContext:context
               completion:^(AEPFeatureEvaluationResult * _Nullable feature) {
    dispatch_async(dispatch_get_main_queue(), ^{
        if (feature.meta.length > 0) {
            // Use the metadata to drive the feature behavior
        } else {
            // Run the default behavior
        }
    });
} errorCallback:^(enum AEPError error) {
    dispatch_async(dispatch_get_main_queue(), ^{
        // Run the default behavior
    });
}];
```

>[!ENDTABS]

### extensionVersion {#extension-version}

傳回Flags擴充功能的版本。

*Swift*

```swift
let version = Flag.extensionVersion
```

*Objective-C*

```objc
NSString *version = [AEPMobileFlag flagExtensionVersion];
```

## API摘要 {#api-summary}

| API | 傳回值 |
|---|---|
| `isFeatureEnabled(_:evaluationContext:completion:errorCallback:)` | 逐步完成整個步驟 |
| `getFeature(_:evaluationContext:completion:errorCallback:)` | FeatureEvaluationResult？ 完成為止 |
| `extensionVersion` | 字串 |
