---
title: 動態人員清單
description: 在Journey Optimizer B2B Edition中定義成員資格規則和重複的動態人員清單。
feature: Audiences
role: User
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: beb5f4be-cec3-471a-9db6-831a77dd3ac9
    internal-label: Audiences
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: ff2b9b37-92e0-45fc-b853-379d44c08c89
    internal-label: Audience segmentation
source-git-commit: 734966636b6d2addf014905431fa755f6fe92ee6
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 2%
---

# 動態人員清單

動態[人員清單](./people-lists.md)是由規則（篩選器）定義的人員設定檔集合。 動態清單成員資格是使用參考個人屬性和活動的簡單篩選器來定義。 當設定檔根據篩選邏輯符合資格和取消資格時，會自動維護成員資格。

您無法從動態清單新增或移除個別人員。 若要變更清單成員資格，請更新其規則。 如果您需要手動或透過歷程管理成員資格，請改用[靜態清單](./people-lists-static.md)。

## 設定成員資格規則 {#set-membership-rules}

>[!NOTE]
>
>沒有規則的動態清單沒有成員。 若要填入清單，請至少新增一個篩選器。

1. 開啟動態清單並選取&#x200B;**[!UICONTROL 規則]**&#x200B;標籤。

1. 按一下&#x200B;**[!UICONTROL 編輯規則]**。

   ![建立動態人員清單的存取規則](./assets/people-list-dynamic-rules-edit.png){width="700" zoomable="yes"}

1. 在&#x200B;_[!UICONTROL 編輯規則]_&#x200B;對話方塊中，從左側面板拖曳篩選器，定義用於限定設定檔的規則。

   使用下列任一組合來限定清單的設定檔：

   * 活動歷史記錄
   * [!DNL Experience Platform]啟用的人員欄位
   * 自訂欄位
   * 意圖資料
   * 人員屬性
   * 特殊篩選器，例如歷程成員資格

   針對您新增的每個篩選器，按一下&#x200B;**[!UICONTROL 新增限制]**&#x200B;以調整符合條件。 在上方套用&#x200B;**[!UICONTROL 篩選邏輯]**，微調條件。 您可以選擇符合所有條件、任何條件，或定義進階邏輯。

   ![新增包含限制的篩選器以填入動態清單](./assets/people-list-dynamic-rules-edit-filter.png){width="700" zoomable="yes"}

1. 按一下&#x200B;**[!UICONTROL 完成]**&#x200B;以儲存變更。

   **[!UICONTROL 規則]**&#x200B;索引標籤會顯示清單的篩選和篩選邏輯，而&#x200B;**[!UICONTROL 成員]**&#x200B;索引標籤會重新整理以反映更新的成員資格。 若要尋找最新的對象資格，請使用&#x200B;**[!UICONTROL 更多]**&#x200B;功能表中的&#x200B;**[!UICONTROL 重新整理成員]**。

1. 選取&#x200B;**[!UICONTROL 成員]**&#x200B;標籤。

   資格成員會在短暫延遲後出現在清單中。

   ![為動態人員清單產生成員](./assets/people-list-dynamic-members.png){width="700" zoomable="yes"}

>[!NOTE]
>
>若要隨時變更清單規則，您可以重複這些步驟。 清單成員資格會根據儲存的篩選器重新整理。

<!--

## Duplicate a dynamic list {#duplicate-dynamic-list}

Duplicating a dynamic list replicates its membership filtering so that you can reuse it in a different context.

1. In the _[!UICONTROL Dynamic lists]_ tab, click the _More menu_ ( **...** ) icon next to the list and choose **[!UICONTROL Duplicate]**.

1. Enter a unique **[!UICONTROL Name]** (required) and a **[!UICONTROL Description]** (optional).

   By default, the dialog appends `_copy` to the name of the originating list. Enter a different unique name as needed.

   ![Duplicate list dialog](./assets/people-list-duplicate-dialog.png){width="375"}

1. Click **[!UICONTROL Duplicate]**.
-->
