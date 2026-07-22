---
title: 啟動指南
description: 請依照下列步驟，從請求存取權到建立您的第一個功能標幟，讓您的應用程式與標幟整合。
badge: label="Beta" type="Informative"
hide: true
exl-id: 7aa09535-45fa-4ddf-9e3f-a23f8a8ee666
source-git-commit: 339de89fff7bb14eb8146d42482b30c86feeedef
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 1%

---

# 啟動指南 {#startup-guide}

請依照下列步驟，將旗標整合至您的應用程式。

## 步驟1：要求存取權 {#step-1-access}

請求存取旗標主控台並加入您的團隊。 如需逐步指示，請參閱[要求存取權](../console/request-access.md)。

## 步驟2：啟動您的應用程式 {#step-2-onboard}

取得存取權後，請登入Flags主控台，並確認您的應用程式列在您的團隊底下。 如果沒有，請要求您的團隊管理員新增它。 請參閱[將您的應用程式上線](../applications/onboard-your-application.md)。

上線之前，請準備以下內容：

| 需求 | 詳細資料 |
|---|---|
| **應用程式識別碼** | 呼叫旗標API時使用的唯一使用者端識別碼。 在可用的情況下，使用您應用程式現有的使用者端ID。 |

## 步驟3：取得環境檔案ID {#step-3-credentials}

您需要的環境檔案ID取決於您的整合路徑：

* **網頁和行動裝置（以標籤為基礎）：**&#x200B;使用您發佈的標籤屬性中的&#x200B;**環境檔案識別碼**。 請參閱步驟4a以瞭解如何取得此資訊。

## 步驟4：使用SDK整合 {#step-4-integrate}

請遵循應用程式型別的整合指南。 選擇適合您棧疊的路徑：

* **網頁和行動應用程式** — 請參閱整合指南區段中的[Android](../sdk-releases/android/android-extension-integration-guide.md)、[iOS](../sdk-releases/ios/ios-extension-integration-guide.md)和[網頁](../sdk-releases/web/web-extension-integration-guide.md)指南

## 步驟4a：設定資料收集並發佈您的設定 {#step-4a-data-collection}

如果您透過標籤式方法（網頁或行動裝置）進行整合，請在初始化SDK之前設定標籤屬性：

1. 在[Adobe Experience Platform Data Collection](https://experience.adobe.com/#/data-collection)中，建立[標籤屬性](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/tags/get-started/quick-start) （如果尚未建立），或使用現有的標籤屬性。
1. 開啟行動或Web標籤屬性，並移至[擴充功能](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/tags/ui/extensions/overview)。
1. 安裝並設定&#x200B;**Edge Network**&#x200B;擴充功能。 然後安裝&#x200B;**Flags**&#x200B;擴充功能。
1. 選取&#x200B;**資料流** （必須包含Customer Journey Analytics資料集）並設定Edge網域。
1. 透過&#x200B;**Dev → Staging → Production**&#x200B;發佈設定。
1. 從&#x200B;**環境**&#x200B;索引標籤複製&#x200B;**環境檔案ID** — 您將使用此項初始化SDK。

>[!IMPORTANT]
>
>在&#x200B;**暫存**&#x200B;環境中，在環境檔案識別碼前面加上`staging/` — 也就是使用`staging/<environmentId>`。 在&#x200B;**生產**&#x200B;中，直接使用環境檔案ID。

## 步驟5：建立並測試您的第一個功能標幟 {#step-5-feature-flag}

整合完成後，請在主控台中建立您的第一個功能標幟並進行測試：

* [建立您的第一個功能標幟](../feature-flags/create-your-first-feature-flag.md)

## 另請參閱 {#see-also}

* [在應用程式中整合標幟](integrating-in-your-app.md)
* [SDK](sdks.md)

<!-- -->
