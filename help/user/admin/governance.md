---
title: 治理功能
description: 瞭解目前可在Journey Optimizer B2B edition中使用的治理功能。
exl-id: 2845272b-987c-4a37-adf4-6ee5bfd59fc0
source-git-commit: 3198ba223125c95263d8dcf5ee8cb285a888a26a
workflow-type: tm+mt
source-wordcount: '413'
ht-degree: 0%

---

# 治理功能

Journey Optimizer B2B edition是一款整合的Adobe Experience Platform應用程式。 它採用多種工具和服務，根據您的業務實務、法律義務和開發流程，控制您收集的體驗資料。 以下各節提供這些治理功能的摘要。

## 隱私權 — GDPR

Journey Optimizer B2B edition採用Privacy Service及Marketo隱私權代理人服務所提供的現有Marketo EngageGDPR控管功能。

## 角色型存取控制(RBAC)

透過Journey Optimizer B2B edition和Adobe Admin Console的存取權，管理員可以授予使用者對實體型別（檢視區段、管理區段、管理歷程等）的許可權。 此功能是Unified Permissions Framework (UPF)的一部分，可讓所有Adobe Experience Platform客戶定義和管理其組織的角色和許可權。

## 資料加密

**_靜態資料加密_** — 從Adobe Experience Platform傳輸到Journey Optimizer B2B edition的所有帳戶和人員設定檔資料都已加密，以維持Experience Platform的現有合規性。 源自Journey Optimizer B2B edition的所有實體（例如歷程和購買群組）也經過加密。

**_傳輸中資料的加密_** （透過公用網路） — 所有Journey Optimizer B2B edition API和實體都使用TLS 1.2進行傳輸中加密。

## 同意選擇加入/選擇退出

同意選擇加入/選擇退出是一種治理形式，其中設定檔可以選擇退出通訊頻道，例如電子郵件或簡訊，然後設定檔會從通訊頻道中排除。

透過Journey Optimizer B2B edition，您可以建立並管理電子郵件和簡訊傳遞使用案例的訂閱/取消訂閱使用案例。 這些同意偏好設定會儲存在XDM設定檔同意欄位群組中，並做為資料同步架構的一部分，同步至Journey Optimizer B2B edition或從中取得。 這些偏好設定會在傳送時使用，以從傳送中排除選擇退出的設定檔。

## 沙箱已重設

沙箱重設為&#x200B;**目前不支援**&#x200B;用於Adobe Journey Optimizer B2B edition。 重設或刪除對應至Journey Optimizer B2B edition的沙箱可能會導致Journey Optimizer B2B edition中的資料永久遺失，並且可能須布建新的Journey Optimizer B2B edition執行個體。

## 尚未提供

下列治理功能尚無法使用：

* 資料使用標籤實作(DULE) /使用原則
* 資料衛生
* 同意原則
* 欄位層級存取控制(FLAC)
* 物件層級存取控制(OLAC)
* 靜態資料的CMK加密
* 平台稽核服務
