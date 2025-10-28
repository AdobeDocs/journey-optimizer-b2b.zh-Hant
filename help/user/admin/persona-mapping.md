---
title: 角色對應
description: 瞭解如何為B2B行銷設定角色對應。 在Journey Optimizer B2B edition中對應人員屬性以建立角色範本，並最佳化購買群組目標定位。
feature: Setup, Buying Groups
role: Admin
source-git-commit: 6df235bc73066463e5fcfa71dc994f34e13e3ac0
workflow-type: tm+mt
source-wordcount: '901'
ht-degree: 1%

---

# 人物誌對應

角色是以帳戶為基礎的行銷(ABM)方法中的關鍵面向，角色可協助行銷人員根據目標帳戶中個人的特定需求、偏好和痛點調整策略。 行銷人員可以為每個角色建立詳細的設定檔，包括其背景、責任、痛點和偏好的通訊管道。 透過這些定義，管理員可以根據Journey Optimizer B2B edition中的人員屬性來設定角色，讓角色範本可以使用簡化且一致的角色條件來擷取這些角色。

<!-- Currently there is no insight into what persona goes into what role. With buying group agent, when asked questions about, what should be the size of the buying group, what persona should be in that buying group, what role do they play, etc, then agent will analyze all the data, (opportunity data, engagement data, sales conversation, etc) and informs the user that the buying group needs 7 persona, e.g.CMO, VP of marketing, marketing leader, Marketing ops, etc. 

Then based on what agent informed, users can create a template with those personas. -->
角色定義和使用限制：

* 您最多可以在&#x200B;_[!UICONTROL 角色對應]_&#x200B;清單中定義20個角色。
* 每個角色在其定義中最多可以包含五個屬性。
* 在所有已定義的角色中，您最多可以使用10個不同的人員屬性。

>[!BEGINSHADEBOX]

**使用案例：職稱變化**

許多行銷和銷售團隊使用職稱作為識別帳戶中不同角色的方式。 但聯絡人的標題可能會不一致，且對類似角色使用許多變數。 建立購買群組角色範本時，可能需要您為特定角色定義每個可能的相關職稱。 您可以簡化這些定義，將擁有類似職稱的人員歸入同一個推斷角色下，然後您可以跨不同的角色範本運用這些範本來購買群組。

例如，您可以設定名為&#x200B;_產品管理_&#x200B;的角色，並使用&#x200B;_產品經理_，_Sr的值的工作職稱屬性來定義它。產品經理_，_資深產品經理_，_PM_，_Sr。PM_、_主體PM_&#x200B;和&#x200B;_主體產品經理_。 然後，在角色範本中使用此角色，其中&#x200B;_角色上的條件符合產品管理_。 使用已設定的角色，可簡化建立每個角色範本，且不需要符合每個可能職稱的複雜條件。

>[!ENDSHADEBOX]

## 存取已設定的角色

1. 在左側導覽列中，選擇&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 組態]**。

