---
title: 目標
description: 瞭解如何在Journey Optimizer B2B Prime中連線目的地並啟用靜態人員清單，以將受眾資料匯出至廣告、電子郵件和其他行銷平台。
autotag-review: '2026-06-17T18:30:02.442Z'
TQID: 'https://experienceleague.adobe.com/xO1p-VvIfv1KB77g0l2-fFRHQ0w2hy97vnG1QHpMw8c'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2:
  - id: aed878b8-11d0-487c-828b-d23b2051ec37
  - id: beb5f4be-cec3-471a-9db6-831a77dd3ac9
  - id: c8f3fb27-3167-48ac-a66a-fa4bc3f58dda
subfeature_v2:
  - id: d270a788-eb1d-40ed-b74e-9158ed975b1f
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 1cb68e8933d6b1abba3cc82f154344d1dde51818
workflow-type: tm+mt
source-wordcount: 289
ht-degree: 2%

---

# 目標

目的地是預先建立的整合，可讓您將人員清單資料從[!DNL Adobe Journey Optimizer B2B Prime]匯出至外部行銷平台，例如廣告網路、電子郵件服務提供者及CRM系統。 在[!DNL Journey Optimizer B2B Prime]中，您對目的地啟用[靜態人員清單](./people-lists.md#static-list) （由Marketo Engage人員記錄組成），以便這些對象可用於下游管道中的目標定位和參與。

<!-- 
Does not align w/AEP info for Beta

Activating a static list to a destination follows a three-step process:

1. **Connect** — Authenticate and configure a connection to a destination platform.
1. **Map** — Select the static list and map its people attributes to the fields required by the destination.
1. **Schedule** — Define when and how often the list data is exported to the destination.

Destination activations reflect the membership state of the static list at the time of each synch.

## Destination types {#destination-types}

[!DNL Journey Optimizer B2B Prime] supports the following destination types for activating static people lists:

| Type | Description |
|--- |--- |
| Streaming | Real-time API-based connections that push audience membership updates to the destination as they occur. |
| File-based (batch) | Scheduled exports that deliver audience data as structured files to cloud storage or SFTP locations, which the destination platform then ingests. |

-->

## 連線到目的地 {#connect-destination}

1. 在左側導覽列中，展開&#x200B;**[!UICONTROL 連線]**&#x200B;並選取&#x200B;**[!UICONTROL 目的地]**。

1. 在&#x200B;_[!UICONTROL 目錄]_&#x200B;索引標籤中，找出外部目的地型別聯結器。

   >[!TIP]
   >
   >您可以在搜尋方塊中輸入名稱（例如`LinkedIn`）來快速尋找聯結器。

   ![存取可用的聯結器型別](./assets/destinations-catalog.png){width="800" zoomable="yes"}

1. 在聯結器卡中，按一下&#x200B;**[!UICONTROL 設定新的目的地]**。

1. 選取&#x200B;**[!UICONTROL 新帳戶]**&#x200B;並輸入您的帳戶認證。

   ![連線新的目的地帳戶](./assets/destinations-configure-new.png){width="500"}

1. 按一下&#x200B;**[!UICONTROL 連線到目的地]**。

   >[!IMPORTANT]
   >
   >此時，**不要**&#x200B;輸入&#x200B;_[!UICONTROL 目的地詳細資料]_。 只需要連線。

1. 檢閱資料控管和行銷動作設定，然後按一下[儲存]。**&#x200B;**

連線的目的地會顯示在&#x200B;_[!UICONTROL 瀏覽]_&#x200B;索引標籤上的清單中，並可用於靜態清單啟用。

## 對目的地啟用靜態清單 {#activate}

>[!NOTE]
>
>只有[靜態人員清單](./people-lists.md#static-list)可在[!DNL Journey Optimizer B2B Prime]中啟用至目的地。 [動態清單](./people-lists.md#dynamic-lists)不符合目的地啟用的資格。

1. 在左側導覽列中，展開&#x200B;**[!UICONTROL 行銷管理]**。

1. 在&#x200B;**[!UICONTROL 行銷]**&#x200B;資源清單的右側，選取&#x200B;**[!UICONTROL 人員清單]**。

   ![存取人員清單以管理您的對象](./assets/people-lists.png){width="800" zoomable="yes"}

1. 選取&#x200B;**[!UICONTROL 靜態清單]**&#x200B;索引標籤。

1. 找出您要啟用至目的地的靜態清單。

1. 按一下靜態清單名稱旁的&#x200B;_啟動_ （ ![啟動圖示](../../assets/do-not-localize/icon-falco-activate-dest.svg) ）圖示。

1. 選取已設定之目的地連線的核取方塊。

   ![可供啟用的已設定目的地](./assets/static-list-activate-destination-select.png){width="600" zoomable="yes"}

1. 按一下&#x200B;**[!UICONTROL 儲存]**。

<!--

This method not working for Beta

1. On the _[!UICONTROL Browse]_ tab, locate the destination you want to use for the activation and click the name to open it.

1. Select the **[!UICONTROL Activation data]** tab.

1. Click **[!UICONTROL Activate people lists]**.

1. Select the static people list you want to export and click **[!UICONTROL Next]**.

1. Map the people list attributes to the required fields of the destination schema and click **[!UICONTROL Next]**.

1. Set the export schedule:

   * **[!UICONTROL Frequency]** — Choose how often the list is exported (for example, daily or weekly).
   * **[!UICONTROL Start date]** — Set when the first export should run.

1. Review the activation summary and click **[!UICONTROL Finish]**.

The activation is created and the static list data is exported to the destination according to the defined schedule.

-->
