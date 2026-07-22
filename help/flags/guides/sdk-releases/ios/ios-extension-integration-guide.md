---
title: iOS整合指南的旗標擴充功能
description: 瞭解如何在iOS上將Flags擴充功能與Adobe Experience Platform Mobile SDK整合。
badge: label="Beta" type="Informative"
hide: true
source-git-commit: 8fffd619232b2cae2f5dd0aa1e0a55183c4be698
workflow-type: tm+mt
source-wordcount: '1036'
ht-degree: 5%

---

# 標示iOS的擴充功能 {#ios-extension-integration-guide}

本指南說明如何在iOS上將Flags擴充功能與Adobe Experience Platform Mobile SDK整合。

## 先決條件 {#prerequisites}

在實作Flags擴充功能之前，請確定您擁有：

* 在[Adobe Experience Platform Data Collection](https://experience.adobe.com/#/data-collection)中設定的行動屬性
* 在您的行動屬性中安裝並設定的Flags擴充功能
* Adobe Experience Cloud組織ID
* 最低部署目標： iOS 12.0

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

#### 使用Swift封裝管理程式 {#swift-package-manager}

在Xcode中，選取&#x200B;**檔案** > **新增套件**，並新增下列Adobe Experience Platform Mobile SDK套件URL：

| 套件 | URL |
|---|---|
| AEPCore | `https://github.com/adobe/aepsdk-core-ios.git` |
| AEPEdge | `https://github.com/adobe/aepsdk-edge-ios.git` |
| AEPEdgeIdentity | `https://github.com/adobe/aepsdk-edgeidentity-ios.git` |

出現提示時，選取下列資料庫以新增至您的目標：

* `AEPCore`，`AEPLifecycle` （來自`aepsdk-core-ios`）
* `AEPEdge` （來自`aepsdk-edge-ios`）
* `AEPEdgeIdentity` （來自`aepsdk-edgeidentity-ios`）

使用AEPCore 5.8.0或更新版本。

>[!NOTE]
>
>在Xcode中新增套件時，請為每個套件選擇相依性規則（例如&#x200B;**至下一個主要版本**），這會自動挑選新的次要和修補程式發行版本，同時排除下一個主要版本。 如需最新發行的版本，請檢視GitHub上每個擴充功能的發行頁面。

### 新增Flags套件 {#add-flags-package}

請針對應用程式目標使用Swift套件或XCFramework整合方法，而非兩者。

#### 適用於沒有Package.swift檔案的Xcode專案 {#xcode-project}

1. 在Xcode中，選取&#x200B;**檔案** > **新增封裝**。
1. 選取&#x200B;**新增本機**。
1. 選取提供的`Packages/AEPFlags`目錄，其中包含`Package.swift`。
1. 將`AEPFlags`資料庫新增至您的應用程式目標。

Xcode會將本機套件參考儲存在專案中，因此您的應用程式不需要自己的`Package.swift`檔案。

#### 針對含有Package.swift檔案的專案 {#package-swift-project}

在現有資訊清單中，新增`AEPFlags`至您的應用程式目標相依性，並使用提供的URL和資訊清單中的總和檢查碼新增二進位目標：

```swift
targets: [
    .target(
        name: "YourApp",
        dependencies: [
            "AEPFlags"
        ]
    ),
    .binaryTarget(
        name: "AEPFlags",
        url: "<AEPFlags binary URL>",
        checksum: "<AEPFlags binary checksum>"
    )
]
```

Swift封裝管理程式會解析本機Xcode、CI和封存組建的二進位目標。

#### 直接新增XCFramework {#xcframework}

或者，將提供的`AEPFlags.xcframework`拖曳至Xcode專案導覽器，並將其新增至您的應用程式目標。 在&#x200B;**一般** > **架構、程式庫和內嵌內容**&#x200B;底下，將架構設定為&#x200B;**內嵌與簽署**。

### 初始化SDK {#initialize-sdk}

呼叫任何Flags API之前，請先在您的`AppDelegate`中註冊Mobile SDK擴充功能。 在身分識別、Edge和生命週期後註冊`Flag`，然後使用行動屬性中的環境檔案ID設定SDK。

#### 註冊和設定擴充功能 {#register-configure}

>[!IMPORTANT]
>
>對於生產應用程式，僅使用`.error`記錄層級；請勿在發行組建中使用`.debug`或`.trace`。

**Swift**

```swift
// AppDelegate.swift
import AEPCore
import AEPLifecycle
import AEPEdge
import AEPEdgeIdentity
import AEPFlags
import UIKit

final class AppDelegate: NSObject, UIApplicationDelegate {

    func application(_: UIApplication,
                      didFinishLaunchingWithOptions _: [UIApplication.LaunchOptionsKey: Any]? = nil) -> Bool {
        // Production: use .error only. Do not use .debug or .trace in release builds.
        MobileCore.setLogLevel(.error)

        MobileCore.registerExtensions([
            Identity.self,
            Edge.self,
            Lifecycle.self,
            Flag.self
        ]) {
            MobileCore.configureWith(appId: "YOUR_ENVIRONMENT_FILE_ID")
            MobileCore.lifecycleStart(additionalContextData: nil)
        }

        return true
    }
}
```

**Objective-C**

```objc
// AppDelegate.m
#import "AppDelegate.h"
@import AEPCore;
@import AEPLifecycle;
@import AEPEdge;
@import AEPEdgeIdentity;
@import AEPFlags;

@implementation AppDelegate

- (BOOL)application:(UIApplication *)application
    didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {

    // Production: use AEPLogLevelError only. Do not use Debug or Trace in release builds.
    [AEPMobileCore setLogLevel:AEPLogLevelError];

    [AEPMobileCore registerExtensions:@[
        AEPMobileEdgeIdentity.class,
        AEPMobileEdge.class,
        AEPMobileLifecycle.class,
        AEPMobileFlag.class
    ] completion:^{
        [AEPMobileCore configureWithAppId:@"YOUR_ENVIRONMENT_FILE_ID"];
        [AEPMobileCore lifecycleStart:nil];
    }];

    return YES;
}

@end
```

## 評估內容 {#evaluation-context}

`FeatureEvaluationContext`包含目標屬性（用於旗標規則比對）。

| 參數 | 必填 | 說明 |
|---|---|---|
| `attributes` | 否 | `[String: [String]]`. 索引鍵是旗標規則所使用的內容屬性名稱（例如`locale`、`platform`、`appVersion`、`deviceType`）。 值是目前使用者/工作階段之索引鍵的候選屬性值清單（例如`["en_US"]`或`["phone"]`）。 |

**Swift**

```swift
import AEPFlags

let attrs: [String: [String]] = [
    "locale": ["en_US"],
    "platform": ["IOS"],
    "appVersion": ["3.0.0"]
]

let ctx = FeatureEvaluationContext.builder()
    .withAttributes(attrs)
    .build()
```

**Objective-C**

```objc
@import AEPFlags;

NSDictionary<NSString *, NSArray<NSString *> *> *attrs = @{
    @"locale": @[@"en_US"],
    @"platform": @[@"IOS"],
    @"appVersion": @[@"3.0.0"]
};

AEPFeatureEvaluationContextBuilder *builder = [AEPFeatureEvaluationContext builder];
AEPFeatureEvaluationContext *ctx = [[builder withAttributes:attrs] build];
```

### 目標屬性範例 {#sample-attributes}

| 屬性 | 說明 | 範例值 |
|---|---|---|
| `locale` | 使用者的地區/語言 | `["en_US"]`, `["fr_FR"]` |
| `platform` | 平台識別碼 | `["IOS"]` |
| `appVersion` | 應用程式版本 | `["3.0.0"]` |
| `deviceType` | 裝置類型 | `["phone"]`, `["tablet"]` |

### 自訂身分 {#custom-identity}

Flags擴充功能會使用Edge Network的身分擴充功能來進行身分解析。 功能標幟可以在自訂身分上分組（例如CRM ID或忠誠度ID），以便變數拆分和分析繫結到對您的應用程式重要的身分。

編寫功能標幟時，必須在標幟UI中選取自訂身分名稱空間。 若要根據該身分評估旗標，裝置上的Edge身分`identityMap`中必須存在相同的身分，使用相符的名稱空間。 在執行階段提供Edge Network `updateIdentities` API的身分識別。

#### 將自訂身分新增至身分對應 {#add-identity}

在功能標幟上設定的相同名稱空間下新增身分。

**Swift**

```swift
import AEPEdgeIdentity

let identityMap = IdentityMap()
identityMap.add(item: IdentityItem(id: "1111", authenticatedState: .authenticated, primary: true),
                 withNamespace: "userCRMId") // must match the namespace configured on the feature flag
Identity.updateIdentities(with: identityMap)
```

**Objective-C**

```objc
@import AEPEdgeIdentity;

AEPIdentityItem *item = [[AEPIdentityItem alloc]
    initWithId:@"1111"
    authenticatedState:AEPAuthenticatedStateAuthenticated
    primary:YES];
AEPIdentityMap *identityMap = [[AEPIdentityMap alloc] init];
[identityMap addItem:item withNamespace:@"userCRMId"]; // must match the namespace configured on the feature flag
[AEPMobileEdgeIdentity updateIdentities:identityMap];
```

## API 參考資料 {#api-reference}

### isFeatureEnable {#is-feature-enabled}

`isFeatureEnabled`會傳回指定內容的旗標功能是開啟還是關閉。 傳遞`featureKey`、`FeatureEvaluationContext` （選擇性目標屬性）和完成結束。 請參閱[評估內容](#evaluation-context)。

**簽章**

*Swift*

```swift
static func isFeatureEnabled(
    _ featureKey: String,
    evaluationContext: FeatureEvaluationContext,
    completion: @escaping (Bool) -> Void
)
```

*Objective-C*

```objc
+ (void)isFeatureEnabled:(NSString *)featureKey
       evaluationContext:(AEPFeatureEvaluationContext *)evaluationContext
               completion:(void (^)(BOOL))completion;
```

**參數**

| 參數 | 類型 | 說明 |
|---|---|---|
| `featureKey` | 字串 | 要在旗標中評估的功能索引鍵 |
| `evaluationContext` | FeatureEvaluationContext | 視需要包含目標屬性；針對空白內容使用`FeatureEvaluationContext.builder().build()`。 請參閱[評估內容](#evaluation-context)。 |
| `completion` | `(Bool) -> Void` | 如果功能已啟用，則使用`true`呼叫，否則使用`false`。 |

**範例**

*Swift*

```swift
import AEPFlags

Flag.isFeatureEnabled(
    "new-flag",
    evaluationContext: ctx
) { isEnabled in
    if isEnabled {
        // Feature is enabled: run the feature-specific behavior
    } else {
        // Feature is disabled: fall back to the default behavior
    }
}
```

*Objective-C*

```objc
@import AEPFlags;

[AEPMobileFlag isFeatureEnabled:@"new-flag"
              evaluationContext:ctx
                      completion:^(BOOL isEnabled) {
    if (isEnabled) {
        // Feature is enabled: run the feature-specific behavior
    } else {
        // Feature is disabled: fall back to the default behavior
    }
}];
```

### getFeature {#get-feature}

`getFeature`會針對提供的內容傳回評估的功能裝載。 當您需要更多已啟用/已停用，並且想要功能中繼資料或值時，請使用此API。

**簽章**

*Swift*

```swift
static func getFeature(
    _ featureKey: String,
    evaluationContext: FeatureEvaluationContext,
    completion: @escaping (FeatureEvaluationResult?) -> Void
)
```

*Objective-C*

```objc
+ (void)getFeature:(NSString *)featureKey
 evaluationContext:(AEPFeatureEvaluationContext *)evaluationContext
        completion:(void (^)(AEPFeatureEvaluationResult * _Nullable))completion;
```

**參數**

| 參數 | 類型 | 說明 |
|---|---|---|
| `featureKey` | 字串 | 要在旗標中評估的功能索引鍵 |
| `evaluationContext` | FeatureEvaluationContext | 視需要包含目標屬性；針對空白內容使用`FeatureEvaluationContext.builder().build()`。 請參閱[評估內容](#evaluation-context)。 |
| `completion` | `(FeatureEvaluationResult?) -> Void` | 使用評估的功能裝載呼叫；找不到功能時`nil`。 |

**回應**

*FeatureEvaluationResult*

| 欄位 | 類型 | 說明 |
|---|---|---|
| `id` | 整數 | 數值功能識別碼 |
| `key` | 字串 | 功能鍵 |
| `featureGroupKey` | 字串？ | 功能群組索引鍵（可用時） |
| `meta` | 字串？ | 不透明功能中繼資料（可用時） |
| `analyticsParam` | AnalyticsParam？ | 已評估功能的Analytics詳細資料 |

*AnalyticsParam*

| 欄位 | 類型 | 說明 |
|---|---|---|
| `featureGroupId` | 整數 | 數值功能群組識別碼 |
| `featureId` | 整數 | 數值功能識別碼 |
| `variantId` | 字串？ | 變體識別碼 |

**範例**

*Swift*

```swift
import AEPFlags

Flag.getFeature(
    "new-flag",
    evaluationContext: ctx
) { feature in
    guard let meta = feature?.meta, !meta.isEmpty else {
        // No metadata available: fall back to the default behavior
        return
    }
    // Feature metadata is available: use it to drive the feature behavior
}
```

*Objective-C*

```objc
@import AEPFlags;

[AEPMobileFlag getFeature:@"new-flag"
        evaluationContext:ctx
                completion:^(AEPFeatureEvaluationResult * _Nullable feature) {
    NSString *meta = feature.meta;
    if (meta.length > 0) {
        // Feature metadata is available: use it to drive the feature behavior
    } else {
        // No metadata available: fall back to the default behavior
    }
}];
```

### extensionVersion {#extension-version}

傳回Flags副檔名的版本字串。

**語法**

*Swift*

```swift
static var extensionVersion: String
```

*Objective-C*

```objc
+ (nonnull NSString *)flagExtensionVersion;
```

**範例**

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
| `isFeatureEnabled(_:evaluationContext:completion:)`. `FeatureEvaluationContext`攜帶規則的鎖定目標屬性。 請參閱[isFeatureEnabled](#is-feature-enabled)。 | 透過完成關閉的布林值 |
| `getFeature(_:evaluationContext:completion:)`. 傳回給定內容的評估功能裝載。 請參閱[getFeature](#get-feature)。 | FeatureEvaluationResult？ 透過關閉 |
| `extensionVersion` | 字串 |

## 另請參閱 {#see-also}

* [行動應用程式](../../integrate/mobile-applications.md)
* [SDK](../../integrate/sdks.md)
* [Android擴充功能整合指南](../android/android-extension-integration-guide.md)

<!-- -->
