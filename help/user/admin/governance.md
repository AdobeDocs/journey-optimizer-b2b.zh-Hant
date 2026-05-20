---
title: 治理功能
description: 瞭解目前可在Journey Optimizer B2B edition中使用的治理功能。
feature: Setup
role: Admin
exl-id: 2845272b-987c-4a37-adf4-6ee5bfd59fc0
product_v2: id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2: id: d6e625c1-468f-4d73-9f32-fd1edb87f96bid: f2da1b69-6919-4386-a5d2-9c7b5c9033db
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
autotag-review: 2026-03-27T23:18:44.352Z
TQID: https://experienceleague.adobe.com/PwH34suDPc84nB9eiAWtrkVzsOw82RRGw4hrRogf9zE
source-git-commit: d7e971b6d533a173632224baa359f7559b865497
workflow-type: tm+mt
source-wordcount: 419
ht-degree: 0%

---

# 治理功能

Journey Optimizer B2B edition是一款整合的Adobe Experience Platform應用程式。 它採用多種工具和服務，根據您的業務實務、法律義務和開發流程，控制您收集的體驗資料。 以下各節提供這些治理功能的摘要。

## 隱私權 — GDPR

Journey Optimizer B2B edition使用Privacy Service和Marketo Engage隱私權代理人服務所提供的現有Marketo GDPR控管功能。

## 角色型存取控制(RBAC)

透過Journey Optimizer B2B edition和Adobe Admin Console的存取權，管理員可以授予使用者對實體型別（檢視區段、管理區段、管理歷程等）的許可權。 此功能是Unified Permissions Framework (UPF)的一部分，可讓所有Adobe Experience Platform客戶定義和管理其組織的角色和許可權。

## 資料加密

**_靜態資料加密_** — 從Adobe Experience Platform傳輸到Journey Optimizer B2B edition的所有帳戶和人員設定檔資料都已加密，以維持Experience Platform的現有合規性。 源自Journey Optimizer B2B edition的所有實體（例如歷程和購買群組）也經過加密。

**_傳輸中資料的加密_** （透過公用網路） — 所有Journey Optimizer B2B edition API和實體都使用TLS 1.2進行傳輸中加密。

## 同意選擇加入/選擇退出

Journey Optimizer B2B edition會讀取儲存在Adobe Experience Platform XDM設定檔中的個人同意偏好設定，並在電子郵件、簡訊和WhatsApp通道的訊息傳送時強制執行。 從頻道或下游傳訊提供者傳送內容之前，會先將選擇退出頻道的人排除在傳送之外。

使用設定檔同意欄位群組的XDM欄位，在傳送時評估同意。 預設同意行為因管道而異 — 未設定偏好設定時，電子郵件預設為選擇加入，而SMS和WhatsApp預設為選擇退出。

如需針對每個管道評估的XDM屬性及其預設行為的詳細資訊，請參閱[同意偏好設定](../content/channels-consent-preferences.md)。

## 沙箱已重設

沙箱重設為&#x200B;**目前不支援**&#x200B;用於Adobe Journey Optimizer B2B edition。 重設或刪除對應至Journey Optimizer B2B edition的沙箱可能會導致永久資料遺失，並需要布建新的執行個體。

## 尚未提供

下列治理功能尚無法使用：

* 資料使用標籤實作(DULE) /使用原則
* 資料衛生
* 同意原則
* 欄位層級存取控制(FLAC)
* 物件層級存取控制(OLAC)
* 靜態資料的CMK加密
* 平台稽核服務
