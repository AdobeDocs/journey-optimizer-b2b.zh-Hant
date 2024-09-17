---
title: 購買群組角色範本
description: 瞭解如何定義作為購買群組元件的角色範本。
feature: Buying Groups
exl-id: 9206356e-e9cf-486c-8982-c7d893222413
source-git-commit: 8571e26a99a86e938bafbce7cea599a46441da8d
workflow-type: tm+mt
source-wordcount: '864'
ht-degree: 0%

---

# 購買群組角色範本

在B2B市場中，購買決策通常由多人做出。 這些個人會根據其在組織內的角色參與決策過程。 根據每個產品供應專案型別或帳戶使用案例，建立包含這些角色定義的購買群組角色範本。

![影片](../../assets/do-not-localize/icon-video.svg){width="30"} [觀看概觀影片](#overview-video)

## 存取和瀏覽角色範本

1. 在Adobe Experience Platform首頁中，按一下Adobe Journey Optimizer B2B Edition。

1. 在左側導覽列中，按一下&#x200B;**[!UICONTROL 購買群組]**。

1. 在&#x200B;_[!UICONTROL 購買群組]_&#x200B;頁面中，選取&#x200B;**[!UICONTROL 角色範本]**&#x200B;標籤。

   ![角色範本索引標籤](assets/roles-templates-tab.png){width="700" zoomable="yes"}

   索引標籤提供所有現有角色範本的詳細目錄清單，其欄位如下：

   * [!UICONTROL 名稱]
   * [!UICONTROL 狀態]
   * [!UICONTROL 建立日期]
   * [!UICONTROL 建立者：]
   * [!UICONTROL 上次更新]
   * [!UICONTROL 上次更新者]
   * [!UICONTROL 發佈於]
   * [!UICONTROL 發佈者]

   清單預設會依&#x200B;_[!UICONTROL 上次更新]_&#x200B;欄排序。

   _即時_ （已發佈）角色範本的數目會顯示在頁面的右上方。 所有角色範本的狀態都是`Draft`或`Live`。

1. 若要依名稱篩選清單，請使用清單頂端的搜尋欄位。

   輸入名稱的前幾個字元，將顯示的清單縮減為符合的專案。

   按搜尋字串篩選的![角色範本](assets/roles-templates-search.png){width="700" zoomable="yes"}

## 建立角色範本

1. 從&#x200B;_[!UICONTROL 角色範本]_&#x200B;索引標籤，按一下右上角的&#x200B;**[!UICONTROL 建立範本]**。

1. 在對話方塊中，輸入範本的唯一&#x200B;**[!UICONTROL Name]** （必要）和&#x200B;**[!UICONTROL Description]** （選用）。

   ![建立角色範本對話方塊](assets/roles-template-create-dialog.png){width="400"}

1. 為您要為範本定義的每個角色新增規則。

   * 從清單中選擇&#x200B;**[!UICONTROL 購買群組角色]**。

     目前版本有六個角色： `Decision Maker`、`Influencer`、`Practitioner`、`Executive Steering Committee`、`Champion`和`Other`。

     ![購買群組角色清單](./assets/roles-template-create-roles-list.png){width="700" zoomable="yes"}

   * 設定用於計算參與分數的角色的&#x200B;**[!UICONTROL 加權]**。

     每個選項的值都會轉譯成分數計算的百分比： [!UICONTROL 一般] = 20，[!UICONTROL 次要] = 40，[!UICONTROL 一般] = 60，[!UICONTROL 重要] = 80，以及[!UICONTROL 重要] = 100。

     例如，角色範本中的角色使用Vital、Important和Normal，則會轉換成100/240、80/240、60/240。

   * **[!UICONTROL 新增自動指派的條件]** — 選取此核取方塊可新增條件，以便將成員自動指派給符合條件的購買群組。 如果未選取核取方塊，則不需要新增條件。

   * **[!UICONTROL 完整性分數所需]** — 如果您希望計算完整性分數需要角色，請選取此核取方塊。

   * 按一下&#x200B;**[!UICONTROL 新增條件]**。

      * 在條件對話方塊中，展開&#x200B;**[!UICONTROL 人員屬性]**&#x200B;的清單，並找出要用來比對角色的屬性。 將其拖曳至右側，並放置在篩選空間中。

        ![角色範本新增條件拖曳屬性](assets/roles-template-role-attribute.png){width="700" zoomable="yes"}

      * 使用屬性，以使用一或多個值建立相符篩選器。

        在下列範例中，職稱屬性用於識別決策者的相符專案。 任何以`Director`或`Sr Director`開頭的標題值，都會將條件的評估為true。

        使用職稱](assets/roles-template-condition-example-job-title.png){width="700" zoomable="yes"}的![角色範本條件範例

      * 如有需要，請新增其他屬性和條件，進一步精簡符合角色的條件。

      * 按一下&#x200B;**[!UICONTROL 「完成」]**。

   針對您想要加入範本的每個其他角色，按一下&#x200B;**[!UICONTROL 新增其他角色]**，並定義一或多個條件以符合該角色。

   已定義多個角色的![角色範本](assets/roles-template-multiple-roles.png){width="700" zoomable="yes"}

1. 如果範本已可供使用，請按一下右上方的&#x200B;**[!UICONTROL Publish]**。

   發佈範本會將它設定為&#x200B;_即時_&#x200B;狀態，並使其可與解決方案興趣建立關聯。 至少必須有一個已定義的角色才能發佈角色範本。

   您的變更會自動儲存為&#x200B;_草稿_&#x200B;狀態。 如果您尚未準備好發佈角色範本，請按一下頁面頂端的向左（後退）箭頭，並返回「角色範本」清單。

## 編輯草稿角色範本

當角色範本處於&#x200B;_草稿_&#x200B;狀態時，您可以繼續編輯定義的角色。 您所做的任何變更都會自動儲存。

變更角色卡片標題中的任何設定，包括購買群組角色、權重、自動指派及完整性評分要求。

![變更購買群組角色屬性](./assets/roles-template-role-properties.png){width="600"}

### 修改角色的篩選器

若要變更任何角色的篩選邏輯，請按一下角色卡片右上角的&#x200B;_編輯_ （鉛筆）圖示。 此動作會開啟&#x200B;_[!UICONTROL 條件]_&#x200B;工作區，您可以在其中修改現有的篩選器、新增另一個篩選器、移除篩選器或變更篩選器邏輯。

### 刪除角色卡

如果您想要從範本移除角色，請按一下角色卡片中的&#x200B;_刪除_ （垃圾桶）圖示。

### 設定角色的優先順序

您可以重新排序範本中的角色，這會決定指派銷售機會給角色的優先順序。 每個角色卡片右側都顯示有&#x200B;**[!UICONTROL 優先順序]**&#x200B;控制器。 按一下右側的&#x200B;_向上_&#x200B;或&#x200B;_向下_&#x200B;箭號，將角色卡優先向上或向下移動。

![變更角色優先順序](./assets/roles-template-role-priority.png){width="700"}

## 刪除角色範本

如果角色範本處於&#x200B;_草稿_&#x200B;狀態，您可以將其刪除。

1. 從清單中選取角色範本以開啟它。

1. 按一下右上方的&#x200B;**[!UICONTROL 刪除]**。

   ![變更角色優先順序](./assets/roles-template-delete.png){width="700"}

1. 在對話方塊中，按一下&#x200B;**[!UICONTROL 刪除]**&#x200B;以進行確認。

## 概述影片

>[!VIDEO](https://video.tv.adobe.com/v/3433079/?learn=on)
