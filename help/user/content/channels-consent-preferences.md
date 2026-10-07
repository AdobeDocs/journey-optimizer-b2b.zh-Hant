---
title: 頻道傳訊同意
description: 瞭解Journey Optimizer B2B Edition如何讀取AEP XDM設定檔同意偏好設定，並強制在電子郵件、簡訊和WhatsApp管道的訊息傳送時間選擇加入和選擇退出。
feature: Setup, Channels
role: Admin, User
autotag-review: '2026-05-19T16:18:37.228Z'
TQID: 'https://experienceleague.adobe.com/-c0dJnpfiIcj0B5gViyEQ7E1Ws0BwP864OLF003rOjw'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: a4b836d9-ffdd-4df3-a62a-f78b830cf059
    internal-label: Journeys
  - id: f01b5556-e951-40ba-8625-2e3001864f2b
    internal-label: Communication channels
  - id: d77af7eb-afc3-53f3-a50c-dabc0d05ecfd
    internal-label: Channels
  - id: d6e625c1-468f-4d73-9f32-fd1edb87f96b
    internal-label: Administration
subfeature_v2:
  - id: ff0c35fa-aa7e-4050-a37c-198fcacd09e6
    internal-label: Email channel
  - id: a22f05f6-0fcf-40c0-a70e-e13a3db185f7
    internal-label: SMS channel
  - id: f6df9def-cdf7-4728-9ec8-3f65716828c7
    internal-label: Setup
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
source-git-commit: 21fbce544faf291ad01a3301a9981add95442097
workflow-type: tm+mt
source-wordcount: '415'
ht-degree: 1%
---
# 頻道傳訊同意

Adobe Journey Optimizer B2B Edition會讀取儲存在Adobe Experience Platform XDM設定檔中的個人同意偏好設定，並在訊息傳送時強制執行，做為應用程式[治理控制項](../admin/governance.md)的一部分。 從頻道或下游傳訊提供者傳送內容之前，會先將選擇退出頻道的人排除在傳送之外。

以下小節說明Journey Optimizer B2B Edition如何在每個支援的管道中評估訊息傳送時的同意情形。

## 電子郵件 {#email}

在[電子郵件通道](../admin/configure-channels-emails.md)上傳送訊息時，Journey Optimizer B2B Edition會評估下列XDM屬性以取得電子郵件同意：

| XDM屬性 | `y` | `n` | 沒有值 |
| --- | --- | --- | --- |
| `consents.marketing.email.val` | 已選擇加入 | 已選擇退出 | 已選擇加入 |

如需電子郵件同意，請考慮下列事項：

* 全域選擇退出電子郵件的使用者可接收標示為可操作的電子郵件。
* 不支援訂閱層級的偏好設定。

若要檢閱已傳送電子郵件的取消訂閱活動，請參閱[電子郵件效能報表](../dashboards/email-performance-dashboard.md)。

## 簡訊 {#sms}

透過[SMS通道](../admin/configure-channels-sms.md)傳送訊息時，Journey Optimizer B2B Edition會評估下列XDM屬性以取得SMS同意：

| XDM屬性 | `y` | `n` | 沒有值 |
| --- | --- | --- | --- |
| `consents.marketing.sms.val` | 已選擇加入 | 已選擇退出 | 已選擇退出 |
| `consents.marketing.subscriptions.<senderID>` | 已選擇加入 | 已選擇退出 | 已選擇退出 |
| `consents.marketing.sms.subscriptions.<senderId>.subscribers.<phoneNumber>` | 已選擇加入 | 已選擇退出 | 已選擇退出 |

請考慮下列專案以取得簡訊同意：

* 當銷售機會（人員）記錄退出簡訊時，該記錄會完全排除，並且不會傳遞給下游簡訊提供者。
* 可用時，會評估訂閱層級的同意。 無法取得訂閱層級的同意時，系統會以全域選擇退出作為遞補。
* 選擇退出簡訊的人員仍可接收標示為可操作的訊息。
* 如果多個潛在客戶記錄共用相同的電話號碼，則會共用相同的選擇加入或選擇退出狀態。

## WhatsApp {#whatsapp}

透過已設定的[WhatsApp通道](../admin/configure-channels-whatsapp.md)傳送訊息時，Journey Optimizer B2B Edition會針對WhatsApp同意評估下列XDM屬性：

| XDM屬性 | `y` | `n` | 沒有值 |
| --- | --- | --- | --- |
| `consents.marketing.whatsApp.val` | 已選擇加入 | 已選擇退出 | 已選擇退出 |
| `consents.idSpecific.Phone.<number>.marketing.whatsApp.val` | 已選擇加入 | 已選擇退出 | 已選擇退出 |

如需WhatsApp同意，請考慮下列事項：

* 如果全域WhatsApp屬性值(`consents.marketing.whatsApp.val`)存在，則會用來進行同意評估。
* 如果全域屬性值不存在，但存在寄件者特定專案，則會使用寄件者特定專案進行同意評估。
* 如果任一屬性都沒有值，則會將人員視為選擇退出。

## 不支援 {#not-supported}

Journey Optimizer B2B Edition目前不支援下列與同意相關的功能：

* AEP同意原則
* 行銷偏好屬性(`consents.marketing.preferred`)
