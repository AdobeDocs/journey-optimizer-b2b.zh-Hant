---
title: 治理功能
description: 瞭解目前可在Journey Optimizer B2B Edition中使用的治理功能。
exl-id: 2845272b-987c-4a37-adf4-6ee5bfd59fc0
source-git-commit: 78d82aa8b3bb8b8d432eeb187d75e2354dbff3ee
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 1%

---

# 治理功能

Journey Optimizer B2B Edition是一款整合式Adobe Experience Platform應用程式，可運用數種服務和工具，讓您安心控制收集的體驗資料，以符合業務實務、法律義務和開發程式。 以下各節提供這些治理功能的摘要。

## 隱私權 — GDPR

Journey Optimizer B2B版本使用Privacy Service及Marketo隱私權代理人服務所提供的現有Marketo EngageGDPR控管功能。

## 角色型存取控制(RBAC)

透過Journey Optimizer B2B版本和Adobe Admin Console的存取權，管理員可以授予使用者對實體型別（檢視區段、管理區段、管理歷程等）的許可權。 此功能是Unified Permissions Framework (UPF)的一部分，可讓所有Adobe Experience Platform客戶定義和管理其組織的角色和許可權。

## 資料加密

**_靜態資料加密_** — 從Adobe Experience Platform傳輸到Journey Optimizer B2B Edition的所有帳戶和人員設定檔資料都已加密，以維護Experience Platform的現有合規性。 源自於Journey Optimizer B2B Edition的所有實體（例如歷程及購買群組）也會經過加密。

**_傳輸中資料的加密_** （透過公用網路） — 所有Journey Optimizer B2B Edition API和實體都使用TLS 1.2進行傳輸中加密。

## 同意選擇加入/選擇退出

同意選擇加入/選擇退出是一種治理形式，其中設定檔可以選擇退出通訊頻道，例如電子郵件或簡訊，然後設定檔應從此類通訊頻道中排除。

使用Journey Optimizer B2B Edition，您可以為電子郵件和簡訊傳遞使用案例建立和管理訂閱/取消訂閱使用案例。 這些同意偏好設定儲存在XDM設定檔同意欄位群組中，並會隨著Data Sync Framework同步至Journey Optimizer B2B Edition和從中同步。 這些偏好設定會在傳送時使用，以從傳送中排除選擇退出的設定檔。

## 尚未提供

下列治理功能尚未提供，但已納入產品藍圖中：

* 資料使用標籤實作(DULE) /使用原則
* 資料衛生
* 沙箱已重設
* 同意原則
* 欄位層級存取控制(FLAC)
* 物件層級存取控制(OLAC)
* 靜態資料的CMK加密
* 平台稽核服務
