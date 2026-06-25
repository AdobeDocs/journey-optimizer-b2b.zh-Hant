---
title: 個人受眾歷程節點
description: 在Journey Optimizer B2B中設定「人員」對象節點，指定哪些設定檔會使用動態人員清單或事件型對象來進入歷程。
badgeBeta: label="Beta" type="informative" tooltip="此功能目前在有限測試版中提供"
autotag-review: '2026-06-16T21:21:01.614Z'
TQID: 'https://experienceleague.adobe.com/pk1NGg3M67oRieuCOZFdaguKl2bVkiZyEPVnJDTUBJs'
product_v2: id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2: id: a4b836d9-ffdd-4df3-a62a-f78b830cf059id: beb5f4be-cec3-471a-9db6-831a77dd3ac9id: aed878b8-11d0-487c-828b-d23b2051ec37
subfeature_v2: id: ba367494-9862-4596-bd6f-299c7e10a46bid: d270a788-eb1d-40ed-b74e-9158ed975b1f
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: a48a12635d2ba4f14dda49e25e79a5496ebbdecf
workflow-type: tm+mt
source-wordcount: 226
ht-degree: 4%

---

# 個人受眾節點

_個人對象_&#x200B;節點會指定哪些人員設定檔進入歷程。 當您[建立個人歷程](./person-journeys.md)時，歷程一律以定義其輸入的個人對象節點開始。 「人員」對象節點可以有下列兩種對象輸入型別之一：靜態人員清單或動態人員清單。

如果您需要的人員歷程動態人員清單不存在，請[建立人員清單](../audiences/people-lists.md#create-a-people-list)，然後設定人員對象節點。

設定歷程對象(_T):_

1. 按一下&#x200B;**[!UICONTROL 個人對象]**&#x200B;節點。

   此動作會在右側顯示節點屬性。

   ![個人受眾歷程節點](./assets/person-audience-node-properties.png){width="500" zoomable="yes"}

1. 對個人對象使用下列其中一個對象設定選項：

   * **[!UICONTROL 動態清單]** — 使用以規則為基礎的動態人員清單。 清單規則會在歷程執行階段進行評估，以符合歷程成員的資格。 之後不符合動態清單資格的人不會從歷程中移除。 請參閱&#x200B;_[動態清單](../audiences/people-lists.md#dynamic-lists)_。

   * **[!UICONTROL 事件對象]** — 使用事件對象，根據合格事件定義歷程對象。 使用個人資料篩選定義對象成員，並使用事件條件觸發歷程專案。 請參閱&#x200B;_[事件型對象](../audiences/event-based-audiences.md)_。
