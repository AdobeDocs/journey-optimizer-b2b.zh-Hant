---
title: 執行動作節點
description: 預留位置
autotag-review: '2026-06-12T22:58:21.806Z'
TQID: 'https://experienceleague.adobe.com/uR-WvNz3gA6V7yyN3RRXH-MggrmGb1qvu1CBhMZRuAc'
product_v2: id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2: id: a4b836d9-ffdd-4df3-a62a-f78b830cf059id: aed878b8-11d0-487c-828b-d23b2051ec37
subfeature_v2: id: af7eab5e-3580-4254-9f56-3c20b4f6ef42id: d270a788-eb1d-40ed-b74e-9158ed975b1f
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: bf2854a777f62ba2f74f79942ee3336b6e8ab9dd
workflow-type: tm+mt
source-wordcount: 197
ht-degree: 2%

---

# 執行動作節點

在人員歷程中，當您想要將變更套用至節點路徑上的所有人員時，可對人員使用動作。 對於帳戶歷程，此節點型別可用於依人員分割路徑或依帳戶分割路徑。

## 動作和限制

| 動作 | 限制 |
| ------ | ---------- |
| **[!UICONTROL 傳送電子郵件]** | <li>建立電子郵件 <li>傳送時間最佳化（選擇性） |
| **[!UICONTROL 變更資料值]** | <li>選取人員屬性 <li>設定新值 |

## 新增動作節點 {#add-an-action-node}

1. 導覽至歷程圖。

1. 按一下路徑上的加號( **+** )圖示，然後選擇&#x200B;**[!UICONTROL 執行動作]**。

1. 在右側的節點屬性中，從清單中選取動作，並設定該動作的任何值。

<!-- ![Person journey node - take an action](./assets/node-take-action-people.png){width="700" zoomable="yes"} -->

+++[!UICONTROL 傳送電子郵件]

使用此動作傳送電子郵件。 建立節點的電子郵件之後，您可以在電子郵件設計空間設計、個人化和預覽電子郵件訊息（請參閱[電子郵件編寫](../content/email-authoring.md)）。

<!-- ![Take an action - Send email](./assets/node-action-send-email-from-marketo.png){width="300"} -->

您可以使用[傳送時間最佳化](../marketing/email-send-time-optimization.md)，透過預測每個設定檔最有可能參與的時間來個人化電子郵件傳遞時間。

<!--
>[!NOTE]
>
>You can use email deduplication in account journeys to ensure that the same email is not sent multiple times to the same email address within a journey. For more information, see [Email deduplication](../content/email-deduplication.md).
-->

+++

+++[!UICONTROL 變更資料值]

使用此動作來變更資料庫中人員設定檔屬性的值。 選取屬性，然後設定新值。

<!-- ![Take an action - Update person profile](./assets/node-action-update-person-profile.png){width="300"} -->

+++
