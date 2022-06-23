---
keywords: 實施；實施；設定；設定；單個配置檔案更新
description: 將資料 [!DNL Target] 使用單個配置檔案更新API。
title: 如何將資料 [!DNL Target] 是否使用單個配置檔案更新API?
feature: Implementation
role: Developer
exl-id: 8331866c-0b84-4d08-83b4-f7f82c67cd21
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 44%

---

# 單一設定檔更新 API

幾乎與批量配置檔案更新API相同，但每次更新一個訪問者配置檔案，在API調用中排行，而不是使用.csv檔案。

## 格式

必須透過 Target mboxPC 值或 mboxThirdPartyId 值來識別訪客。不支援 Experience Cloud ID (ECID)。

## 範例使用案例

當訪問者執行某些離線操作時，您需要即時更新目標。 行動可以包括到達呼叫中心、為貸款提供資金、使用商店中的會員卡、訪問亭子等。

## 方法的益處

設定檔屬性的數量不限。

透過網站傳送的設定檔屬性可以透過 API 更新，反之亦然。

## 注意事項

24 小時期間內以 1,000,000 次 API 呼叫 (1 百萬) 為限制。

只更新設定檔。無法為 Target 尚未看到的潛在使用者建立設定檔。

## 代碼示例

GET和POST支援。 `https://CLIENT.tt.omtrdc.net/m2/client/profile/update?mboxPC=1368007744041-575948.01_00&profile.attr1=0&profile.attr2=1...`

>[!MORELIKETHIS]
>
>* [更新設定檔](https://developers.adobetarget.com/api/#updating-profiles)

