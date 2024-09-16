---
title: 片段
description: 瞭解如何在Adobe Journey Optimizer B2B Edition中建立和使用視覺內容片段，作為電子郵件和電子郵件範本的可重複使用元件。
feature: Content, Email Authoring
exl-id: 3c1d2ca0-d009-4a2a-9d81-1a838845b7fa
source-git-commit: 8e55e4444a363a5699574c2fa1ed256fdb690dd0
workflow-type: tm+mt
source-wordcount: '1849'
ht-degree: 3%

---

# 片段

片段是可重複使用的元件，可在各個Adobe Journey Optimizer B2B Edition的一或多個電子郵件和電子郵件範本中參考。 這通常是可以預先建立並快速插入電子郵件或電子郵件範本中的內容區塊（文字、影像或兩者）。 透過此功能，您可以預先建置多個自訂內容區塊，以供行銷團隊成員用於組合電子郵件內容，以改進設計流程。 常見的使用案例包括電子郵件的頁首/頁尾內容區塊、事件邀請橫幅和季節性問候。

若要在工作流程中善用片段：

* _建立您自己的片段_ — 從草稿開始建立視覺化片段，或是從視覺化內容編輯器將內容儲存為片段。
* _重複使用片段_ — 視需要在您的內容中多次使用這些片段。

## 視覺片段

視覺片段是預先定義的視覺化區塊，使用視覺化內容編輯器建置，可在多個電子郵件或電子郵件範本中重複使用。 Journey Optimizer B2B版本的目前範圍及本檔案僅為視覺片段。 Journey Optimizer B2B Edition尚不支援運算式型片段。

## 存取及管理片段

若要存取Adobe Journey Optimizer B2B版本中的視覺片段，請前往左側導覽並按一下&#x200B;**[!UICONTROL 內容管理]** > **[!UICONTROL 片段]**。 此動作會開啟一個清單頁面，其中包含在表格中列出的執行個體中建立的所有片段。

![存取片段庫](./assets/fragments-list.png){width="700" zoomable="yes"}

此表格是依&#x200B;_[!UICONTROL 已修改]_&#x200B;欄排序，最近更新的片段預設會排在頂端。 按一下欄標題，在升序和降序之間變更。

若要依名稱搜尋片段，請在搜尋列中輸入文字字串以尋找相符專案。 按一下&#x200B;_篩選器_&#x200B;圖示，根據您指定的條件篩選顯示的專案。

![篩選顯示的片段](./assets/fragments-list-filtered.png){width="700" zoomable="yes"}

按一下右上角的&#x200B;_自訂表格_&#x200B;圖示，自訂您要顯示在表格中的欄。 選取要顯示的資料行，然後按一下&#x200B;**[!UICONTROL 套用]**。

## 建立內容片段

您可以按一下右上角的「**[!UICONTROL 建立片段]**」，在Journey Optimizer B2B Edition中建立新的視覺片段。

1. 在&#x200B;_[!UICONTROL 建立片段]_&#x200B;對話方塊中，輸入有用的&#x200B;**[!UICONTROL 名稱]**&#x200B;和&#x200B;**[!UICONTROL 描述]** （選擇性）。

   片段需求：

   * 名稱 — 最多100個字元，必須是唯一的、不區分大小寫

   * 說明 — 最多300個字元

   * 允許使用Alpha、數值和特殊字元

   * 保留的字元是&#x200B;**_不允許_**： `\ / : * ? " < > |`

   ![建立片段對話方塊](./assets/assets-fragments-create-dialog.png){width="400"}

1. 按一下&#x200B;**[!UICONTROL 建立]**。

   隨即開啟視覺內容編輯器，其中顯示空白畫布。

<!-- To be linked to the corresponding sections on this page: Adobe Journey Optimizer B2B Edition - Email Templates

Adding structure and content
Adding assets
Navigating the layers
Previewing & editing URLs
View options
More options -->

### 新增結構和內容 {#design-fragment}

>[!CONTEXTUALHELP]
>id="ajo-b2b_structure_components_fragment"
>title="新增結構元件"
>abstract="結構元件會定義區段的版面。將&#x200B;**結構**&#x200B;元件拖放到畫布中開始設計您的片段內容。"

>[!CONTEXTUALHELP]
>id="ajo-b2b_content_components_fragment"
>title="關於內容元件"
>abstract="內容元件指可用於建立片段版面的空白內容預留位置。"

{{$include /help/_includes/content-design-components.md}}

### 新增資產

{{$include /help/_includes/content-design-assets.md}}

### 導覽圖層、設定和樣式

{{$include /help/_includes/content-design-navigation.md}}

### 個人化內容

{{$include /help/_includes/content-design-personalization.md}}

### 編輯連結的URL追蹤

{{$include /help/_includes/content-design-links.md}}

## 檢視片段詳細資訊

按一下清單頁面中任何片段的名稱，以開啟片段詳細資訊頁面。 您可以選擇編輯片段、重新命名片段或更新片段說明。 進行更新，然後按一下名稱或說明欄位外部以自動儲存變更。

