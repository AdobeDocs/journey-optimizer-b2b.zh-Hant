---
title: 帳戶歷程
description: 了解帳戶歷程，以及如何建立和管理帳戶歷程。
feature: Account Journeys
exl-id: 5c22f11f-1967-4b55-8aee-16371173c040
source-git-commit: bd6f998b610c6f3a4d7c0e1fce5db4bb72b8a1e3
workflow-type: tm+mt
source-wordcount: '1022'
ht-degree: 30%

---


# 帳戶歷程

透過客戶歷程，您可以簡化需求產生和購買群組資格，並針對您的收購、向上銷售/交叉銷售和保留計畫推動更多符合資格的需求。 使用電子郵件、簡訊、活動等的自動化參與，為每個購買群組和購買群組成員量身打造您的歷程。

定義銷售導向的參與度機制，涵蓋電子郵件、簡訊以及更多內部帳戶歷程，以協調每個購買群組成員的集客式行銷和推播式銷售活動。

![影片](../../assets/do-not-localize/icon-video.svg){width="30"} [觀看概觀影片](#overview-video)

## 開始使用歷程

若要開始使用帳戶歷程：

1. [建立歷程](./create-publish-journey.md#create-an-account-journey)。
1. 在歷程圖中[新增節點](./create-publish-journey.md#add-a-node)，並[定義歷程流程圖](./create-publish-journey.md#add-and-delete-a-path)。
1. [發佈此歷程](./create-publish-journey.md#publish-an-account-journey)。

## 存取並瀏覽帳戶歷程

1. 在 Adobe Experience Platform 首頁，按一下「Adobe Journey Optimizer B2B Edition」。

1. 在左側導覽中，按一下「**[!UICONTROL 帳戶歷程]**」。

   ![存取帳戶歷程](./assets/account-journey-browse.png){width="800" zoomable="yes"}

   顯示的歷程頁面包括下列欄：

   * [!UICONTROL 名稱] （按一下名稱以開啟歷程進行編輯）
   * [!UICONTROL 狀態]
   * [!UICONTROL 說明]
   * [!UICONTROL 建立者]
   * [!UICONTROL 上次更新日期]
   * [!UICONTROL 上次更新者]
   * [!UICONTROL 發佈日期]
   * [!UICONTROL 發佈者]

使用頂端的&#x200B;_搜尋_&#x200B;工具，依名稱尋找歷程。 您可以按一下欄標題，依&#x200B;_[!UICONTROL 狀態]_&#x200B;來排序清單。

您可以按一下右上角的&#x200B;_自訂表格_ （ ![自訂表格](../assets/do-not-localize/icon-column-settings.svg) ）圖示，以自訂表格中顯示的欄。 選取或清除對話方塊中的核取方塊，然後按一下&#x200B;**[!UICONTROL 套用]**。

![選擇要在帳戶歷程清單中顯示的欄](./assets/account-journeys-list-columns.png){width="800" zoomable="yes"}

## 帳戶歷程剖析

按一下「_[!UICONTROL 帳戶歷程]_」清單中的名稱 (顯示為連結) 來檢視其詳細資訊、進行變更及採取動作。

![帳戶歷程工作區](./assets/account-journey-workspace.png){width="800" zoomable="yes"}

每個帳戶歷程地圖的標題包括：

* 歷程名稱
* 存取以編輯歷程名稱（![編輯圖示](../assets/do-not-localize/icon-edit.svg) _編輯_&#x200B;圖示）
* 歷程狀態

歷程的狀態可根據您套用的動作而變更。 根據歷程的狀態，某些動作無法從標題右側使用。

| 狀態 | 說明 | 可用的動作 |
| ------ | ----------- | ----------------- |
| _**草稿**_ | 未發佈且可以編輯的歷程。 | <ul><li>[發佈](./create-publish-journey.md#publish-an-account-journey)</li><li>重複 </li><li>刪除 </li></ul> |
| _**已上線**_ | 歷程發佈後，歷程狀態會從「草稿」變更為「已上線」。在此狀態下，您將無法編輯歷程。 | <ul><li>重複 </li><li>對新進客戶關閉 </li><li>中止 </li></ul> |
| _**對新進客戶關閉**_ | 當您在頂端導覽區域按一下「[!UICONTROL 對新進客戶關閉]」，此歷程狀態會從「_已上線_」變更為「_對新進客戶關閉_」。 | <ul><li>重複 </li><li>中止 </li></ul> |
| _**已中止**_ | 中止歷程時，原本的「_已上線_」或「_對新進客戶關閉_」歷程狀態將會發生變更。中止的歷程無法重新啟動。 | <ul><li>重複 </li><li>刪除 </li></ul> |
| _**已完成**_ | 當歷程中的所有帳戶均完成此歷程時，其狀態會從「已上線」或「對新進客戶關閉」變更為「已完成」。 | <ul><li>重複 </li><li>刪除 </li></ul> |

## 管理歷程

_帳戶歷程_&#x200B;清單包含Journey Optimizer B2B edition執行個體中的所有歷程。

### 中止歷程

如果您中止（停止）即時或排程的歷程，歷程中的帳戶會立即停止進度，而且可能不會發生進一步的歷程入口。 中止的歷程無法重新啟動。

>[!IMPORTANT]
>
>當帳戶歷程用於來自&#x200B;_採取動作_&#x200B;節點且&#x200B;_將帳戶新增至（其他）歷程_&#x200B;動作的另一個歷程時，將中止該歷程封鎖該歷程的動作。

1. 按一下歷程名稱以開啟。

1. 按一下右上方的&#x200B;**[!UICONTROL 更多……]**&#x200B;功能表，然後選擇&#x200B;**[!UICONTROL 中止]**。

   ![按一下右上角的[更多]](./assets/account-journey-live-more-menu.png){width="450"}

1. 在確認對話方塊中，按一下&#x200B;**[!UICONTROL 中止]**。

### 對新進客戶關閉

如果您關閉即時歷程，目前處於歷程中的帳戶會繼續其在歷程中的路徑，且不會發生進一步的歷程入口。 已關閉的歷程無法重新啟動。您可以重複已關閉的歷程。

>[!IMPORTANT]
>
>當帳戶歷程用於來自&#x200B;_採取動作_&#x200B;節點並具有&#x200B;_將帳戶新增至（其他）歷程_&#x200B;動作，將它關閉至該歷程中該動作的新專案區塊時。

1. 按一下歷程名稱以開啟。

1. 按一下右上方的&#x200B;**[!UICONTROL 更多……]**&#x200B;功能表，然後選擇&#x200B;**[!UICONTROL 關閉新專案]**。

1. 在確認對話方塊中，按一下&#x200B;**[!UICONTROL 關閉新專案]**。

### 複製歷程

重複動作類似於複製函式，但重複的歷程不包含任何建立的歷程內容資產。 您可以複製帳戶歷程的詳細資料，或只是流量和路徑結構的簡單&#x200B;_骨架_。

1. 按一下歷程名稱旁的&#x200B;_更多_&#x200B;圖示(**...**)，然後選擇&#x200B;**[!UICONTROL 複製]**。

   ![按一下……圖示並選擇[複製]](./assets/account-journeys-list-more-menu.png){width="450"}

   根據帳戶歷程的狀態，您還可以從歷程詳細資訊或歷程地圖存取重複的動作：

   * 若要草稿歷程，請按一下右上方的&#x200B;**[!UICONTROL 更多……]**&#x200B;功能表，然後選擇&#x200B;**[!UICONTROL 複製]**。

   * 若為所有其他歷程狀態，請按一下右上方的&#x200B;**[!UICONTROL 複製]**。

     ![按一下右上角的[複製]](./assets/account-journey-duplicate-button.png){width="450"}

1. 在&#x200B;_重複的歷程_&#x200B;對話方塊中，設定新歷程的&#x200B;**[!UICONTROL 名稱]**&#x200B;和&#x200B;**[!UICONTROL 描述]**。

   依照預設，對話方塊會使用附加__副本_&#x200B;的重複歷程名稱。 視需要為歷程輸入另一個唯一名稱。

   ![重複的歷程對話方塊](./assets/account-journey-duplicate-dialog.png){width="400"}

1. 選擇重複&#x200B;**[!UICONTROL 型別]**：

   * **[!UICONTROL 部分內容複製]** — 使用此型別複製歷程中的所有內容，不包括任何已建立的電子郵件或簡訊。 參考Marketo Engage電子郵件或簡訊訊息的節點完整無損。

   * **[!UICONTROL 複製但不含詳細資料]** — 使用此型別僅複製節點結構和路徑。 所有節點設定和路徑條件皆未定義（預設），因此您可以使用不同的對象、動作和路徑分段設定來重複使用基本流程。 所有&#x200B;_等待_&#x200B;節點都使用預設的5天。

1. 按一下&#x200B;**[!UICONTROL 複製]**。

   重複的帳戶歷程會在歷程地圖中開啟，您可以在其中設定詳細資訊，並視需要建立歷程內容。

### 刪除歷程

使用刪除動作永久刪除歷程。 您無法刪除即時或排程歷程。

1. 按一下歷程名稱旁的&#x200B;_更多_&#x200B;圖示(**...**)，然後選擇&#x200B;**[!UICONTROL 刪除]**。

   根據帳戶歷程的狀態，您也可以從歷程詳細資訊或歷程地圖存取刪除動作：

   * 若要草稿歷程，請按一下右上方的&#x200B;**[!UICONTROL 更多……]**&#x200B;功能表，然後選擇&#x200B;**[!UICONTROL 刪除]**。

   * 若是其他歷程狀態，例如&#x200B;_已完成_&#x200B;或&#x200B;_已中止_，請按一下右上方的&#x200B;**[!UICONTROL 刪除]**。

1. 在確認對話方塊中，按一下&#x200B;**[!UICONTROL 刪除]**。

## 概觀影片

>[!VIDEO](https://video.tv.adobe.com/v/3443202/?learn=on)
