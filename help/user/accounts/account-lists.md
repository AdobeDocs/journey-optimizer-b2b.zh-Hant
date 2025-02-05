---
title: 帳戶清單
description: 瞭解帳戶清單，以及行銷人員如何透過帳戶歷程使用它們來鎖定帳戶。
source-git-commit: c44721af93275297a90c6f7c0c3683ade6847658
workflow-type: tm+mt
source-wordcount: '1632'
ht-degree: 0%

---

# 帳戶清單

帳戶清單是行銷人員可用於目標歷程協調的具名帳戶集合。 帳戶清單可依據您定義的條件（例如產業、地點或公司規模）來鎖定已命名的帳戶。 帳戶清單有兩種型別：

* **靜態** — 使用靜態帳戶清單時，清單只有在您新增帳戶時才會變更。 您可以套用篩選器集來根據目前的帳戶資料填入清單，以手動新增帳戶，或是透過帳戶歷程新增和移除帳戶。
* **動態** — 使用動態帳戶清單，您可以定義自動組織清單的篩選器集。 系統會使用此篩選器集，根據帳戶資訊中的變更來新增和移除帳戶。 此清單管理類似於Real-time Customer Data Platform](https://experienceleague.adobe.com/en/docs/experience-platform/rtcdp/segmentation/b2b)中的[對象細分。

當帳戶清單處於&#x200B;_即時_ （已發佈）狀態時，它可用於帳戶歷程。

## 存取和瀏覽帳戶清單

1. 在Adobe Experience Platform首頁中，按一下Adobe Journey Optimizer B2B edition。

1. 在左側導覽列中，展開&#x200B;**[!UICONTROL 帳戶]**&#x200B;並按一下&#x200B;**[!UICONTROL 帳戶清單]**。

   ![存取帳戶歷程](./assets/account-lists-browse.png){width="800" zoomable="yes"}

   顯示的&#x200B;_[!UICONTROL 帳戶清單]_&#x200B;頁面包含下列資料行：

   * [!UICONTROL 名稱] （按一下帳戶清單名稱以檢視詳細資料）
   * [!UICONTROL 狀態]
   * [!UICONTROL 類型]
   * [!UICONTROL 上次更新時間：]
   * [!UICONTROL 上次更新者]
   * [!UICONTROL 建立日期]
   * [!UICONTROL 建立者：]

此表格包含依名稱搜尋的功能。 排序功能目前無法使用。

您可以按一下右上角的&#x200B;_欄設定_ （ ![欄設定](../assets/do-not-localize/icon-column-settings.svg) ）圖示，並選取或清除核取方塊來自訂顯示的表格。

![選擇要顯示在帳戶歷程清單中的資料行](./assets/account-lists-list-columns.png){width="300"}

若要檢視帳戶清單的說明，請按一下名稱旁的&#x200B;_資訊_&#x200B;圖示。

## 建立帳戶清單

建立帳戶清單時，您可以定義一組篩選條件來產生清單。 例如，您可以使用它產生一份帳戶清單，其中產業為Healthcare且收入超過1億美元。

1. 在&#x200B;_[!UICONTROL 帳戶清單]_&#x200B;頁面中，按一下頁面右上角的&#x200B;**[!UICONTROL 建立帳戶清單]**。

   ![按一下[建立帳戶清單]](./assets/account-lists-create.png){width="700" zoomable="yes"}

1. 在&#x200B;_[!UICONTROL 建立帳戶清單]_&#x200B;對話方塊中，輸入唯一的&#x200B;**[!UICONTROL 名稱]** （必要）和&#x200B;**[!UICONTROL 描述]** （選用）。

1. 選擇帳戶清單的&#x200B;_[!UICONTROL 型別]_、**[!UICONTROL 靜態]**&#x200B;或&#x200B;**[!UICONTROL 動態]**。

   ![為帳戶清單選擇[靜態]或[動態]](./assets/account-list-create-dialog.png){width="380"}

1. 按一下&#x200B;**[!UICONTROL 建立]**。

   隨即開啟新的靜態帳戶清單，其中含有空白的帳戶清單。 開啟新的動態帳戶清單，其中顯示頁面中的&#x200B;_[!UICONTROL 依篩選器新增帳戶]_&#x200B;面板。

## 將帳戶新增至帳戶清單

對於靜態清單，您可以繼續發佈空白帳戶清單，並透過帳戶歷程新增帳戶。 您也可以在發佈之前套用篩選器集，以手動新增帳戶。

對於動態帳戶清單，您必須先新增要用來自動管理清單的篩選器集，然後才能發佈。

>[!BEGINTABS]

>[!TAB 靜態帳戶清單]

建立靜態帳戶清單後，您可以套用篩選器集來填入清單。 您也可以套用篩選器集，在靜態帳戶清單發佈後新增帳戶（_即時_）。

>[!NOTE]
>
>如果您希望帳戶清單一開始是空的，請勿選取任何篩選器，而只需發佈帳戶清單即可。 當您計畫透過帳戶歷程動作新增成員時，最好從空白清單開始（請參閱[採取動作節點 — 新增至帳戶](#take-an-action-node---add-to-account)）。

1. 按一下&#x200B;**[!UICONTROL 新增帳戶]**。

   ![新增帳戶篩選器以填入清單](./assets/account-lists-static-new-add-accounts.png){width="700" zoomable="yes"}

   您可以在空白清單頁面或右上角存取此函式。

1. 在&#x200B;_[!UICONTROL 依篩選器新增帳戶]_&#x200B;對話方塊中，使用&#x200B;**[!UICONTROL 帳戶篩選器]**&#x200B;功能表新增要用來建構篩選器集的屬性和活動：

   這些篩選器會巢狀內嵌至類別資料夾中。 您可以展開每個資料夾，並捲動瀏覽可用篩選器的清單。 或者，使用頂端的&#x200B;_搜尋_&#x200B;工具來尋找您需要的篩選器。

   * 從左側選單將篩選器拖放至篩選器定義空間。
   * 完成比對評估定義。
   * 對要包含的每個篩選器重複這些動作。

     ![新增篩選器以填入帳戶清單](./assets/account-lists-static-add-accounts-by-filters.png){width="700" zoomable="yes"}

   * 您可以在頂端套用&#x200B;**[!UICONTROL 篩選邏輯]**，以微調條件。 您可以選擇符合所有屬性條件或任何條件。

     ![帳戶清單篩選邏輯](./assets/account-lists-filter-logic.png){width="450"}

1. 篩選器集和邏輯完成時，按一下&#x200B;**[!UICONTROL 填入帳戶]**。

   根據要評估和填入的帳戶數量（資料庫的大小和您選取的篩選條件），填入程式可能需要一些時間。 將帳戶填入您的清單最多可能需要兩個小時的時間。

您可以繼續發佈清單，使其可用於帳戶歷程中的新增和移除動作。

>[!TAB 動態帳戶清單]

建立動態帳戶清單之後，您定義用來管理清單的篩選器集（新增/移除帳戶），當清單為&#x200B;_即時_ （已發佈）。 您無法透過帳戶歷程新增/移除帳戶，但已發佈的動態帳戶清單可用於起始帳戶對象節點。

1. 按一下&#x200B;**[!UICONTROL 選取篩選器]**。

   ![選取用來動態填入清單的篩選器](./assets/account-lists-dynamic-new-select-filters.png){width="700" zoomable="yes"}

1. 在&#x200B;_[!UICONTROL 依篩選器新增帳戶]_&#x200B;對話方塊中，使用&#x200B;**[!UICONTROL 帳戶篩選器]**&#x200B;功能表新增要用來建構篩選器集的屬性和特殊篩選器：

   這些篩選器會巢狀內嵌至類別資料夾中。 您可以展開每個資料夾，並捲動瀏覽可用篩選器的清單。 或者，使用頂端的&#x200B;_搜尋_&#x200B;工具來尋找您需要的篩選器。

   * 從左側選單將篩選器拖放至篩選器定義空間。
   * 完成比對評估定義。
   * 對要包含的每個篩選器重複這些動作。

     ![新增篩選器以填入帳戶清單](./assets/account-lists-dynamic-add-accounts-by-filters.png){width="700" zoomable="yes"}

   * 您可以在頂端套用&#x200B;**[!UICONTROL 篩選邏輯]**，以微調條件。 您可以選擇符合所有屬性條件或任何條件。

     ![帳戶清單篩選邏輯](./assets/account-lists-filter-logic.png){width="450"}

1. 篩選器集和邏輯完成時，按一下&#x200B;**[!UICONTROL 完成]**。

   如果您滿意篩選器集，可以繼續進行[發佈清單](#publish-an-account-list)，使其可用於帳戶歷程中的起始[帳戶對象節點](#account-audience-node)。

   >[!NOTE]
   >
   >在發佈動態帳戶清單後，您無法更新該清單的篩選器。

   根據要評估和填入的帳戶數量（資料庫的大小和您選取的篩選條件），填入程式可能需要一些時間。 將帳戶填入您的清單最多可能需要兩個小時的時間。

>[!ENDTABS]

## Publish帳戶清單

篩選器集完成後，您就可以繼續發佈帳戶清單。

>[!BEGINTABS]

>[!TAB 靜態帳戶清單]

1. 按一下右上方的&#x200B;**[!UICONTROL Publish]**。

   ![按一下右上方的Publish](./assets/account-lists-static-publish.png){width="700" zoomable="yes"}

1. 在&#x200B;_[!UICONTROL Publish靜態帳戶清單]_&#x200B;對話方塊中，按一下&#x200B;**[!UICONTROL Publish]**&#x200B;以進行確認。

   ![確認發佈靜態帳戶清單](./assets/account-lists-static-publish-confirm.png){width="400"}

靜態帳戶清單的狀態變更為&#x200B;_[!UICONTROL 即時]_，且可用於[帳戶歷程](#account-list-usage-in-account-journeys)中使用。

>[!TAB 動態帳戶清單]

篩選器集完成後，您就可以繼續發佈動態帳戶清單。 帳戶清單處於即時狀態後，就可在帳戶對象歷程節點中選取。

1. 按一下右上方的&#x200B;**[!UICONTROL Publish]**。

   ![按一下右上方的Publish](./assets/account-lists-dynamic-publish.png){width="700" zoomable="yes"}

1. 在&#x200B;_[!UICONTROL Publish動態帳戶清單]_&#x200B;對話方塊中，按一下&#x200B;**[!UICONTROL Publish]**&#x200B;以進行確認。

   ![確認發佈動態帳戶清單](./assets/account-lists-dynamic-publish-confirm.png){width="400"}

動態帳戶清單的狀態變更為&#x200B;_[!UICONTROL 即時]_，且可用於[帳戶歷程](#account-list-usage-in-account-journeys)中使用。

>[!ENDTABS]

## 帳戶歷程中的帳戶清單使用情況

您有三種方式可以在帳戶歷程中合併即時（已發佈）帳戶清單：

### 帳戶對象節點

1. 為起始&#x200B;_帳戶對象_&#x200B;節點選取&#x200B;**[!UICONTROL 帳戶清單]**。

   ![選取帳戶對象節點的帳戶清單選項](../journeys/assets/node-audience-account-list.png){width="500"}

1. 按一下&#x200B;**[!UICONTROL 新增帳戶清單]**。

1. 選取帳戶清單的核取方塊，然後按一下[儲存]。****

   ![選取帳戶對象節點的帳戶清單選項](../journeys/assets/node-audience-account-list-select-dialog.png){width="600" zoomable="yes"}

清單中的帳戶在歷程上線（發佈）時進行移動。

### 採取動作節點 — 新增至帳戶

**_僅限靜態帳戶清單_**

使用[a _執行動作_&#x200B;節點](../journeys/action-nodes.md)將帳戶新增至靜態帳戶清單。

例如，您可能有傳送電子郵件的歷程路徑，且某些帳戶會將各種動作視為回應動作。 您將此活動視為歷程中的資格點，並想要將其新增至帳戶清單，該清單用來作為另一個歷程的對象，該歷程具有不同的合格帳戶流程。

>[!NOTE]
>
>如果節點執行時帳戶已在清單中，則會忽略動作。

1. 選取&#x200B;]_**[!UICONTROL 帳戶]**上的_[!UICONTROL &#x200B;動作選項。

1. 若為帳戶&#x200B;]_上的_[!UICONTROL &#x200B;動作，請選擇&#x200B;**[!UICONTROL 新增至帳戶清單]**。

   ![選取[新增至帳戶清單]](../journeys/assets/node-action-account-add-to-account-list.png){width="500"}

1. 若為&#x200B;**[!UICONTROL 選取即時靜態帳戶清單]**，請選擇您要新增帳戶的帳戶清單。

   ![選取[新增至帳戶清單]](../journeys/assets/node-action-account-add-to-account-list-select.png){width="500"}

### 採取動作節點 — 從帳戶移除

**_僅限靜態帳戶清單_**

使用[a _執行動作_&#x200B;節點](../journeys/action-nodes.md)，從靜態帳戶清單中移除帳戶。

例如，您可能有傳送電子郵件的歷程路徑，且某些帳戶會將各種動作視為回應動作。 您將此活動視為歷程中的資格點，並想要將其從帳戶清單中移除，該帳戶清單用於作為另一個傳送其他電子郵件的歷程的受眾，以便您不會複製您的資格通訊。

>[!NOTE]
>
>如果帳戶不在排定移除的清單中，則會忽略動作。

1. 選取&#x200B;]_**[!UICONTROL 帳戶]**上的_[!UICONTROL &#x200B;動作選項。

1. 若為帳戶&#x200B;]_上的_[!UICONTROL &#x200B;動作，請選擇&#x200B;**[!UICONTROL 從帳戶清單移除]**。

   ![選取[新增至帳戶清單]](../journeys/assets/node-action-account-remove-from-account-list.png){width="500"}

1. 若為&#x200B;**[!UICONTROL 選取即時靜態帳戶清單]**，請選擇您要移除帳戶的帳戶清單。

   ![選取[新增至帳戶清單]](../journeys/assets/node-action-account-remove-from-account-list-select.png){width="500"}

