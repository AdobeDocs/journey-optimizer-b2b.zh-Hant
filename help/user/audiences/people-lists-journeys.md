---
title: 在歷程中使用人員清單
description: 使用人員清單以動態方式新增或移除人員，以及在Journey Optimizer B2B Edition中依清單成員資格分割歷程路徑。
feature: Audiences, Person Journeys, Account Journeys
role: User
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: beb5f4be-cec3-471a-9db6-831a77dd3ac9
    internal-label: Audiences
  - id: a4b836d9-ffdd-4df3-a62a-f78b830cf059
    internal-label: Journeys
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
source-git-commit: d713d57bddf2ac6f8cf7e7a7d163281f607d729c
workflow-type: tm+mt
source-wordcount: '829'
ht-degree: 0%
---

# 在歷程中使用人員清單

您有多種方式可將[人員清單](./people-lists.md)合併至您的帳戶歷程和個人歷程：

* **維護歷程中的靜態清單** — 在&#x200B;_採取動作_&#x200B;節點中，使用&#x200B;_[!UICONTROL 新增至人員清單]_&#x200B;或&#x200B;_[!UICONTROL 從人員清單移除]_&#x200B;動作，在人員經過歷程時更新靜態人員清單的成員資格。
* **根據清單成員資格路由人員** — 在&#x200B;_分割路徑_&#x200B;節點中，使用&#x200B;_[!UICONTROL 人員靜態清單的人員成員]_&#x200B;或&#x200B;_[!UICONTROL 人員動態清單的人員成員]_&#x200B;篩選器，為身為清單成員（或並非清單成員）的人員建立路徑。

例如，您可以建立團隊成員和合作夥伴的排除清單，並使用它從培養路徑中排除這些人員。 或者，當人員在一個歷程中到達資格點時，您可以將人員新增至靜態清單，然後使用該清單在不同歷程中分支人員。

## 執行動作節點 — 新增至人員清單 {#add-to-people-list}

**_僅限靜態人員清單_**