1. 按一下中繼面板上的&#x200B;**[!UICONTROL 角色對應]**&#x200B;以顯示角色清單。

   ![存取設定的角色](./assets/configuration-engagement-scoring-list.png){width="800" zoomable="yes"}

   您可以從此頁面[建立](#create-an-engagement-score-model)、[編輯](#change-the-engagement-weighting-settings)或[刪除](#delete-a-persona)角色。

   角色對應清單。 組織為表格，並在頂端顯示最近更新的角色（依&#x200B;_[!UICONTROL 上次更新]_&#x200B;排序）。 您可以按一下右上角的&#x200B;_欄設定_ （ ![欄設定](../assets/do-not-localize/icon-column-settings.svg) ）圖示，並選取或清除欄核取方塊來自訂顯示的表格。

![要顯示在角色對應清單中的欄](./assets/configuration-engagement-scoring-list-columns.png){width="300"}

1. 若要存取角色的詳細資訊，請按一下名稱。

### 預設角色

_角色對應_&#x200B;清單包含根據工作標題屬性定義的五個預設角色。 您可以根據組織的需求編輯以下任何預設角色：

| 人物誌 | 職稱 |
| ------- | ---------- |
| CXO / EVP - CXO /執行副總裁 | CEO、CIO、CTO、CMO、CFO、策略執行副總裁 |
| SVP / VP — 資深副總裁/副總裁 | 行銷副總裁、銷售副總裁、營運副總裁、產品副總裁、IT副總裁 |
| 高級董事/董事 — 高級董事/董事 | 工程總監、資深產品總監、財務總監、客戶成功總監 |
| 資深經理/經理 — 資深經理/經理 | 資深行銷經理、IT經理、營運經理、銷售經理、人力資源經理 |
| 個人貢獻者 — 個人貢獻者 | 客戶主管、軟體工程師、行銷專家、客戶成功代表 |
| 分析師 — 分析師 | 業務分析師、資料分析師、市場研究分析師、財務分析師、營運分析師 |
| 開發人員 — 開發人員 | 前端開發人員、後端開發人員、完整棧疊開發人員、行動應用程式開發人員、DevOps工程師 |
| 專業人員 — 專業人員 | 人力資源專家、法律顧問、法規遵循人員、專案經理、採購專家 |
| 顧問 — 顧問 | 管理顧問、IT顧問、業務流程顧問、行銷顧問 |
| 其他 — 其他 | 產業專家、獨立顧問、自由顧問、主題專家 |

### 清單篩選

若要找到您想要的角色，請使用搜尋和篩選工具：

* 在搜尋列中輸入文字字串，依名稱比對角色，

  ![篩選顯示的事件定義](./assets/configuration-events-defs-list-filtered.png){width="700" zoomable="yes"}

* 按一下左上方的&#x200B;_篩選器_ （![篩選器圖示](../assets/do-not-localize/icon-filter.svg) ）圖示，以依屬性篩選顯示的清單。

## 建立角色

1. 在左側導覽中，選擇&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 組態]**。

1. 按一下中繼面板中的&#x200B;**[!UICONTROL 角色對應]**。

1. 按一下&#x200B;**[!UICONTROL 建立角色]**。

1. 輸入角色唯一&#x200B;**[!UICONTROL 名稱]**&#x200B;和&#x200B;**[!UICONTROL 描述]** （選擇性）。

1. 選取用於比對角色的屬性。

   * 按一下&#x200B;**[!UICONTROL 選取人員屬性]**。

   * 在對話方塊中，選取每一個要對應的屬性的核取方塊（最多五個）。

     您可以按一下右上角的&#x200B;_欄設定_ （ ![欄設定](../assets/do-not-localize/icon-column-settings.svg) ）圖示來自訂顯示的表格。

     若要依名稱篩選屬性清單，請在搜尋列中輸入文字字串。 您也可以按一下左上方的&#x200B;_篩選器_ （![篩選器圖示](../assets/do-not-localize/icon-filter.svg) ）圖示，依型別&#x200B;_標準_&#x200B;或&#x200B;_自訂_&#x200B;來篩選顯示的清單。

   * 按一下&#x200B;**[!UICONTROL 儲存]**。

     選取的屬性會填入&#x200B;_[!UICONTROL 角色屬性]_&#x200B;區段中。

1. 針對每個屬性，輸入您要與屬性比對的逗號分隔值。

   您也可以新增可用來識別相符專案的提示，以取代值。 例如，您可以輸入

1. 按一下&#x200B;**[!UICONTROL 建立]**。

## 編輯角色

按一下角色名稱以存取及編輯角色的詳細資料，

## 刪除角色

刪除角色會將其從&#x200B;_角色對應_&#x200B;清單中移除，並且無法再用於角色範本。

1. 在&#x200B;_[!UICONTROL 角色對應]_&#x200B;頁面上，找出您要刪除的角色。

1. 在名稱旁邊，按一下的省略符號(**...**)圖示，然後選擇&#x200B;**[!UICONTROL 刪除]**。

1. 在確認對話框中，按一下「**[!UICONTROL 刪除]**」。
