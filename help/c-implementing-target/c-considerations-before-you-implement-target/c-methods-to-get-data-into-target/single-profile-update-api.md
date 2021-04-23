---
keywords: 實施；實施；設定；設定；設定；單個配置檔案更新
description: 使用單一描述檔更新API將資料匯入 [!DNL Target] 。
title: 如何使用單一描述檔更新API將資料匯入 [!DNL Target] ?
feature: 實施
role: Developer
exl-id: 8331866c-0b84-4d08-83b4-f7f82c67cd21
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 41%

---

# 單一設定檔更新 API

幾乎與「大量描述檔更新API」相同，但每次會更新一個訪客描述檔，並以API呼叫的行式，而非。csv檔案。

## 格式

必須透過 Target mboxPC 值或 mboxThirdPartyId 值來識別訪客。不支援 Experience Cloud ID (ECID)。

## 範例使用案例

您想在訪客執行離線動作時即時更新Target。 行動可包括到達客服中心、提供貸款、使用店內忠誠卡、存取資訊站等。

## 方法的優點

設定檔屬性的數量不限。

透過網站傳送的設定檔屬性可以透過 API 更新，反之亦然。

## 注意事項

24 小時期間內以 1,000,000 次 API 呼叫 (1 百萬) 為限制。

只更新設定檔。無法為 Target 尚未看到的潛在使用者建立設定檔。

## 程式碼範例

GET與POST。`https://CLIENT.tt.omtrdc.net/m2/client/profile/update?mboxPC=1368007744041-575948.01_00&profile.attr1=0&profile.attr2=1...`

## 相關資訊的連結

[更新設定檔](https://developers.adobetarget.com/api/#updating-profiles)