在帳戶或個人歷程中，使用[a _採取動作_&#x200B;節點](../journeys/action-nodes.md#people-actions)將人員新增至靜態人員清單。

例如，考慮您傳送電子郵件的歷程路徑，有些人註冊了網路研討會。 您將此回應視為歷程中的資格點。 取得資格後，您想要將這些人員新增至靜態人員清單，其他歷程會使用這些清單將合格人員分割至不同路徑。

>[!NOTE]
>
>如果節點執行時清單中已列有人員，則會忽略動作。

1. 導覽至歷程圖。

1. 按一下路徑上的加號( **+** )圖示，然後選擇&#x200B;**[!UICONTROL 執行動作]**。

1. （僅限帳戶歷程）Select ]_**[!UICONTROL 人員]**選項上的_[!UICONTROL &#x200B;動作。

1. 若要對人員執行&#x200B;_[!UICONTROL 動作]_，請選擇&#x200B;**[!UICONTROL 新增至人員清單]**。

1. 針對&#x200B;**[!UICONTROL Select靜態人員清單]**，選擇您要新增人員的人員清單。

   ![Select新增至人員清單](../journeys/assets/node-action-add-to-people-list.png){width="300"}

## 採取動作節點 — 從人員清單中移除 {#remove-from-people-list}

**_僅限靜態人員清單_**

在帳戶或人員歷程中，使用[a _採取動作_&#x200B;節點](../journeys/action-nodes.md#people-actions)從靜態人員清單移除人員。

例如，當某人轉換後，您想將其從靜態清單中移除。 此清單可用來將人們引導至培養路徑，讓他們不再接受培養通訊。

>[!NOTE]
>
>如果人員不在排定其移除的清單中，則會忽略動作。

1. 導覽至歷程圖。

1. 按一下路徑上的加號( **+** )圖示，然後選擇&#x200B;**[!UICONTROL 執行動作]**。

1. （僅限帳戶歷程）Select ]_**[!UICONTROL 人員]**選項上的_[!UICONTROL &#x200B;動作。

1. 若要對人員執行&#x200B;_[!UICONTROL 動作]_，請選擇&#x200B;**[!UICONTROL 從人員清單移除]**。

1. 針對&#x200B;**[!UICONTROL Select靜態人物清單]**，選擇您要移除的人物清單。

   ![Select從人員清單移除](../journeys/assets/node-action-remove-from-people-list.png){width="300"}

## 分割路徑節點 — 人員清單的成員 {#split-paths-by-list-membership}

**_帳戶和個人歷程_**

在&#x200B;[_分割路徑_&#x200B;節點](../journeys/split-merge-paths-nodes.md)中使用人員清單成員資格篩選器，根據人員是否為人員清單的成員來路由人員。 有兩個篩選器可供使用：

| 篩選 | 說明 |
| ------ | ----------- |
| [!UICONTROL 人員動態清單中的人員] | 人員是否為一或多個動態人員清單的成員。 成員資格會反映清單的目前規則。 |
| [!UICONTROL 人員靜態清單的成員] | 此人是否是一或多個靜態人員清單的成員。 |

這些篩選器適用於兩種歷程型別：

* **個人歷程** — 在&#x200B;_分割路徑_&#x200B;節點中。
* **帳戶歷程** — 在由&#x200B;_[!UICONTROL 人員]_&#x200B;分割的&#x200B;_分割路徑_&#x200B;節點中。

若要從Nurture路徑排除團隊成員和夥伴，請新增&#x200B;_[!UICONTROL 人員靜態清單的「人員」成員]_&#x200B;篩選器，將運運算元設定為`is not`，然後選取清單。

1. 導覽至歷程圖。

1. 按一下路徑上的加號( **+** )圖示，然後選擇&#x200B;**[!UICONTROL 分割路徑]**。

   ![新增歷程節點 — 分割路徑](../journeys/assets/add-node-split.png){width="300" zoomable="no"}

1. （僅限帳戶歷程）設定人員條件的節點。

   * 在右側的節點屬性中，選擇&#x200B;**[!UICONTROL 人員]**&#x200B;進行分割。

   * 將用於條件&#x200B;]**的**[!UICONTROL &#x200B;屬性設定為僅限&#x200B;**[!UICONTROL 人員屬性]**。

   ![帳戶歷程 — 分割路徑節點 — 人員屬性](../journeys/assets/node-split-path-account-journey-people-attributes.png){width="300" zoomable="no"}

1. 若要定義&#x200B;_[!UICONTROL 路徑1]_&#x200B;的條件，請按一下[套用條件]。****

1. 在條件編輯器中，展開&#x200B;_[!UICONTROL 特殊篩選器]_&#x200B;資料夾，並將&#x200B;**[!UICONTROL 人員動態清單的人員成員]**&#x200B;或&#x200B;**[!UICONTROL 人員靜態清單的人員成員]**&#x200B;篩選器拖曳到條件工作區。

   ![分割路徑條件編輯器，包含人員清單篩選器的人員成員](../accounts/assets/account-lists-person-journeys-split-path-filter.png){width="700" zoomable="yes"}

1. 若要包含清單成員，請將成員資格設為`is`。

   若要排除這些專案，請將其設為`is not`。

1. Select要評估的人員清單。

   在欄位中輸入文字，以篩選可用的清單。 只有使用者建立的人員清單可供選取。

1. 在上方套用&#x200B;**[!UICONTROL 篩選邏輯]**，以精簡條件。

   您可以將清單成員資格篩選器與其他人員篩選器結合，並選擇符合所有條件或任何條件。

1. 按一下「**[!UICONTROL 完成]**」。

繼續設定分割路徑節點，如&#x200B;[_依人員新增分割路徑_](../journeys/split-merge-paths-nodes.md#add-a-split-path-by-people-node)&#x200B;中所述。 如需成員資格篩選的詳細資訊，請參閱&#x200B;[_成員資格篩選_](../journeys/split-merge-paths-nodes.md#membership-filtering)。
