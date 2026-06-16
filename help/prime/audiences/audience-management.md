---
title: Audience Management
description: 對象的預留位置頁面。
autotag-review: '2026-06-12T22:47:10.727Z'
TQID: 'https://experienceleague.adobe.com/KWT9-Lr6358MQ0sLQyKAlb4SLERnBl-QQL7Cj1iXCZM'
product_v2: id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2: id: beb5f4be-cec3-471a-9db6-831a77dd3ac9id: aed878b8-11d0-487c-828b-d23b2051ec37
subfeature_v2: id: d270a788-eb1d-40ed-b74e-9158ed975b1f
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: c844cb4fb520f802c18a9988461c39106000b778
workflow-type: tm+mt
source-wordcount: 474
ht-degree: 3%

---

# 客群管理

從行銷管理中心，按一下右側導覽中的&#x200B;**[!UICONTROL 人員清單]**。

![存取人員清單以管理您的對象](./assets/people-lists.png){width="800" zoomable="yes"}

頁面有兩個標籤，您可以在其中檢視和管理&#x200B;**[!UICONTROL 動態清單]**&#x200B;和&#x200B;**[!UICONTROL 靜態清單]**。 按一下索引標籤，在每種型別之間切換清單檢視。

您可以從此頁面執行下列作業：

* 建立新的動態和靜態清單
* 搜尋現有清單
* 檢視資產資訊
* 存取清單以檢閱其成員資格

<!--
## Audience Hub

The AI Audience Hub is a centralized, AI-driven starting point for all audience-related capabilities across AJO B2B. It is designed to accelerate first-time user success while progressively unlocking advanced intelligence, insights, and control for returning and power users.

The Hub acts as:

* A guided starting point for discovering, creating, and refining person lists, account lists, and buying groups

* A visibility layer for audience health, coverage, overlap, engagement patterns, and AI-driven insights

* A control center for audience governance, optimization, reuse, and readiness for activation across journeys and sales workflows

### High level structure

Prompt-based starting point - Quick Start prompts and freeform input to help users discover, create, or optimize audiences.

1. AI insights feed - Surfaces key audience signals such as overlap, gaps, saturation risk, and optimization opportunities.

1. Adaptive audience library - A personalized view of people lists, account lists, and buying groups that adapts based on usage, relevance, and activation.

1. Optimization and arbitration nudges - Guides users to refine, split, or reuse audiences before activation.

1. Audience visibility and reporting - High-level insight into audience health, engagement patterns, and usage across active journeys.


### Empty and Error States (High-Level)

No audiences / no data - Show Quick Start prompts to help first-time users create or import person lists

Low data or incomplete audience - Explain what's missing (e.g., insufficient contacts, missing persona coverage, or low engagement data) and suggest next steps.

AI insights unavailable - Provide a graceful fallback with a clear explanation, so users understand why insights aren't shown and what actions they can take manually.
-->

## 建立人員清單


若要建立動態或靜態清單：

1. 按一下&#x200B;_[!UICONTROL 人員清單]_&#x200B;頁面右上角的&#x200B;**[!UICONTROL 建立清單]**。
1. 選取一個方案作為清單的&#x200B;**[!UICONTROL 父項]**。
1. 輸入清單&#x200B;**[!UICONTROL 名稱]**&#x200B;和&#x200B;**[!UICONTROL 描述]** （選擇性）。
1. 選擇然後列出&#x200B;**[!UICONTROL 型別]**：

   * **[!UICONTROL 靜態]** — 成員資格取決於您建立清單時所評估的合格篩選器。除非您手動限定或取消限定記錄，否則清單成員資格不會更新。
***[!UICONTROL 動態]** — 成員資格是由合格的篩選器動態決定。清單成員資格會自動重新整理。

1. 按一下&#x200B;**[!UICONTROL 建立]**。

>[!NOTE]
>
>此Beta版本中的人員清單目前不支援刪除和複製。

## 靜態清單

靜態清單成員資格是由參照人員屬性和活動的簡單篩選器所定義。 除非您手動讓成員符合資格或取消成員資格，否則成員資格不會變更。

>[!NOTE]
>
>當您新增或移除清單中的成員時，靜態清單篩選定義只會套用一次。 定義的篩選器之後將無法使用。 如果您想要使用篩選器維持一致的對象定義，請改用動態清單。

### 新增成員

1. 開啟靜態清單，然後按一下右上方的&#x200B;**[!UICONTROL 新增人員]**。

1. 在對話方塊中，從左側拖放篩選器，定義用於限定銷售機會的規則。

   您可以使用下列任一組合來篩選人員：

   * 活動歷史記錄
   * 公司屬性
   * 人員屬性
   * 歷程成員資格等特殊篩選器

1. 若要儲存變更，請按一下[完成]。****

1. 選取&#x200B;**[!UICONTROL 成員]**&#x200B;標籤。

   一段時間後，符合資格的成員會出現在清單中。

### 移除成員

1. 開啟靜態清單，然後按一下右上方的&#x200B;**[!UICONTROL 移除人員]**。

1. 在對話方塊中，新增篩選器以符合您要取消資格的成員。

1. 若要儲存變更，請按一下[完成]。****

1. 選取&#x200B;**[!UICONTROL 成員]**&#x200B;標籤。

   一段時間後，取消資格的成員會離開清單。

## 動態清單

動態清單成員資格是使用參考人員屬性和活動的簡單篩選器來定義。 會根據篩選邏輯，透過限定和取消限定銷售機會來自動維護成員資格。

### 定義成員資格邏輯

1. 開啟靜態清單，然後選取「規則」標籤。

1. 按一下「編輯規則」。

1. 在對話方塊中，從左側拖放篩選器，定義用於限定銷售機會的規則。

   您可以使用下列任一組合來限定銷售機會加入清單：

   * 活動歷史記錄
   * 公司屬性
   * 人員屬性
   * 歷程成員資格等特殊篩選器

1. 若要儲存變更，請按一下[完成]。****

1. 選取&#x200B;**[!UICONTROL 成員]**&#x200B;標籤。

   一段時間後，符合資格的成員會出現在清單中。

若要開啟潛在客戶設定檔詳細資訊頁面，您可在此檢視摘要和最近的活動，請按一下清單中的人員名稱。