>[!NOTE]
>
>如果電子郵件或電子郵件範本正在使用已發佈的片段，則您無法變更名稱或編輯內容。 如果您想對片段進行變更，可以建立草稿版本。

![檢視已發佈片段的詳細資料](./assets/fragment-details-published.png){width="600" zoomable="yes"}

按一下「**[!UICONTROL 編輯片段]**」以在視覺內容編輯器中開啟片段。

隨時按一下左上方的&#x200B;_上一步_&#x200B;箭頭以結束檢視，此箭頭會返回&#x200B;_片段_&#x200B;清單頁面。

## 檢視片段使用者參考

在片段詳細資訊頁面中，按一下&#x200B;**[!UICONTROL 使用者]**&#x200B;索引標籤，以檢視Journey Optimizer B2B Edition、電子郵件、電子郵件範本和片段中目前使用片段的詳細資訊。

>[!IMPORTANT]
>
>無法刪除任何電子郵件或電子郵件範本目前正在使用的任何片段。

根據類別顯示參考： _電子郵件_&#x200B;或&#x200B;_電子郵件範本_。 Journey Optimizer B2B Edition中的電子郵件會內嵌於帳戶歷程中並加以撰寫，因此使用片段的電子郵件上層歷程會顯示在參考中。

![由片段](./assets/fragment-used-by-published.png){width="600" zoomable="yes"}的參考使用

按一下連結，開啟使用片段之對應的電子郵件或電子郵件範本。

## 刪除片段

無法刪除任何電子郵件或電子郵件範本目前正在使用的任何片段，因此在起始片段移除前，請務必檢查&#x200B;_used-by_&#x200B;參考。 此外，移除無法復原，因此在起始刪除動作前請先檢查。

您可以使用下列其中一種方法來刪除片段：

* 從右側的片段詳細資料中，按一下&#x200B;**[!UICONTROL 刪除]**。
* 從&#x200B;_[!UICONTROL 片段]_&#x200B;清單頁面，按一下片段旁的省略符號，然後選擇&#x200B;**[!UICONTROL 刪除]**。

此動作會開啟確認對話方塊。 您可以按一下&#x200B;**[!UICONTROL 取消]**，或按一下&#x200B;**[!UICONTROL 刪除]**&#x200B;確認刪除，以中止程式。

![刪除片段對話方塊](./assets/fragment-delete-dialog.png){width="400"}

如果片段目前正在使用中，動作會開啟資訊對話方塊，提醒您無法刪除該片段。 按一下&#x200B;**[!UICONTROL 確定]**，這會中止刪除動作。

![刪除片段對話方塊 — 無法刪除使用中的片段](./assets/fragment-delete-dialog-in-use.png){width="400"}

## 編輯片段

您可以使用下列其中一種方法來編輯片段：

* 從右側的片段詳細資料中，按一下&#x200B;**[!UICONTROL 編輯]**。
* 從&#x200B;_[!UICONTROL 片段]_&#x200B;清單頁面，按一下片段旁的省略符號，然後選擇&#x200B;**[!UICONTROL 編輯]**。

