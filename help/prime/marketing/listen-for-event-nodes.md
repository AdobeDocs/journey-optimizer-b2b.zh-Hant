---
title: 接聽事件節點
description: 在Journey Optimizer B2B edition Prime中設定監聽事件節點 — 設定事件觸發器、套用選用篩選器，並在活動或資料變更發生時提升人員。
autotag-review: '2026-06-12T23:00:36.531Z'
TQID: 'https://experienceleague.adobe.com/SBEfrrIKSCnO5x1tGXQTz1EZryH0IKhQx4tuqVn78FI'
product_v2: id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2: id: a4b836d9-ffdd-4df3-a62a-f78b830cf059id: aed878b8-11d0-487c-828b-d23b2051ec37
subfeature_v2: id: d0031543-532c-4a26-8f90-01af2b91e6d0id: ba367494-9862-4596-bd6f-299c7e10a46bid: d270a788-eb1d-40ed-b74e-9158ed975b1f
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 3368f815edc0ce817cb7ed371157b63fa548d848
workflow-type: tm+mt
source-wordcount: 233
ht-degree: 8%

---

# 接聽事件節點

新增&#x200B;_接聽事件_&#x200B;節點，以便在事件發生時，將您的對象移至歷程的下一個步驟。

## 事件觸發程式 {#event-triggers}

從PM取得清單

## 事件篩選器 {#event-filters}

從PM取得更新清單

| 篩選器 | 說明 |
| ------- | ----------- |
| 活動歷史記錄>電子郵件 | 根據使用一或多封所選電子郵件訊息評估的條件，以電子郵件活動為基礎： <li>電子郵件中已點選的連結 <li>開啟電子郵件 |
| 活動歷史記錄>資料值已變更 | 針對選取的人員屬性，發生值變更。 這些變更型別包括： <li>新值 <li>上一個值 <li>原因 <li>來源 <li>活動日期 <li> 最低 次數 |

## 新增事件節點 {#add-event-node}

1. 導覽至歷程畫布。

1. 按一下路徑上的加號( **+** )圖示，然後選擇&#x200B;**[!UICONTROL 接聽事件]**。

   ![按一下歷程路徑上的新增圖示](./assets/person-journey-canvas-add-node.png){width="200"}

1. 在右側的節點屬性中，按一下&#x200B;**[!UICONTROL 新增事件條件]**。

1. 在&#x200B;_[!UICONTROL 編輯事件]_&#x200B;對話方塊中，新增要觸發的事件。

   ![編輯事件 — 事件觸發程式](./assets/edit-event-triggers.png){width="600" zoomable="yes"}

1. （選擇性）在對話方塊中選取&#x200B;**[!UICONTROL 篩選器]**&#x200B;索引標籤，並為觸發程式新增篩選准則。

1. 按一下&#x200B;**[!UICONTROL 編輯事件]**&#x200B;並定義事件的詳細資料。

   ![編輯事件 — 事件篩選](./assets/edit-event-filters.png){width="600" zoomable="yes"}

1. 按一下&#x200B;**[!UICONTROL 儲存]**。

<!--
1. If needed, set the **[!UICONTROL Timeout]** option to limit the time period to listen for the event.

   >[!NOTE]
   >
   >The journey ends after a timeout unless you define a timeout path, where you can add other nodes.

   Enable the **[!UICONTROL Timeout]** option and select the duration for which the journey waits for an event to occur before it times out.

   You can choose to end the path here or take a different course of action by setting another path. To create a new path in the journey where you can add actions and events applicable to accounts when the event does not occur, select the **[!UICONTROL Set timeout path]** check box.

   ![Journey event node - set timeout path](../../user/journeys/assets/node-event-timeout-set-path.png){width="700" zoomable="yes"}
-->

>[!NOTE]
>
>監聽事件節點的逾時功能目前無法運作。 已規劃於更高版本中推出。
