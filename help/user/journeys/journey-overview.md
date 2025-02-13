---
title: 帳戶歷程
description: 瞭解帳戶歷程，以及如何建立和管理它們。
feature: Account Journeys
exl-id: 5c22f11f-1967-4b55-8aee-16371173c040
source-git-commit: d03e0e2d8070916d38bb956adff8dea3f3873aad
workflow-type: tm+mt
source-wordcount: '575'
ht-degree: 2%

---


# 帳戶歷程

使用電子郵件、簡訊、活動等自動參與功能，建置並執行為每個購買群組和購買群組成員量身打造的歷程。 WIth客戶歷程，您可以簡化需求產生和購買群組資格，並針對您的收購、追加銷售/交叉銷售和保留計畫推動更多合格需求。

定義包括電子郵件、簡訊等內部帳戶歷程的銷售導向參與，以協調每個購買群組成員的傳入行銷與傳出銷售活動。

![影片](../../assets/do-not-localize/icon-video.svg){width="30"} [觀看概觀影片](#overview-video)

## 存取和瀏覽帳戶歷程

1. 在Adobe Experience Platform首頁中，按一下Adobe Journey Optimizer B2B edition。

1. 在左側導覽中，按一下&#x200B;**[!UICONTROL 帳戶歷程]**。

   ![存取帳戶歷程](./assets/account-journey-browse.png){width="800" zoomable="yes"}

   顯示的歷程頁面包含下列欄：

   * [!UICONTROL 名稱] （按一下名稱以開啟帳戶歷程以進行編輯）
   * [!UICONTROL 狀態]
   * [!UICONTROL 說明]
   * [!UICONTROL 建立者：]
   * [!UICONTROL 上次更新時間：]
   * [!UICONTROL 上次更新者]
   * [!UICONTROL 發佈於]
   * [!UICONTROL 發佈者]

此表格包含依名稱和建立者搜尋的功能。 排序目前無法使用。

您可以按一下右上角的&#x200B;_欄_&#x200B;圖示並選取或清除核取方塊，以自訂顯示的表格。

![選擇要顯示在帳戶歷程清單中的資料行](./assets/account-journeys-list-columns.png){width="800" zoomable="yes"}

## 帳戶歷程剖析

按一下&#x200B;_[!UICONTROL 帳戶歷程]_&#x200B;清單中的名稱（顯示為連結），即可檢閱詳細資料、進行變更以及執行動作。

![帳戶歷程工作區](./assets/account-journey-workspace.png){width="800" zoomable="yes"}

每個帳戶歷程的編輯器標題包括：

* 歷程名稱
* 可編輯名稱（_編輯_&#x200B;圖示）
* 歷程的狀態

標頭中有以下動作：

* **發佈** — 如果沒有封鎖程式錯誤，您可以發佈歷程。 發佈後，歷程狀態會變更為&#x200B;_即時_。 如果歷程發生錯誤，按鈕會以灰色顯示內容資訊： `Resolve errors before publishing`。
* **複製** — 此動作類似於複製函式，但複製的歷程不包含任何資產。
* **關閉新專案** — 如果您關閉歷程，目前歷程中的帳戶會繼續其在歷程中的路徑，且無法進一步進入歷程。 無法重新啟動已關閉的歷程。 您可以複製已關閉的歷程。
* **中止** — 如果您停止歷程，歷程中的帳戶會立即停止進度，而且無法進入進一步的歷程。 停止的歷程無法重新啟動。 如果您封鎖新入口而不停止人們的進度，請考慮改為關閉歷程。
* **刪除** — 此動作會永久刪除歷程。

歷程的狀態會根據您套用的動作而變更。 根據歷程的狀態，某些動作在/無法在標題中使用。

| 狀態 | 說明 | 可用動作 |
| ------ | ----------- | ----------------- |
| _**草稿**_ | 可編輯的未發佈歷程。 | <ul><li>發佈</li><li>複製 </li><li>刪除 </li></ul> |
| _**即時**_ | 發佈歷程時，歷程狀態從草稿變更為即時。 在此狀態下，將無法再編輯它。 | <ul><li>複製 </li><li>關閉新專案 </li><li>中止 </li></ul> |
| _**已關閉新專案**_ | 當您在頂端導覽中按一下[!UICONTROL 關閉新專案]時，歷程狀態會從&#x200B;_即時_&#x200B;變更為&#x200B;_已關閉新專案_。 | <ul><li>複製 </li><li>中止 </li></ul> |
| _**已中止**_ | 當您中止歷程時，歷程狀態從&#x200B;_即時_&#x200B;或&#x200B;_已關閉新專案_&#x200B;變更。 中止的歷程無法重新啟動。 | <ul><li>複製 </li><li>刪除 </li></ul> |
| _**已完成**_ | 當歷程中的所有帳戶完成歷程時，狀態會從「即時」或「已關閉」變更為新專案，即「已完成」。 | <ul><li>複製 </li><li>刪除 </li></ul> |

## 開始使用歷程

若要開始使用帳戶歷程：

1. [建立歷程](./create-publish-journey.md#create-an-account-journey)。
1. [新增節點](./create-publish-journey.md#add-a-node)並在歷程地圖中定義[歷程流程](./create-publish-journey.md#add-and-delete-a-path)。
1. [發佈歷程](./create-publish-journey.md#publish-an-account-journey)。

## 概述影片

>[!VIDEO](https://video.tv.adobe.com/v/3443202/?learn=on)