此動作會在視覺內容編輯器中開啟片段，您可以在其中使用[建立片段](#create-fragments)的任何功能來編輯片段。

## 重複片段

您可以使用以下任一方法復製片段：

* 從&#x200B;_[!UICONTROL 片段]_&#x200B;清單頁面，按一下片段名稱旁的&#x200B;_更多_ (**...**)圖示，然後選擇&#x200B;**[!UICONTROL 複製]**。
* 在片段詳細資料頁面的右上方，按一下&#x200B;**[!UICONTROL ...更多]**&#x200B;並選擇&#x200B;**[!UICONTROL 複製]**。

![復製片段](./assets/fragment-details-duplicate.png){width="600" zoomable="yes"}

在對話方塊中，輸入有用的名稱（唯一）和說明。 按一下&#x200B;**[!UICONTROL 複製]**&#x200B;以完成動作。

![輸入複製的片段的名稱和描述](./assets/fragment-duplicate-dialog.png){width="400"}

然後，重複的（新）片段會出現在&#x200B;_片段_&#x200B;清單中。

## 從電子郵件或範本內容儲存片段

在視覺內容編輯器中建立/編輯電子郵件或電子郵件範本時，您可以選擇將內容的所有或部分儲存為片段，以便重複使用。

1. 當您將某些內容儲存為片段時，請按一下[其他] ****，然後選擇[另存為片段] ]**。**[!UICONTROL 

1. 選取要包含在片段中的不同元素。

   按住Shift或Control按鈕，選取多個結構。

   您只能選取彼此相鄰的結構，而且介面不允許您選取不相鄰的元素。

1. 選取內容後，按一下右上角的&#x200B;**[!UICONTROL 建立]**。

1. 在對話方塊中，輸入片段的實用名稱和說明。 然後按一下&#x200B;**[!UICONTROL 建立]**。

   然後，新片段會顯示在&#x200B;_片段_&#x200B;清單頁面中，也可在電子郵件和電子郵件範本中使用。

## 將視覺化片段新增至您的電子郵件或範本內容

片段是專為重複使用而設計，可插入以用於電子郵件和電子郵件範本的製作。 您最多可以在電子郵件或範本中新增30個片段。 片段最多只能巢狀內嵌一個層級。

>[!BEGINTABS]

>[!TAB 新增片段至電子郵件]

1. 導覽至&#x200B;**[!UICONTROL 帳戶歷程]**&#x200B;並開啟現有歷程或建立新歷程。

1. 建立[_[!UICONTROL 傳送電子郵件&#x200B;]_節點](./email-authoring.md#add-an-email-action-in-an-account-journey)。

1. 建立或編輯節點](./email-authoring.md#create-the-email-content)的[電子郵件內容。

1. 從&#x200B;**[!UICONTROL 元件]**&#x200B;功能表拖放專案，以提供片段的&#x200B;_結構_。

1. 若要開啟已發佈片段的清單，請按一下&#x200B;_片段_&#x200B;圖示。

   您可以：
   * 排序清單。
   * 瀏覽、搜尋及篩選清單。
   * 在卡片（縮圖）和清單檢視之間切換。
   * 重新整理清單以反映任何最近建立的片段。

   ![在視覺化設計工具中搜尋片段](./assets/fragments-list-designer-search.png){width="600"}

1. 將任何片段拖放至結構元件預留位置。

   編輯器會在電子郵件結構的區段/元素中轉譯片段。

片段的內容會在結構內動態更新，以呈現內容在電子郵件中如何顯示的視覺效果。

>[!TIP]
>
>如果您希望片段佔據電子郵件內的整個水準版面，請新增[!UICONTROL 1:1欄]結構，然後將片段拖放到其中。

儲存電子郵件後，選取&#x200B;_[!UICONTROL 使用者]_&#x200B;索引標籤時，它就會顯示在片段詳細資訊頁面中。 新增到電子郵件的片段在電子郵件或範本中無法編輯 — 發佈的來源片段會定義內容。

>[!TAB 新增片段至電子郵件範本]

1. 從左側導覽列按一下&#x200B;**[!UICONTROL 內容管理]** > **[!UICONTROL 範本]**。

1. 建立新範本，或開啟現有的電子郵件範本，然後按一下[編輯電子郵件範本]。****

1. 從&#x200B;**[!UICONTROL 元件]**&#x200B;功能表拖放專案，以提供片段的&#x200B;_結構_。

1. 若要開啟片段清單，請按一下&#x200B;_片段_&#x200B;圖示。

   您可以：
   * 排序清單。
   * 瀏覽、搜尋及篩選清單。
   * 在卡片（縮圖）和清單檢視之間切換。
   * 重新整理清單以反映任何最近建立的片段。

   ![在視覺化設計工具中搜尋片段](./assets/fragments-list-designer-search.png){width="600"}

1. 將任何片段拖放至結構元件預留位置。

   編輯器會在電子郵件範本結構的區段/元素中轉譯片段。

1. 將任何片段拖放至結構元件預留位置。

   編輯器會在電子郵件範本結構的區段/元素中轉譯片段。

>[!TIP]
>
>如果您希望片段佔據電子郵件範本內的整個水準配置，請新增&#x200B;_[!UICONTROL 1:1欄]_&#x200B;結構，然後將片段拖放到其中。

儲存電子郵件範本後，選取&#x200B;_[!UICONTROL 使用者]_&#x200B;索引標籤時，其會出現在片段詳細資訊頁面中。 新增到電子郵件範本的片段在範本中無法編輯 — 發佈的來源片段會定義內容。

>[!ENDTABS]

## 電子郵件和範本製作期間的片段動作

將片段新增至電子郵件或電子郵件範本時，無法在電子郵件或範本中編輯片段內容。 不過，您可以套用下列動作：

* **[!UICONTROL 刪除]** — 此動作會從目前的電子郵件或電子郵件範本內容移除片段（片段來源不受影響）。
* **[!UICONTROL 重新整理]** — 此動作會重新整理目前電子郵件或電子郵件範本中的片段內容。 當您想要反映新增到電子郵件或電子郵件範本後對片段的任何最近編輯時，重新整理會很有用。
* **[!UICONTROL 複製]** — 此動作會複製編輯器內相同電子郵件或電子郵件範本中的片段（使用相同的維度），並在其下方新增。
* **[!UICONTROL 開啟片段]** — 此動作會開啟新的瀏覽器索引標籤，其中包含片段編輯器頁面和詳細資訊。
* **[!UICONTROL 中斷繼承]** — 此動作會中斷來自來源的片段繼承（及其變更）。 使用此動作，在電子郵件或電子郵件範本中讓片段內容成為獨立且可編輯的內容。 此動作也會從原始片段的&#x200B;_使用者_&#x200B;參考中移除電子郵件或電子郵件範本。

在編輯器頁面上選取片段時，可以從右側的內容工具列和屬性面板中取得這些動作。

![套用動作至選取的片段](./assets/fragment-actions-email-authoring.png){width="600" zoomable="yes"}