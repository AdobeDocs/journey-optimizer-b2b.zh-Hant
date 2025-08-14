---
title: 帳戶受眾節點
description: 瞭解可用於在Journey Optimizer B2B edition中定義帳戶歷程輸入的帳戶對象節點型別。
feature: Account Journeys, Audiences, Account Lists
role: User
exl-id: 288ac5a8-79ed-4654-8ac1-83da2af04f2c
source-git-commit: 82553c9ee6205e0ad47cc5a56112590471c03d0e
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 0%

---


# 帳戶對象歷程節點

帳戶對象節點會指定哪些帳戶進入歷程。 當您[建立帳戶歷程](./journey-overview.md#create-an-account-journey)時，歷程一律以定義其輸入的帳戶對象節點開始。

對此歷程節點使用下列其中一個輸入選項：

* **[帳戶對象](../audiences/account-audience-overview.md)** — 帳戶對象代表從Experience Platform Segmentation Service同步的基本對象。
* **[帳戶清單](../accounts/account-lists.md)** — 帳戶清單是您用於目標歷程協調的具名帳戶集合。 帳戶會使用定義的條件（例如產業、地點或公司規模）列出具名帳戶的目標。

## 設定帳戶對象節點的對象

1. 按一下&#x200B;**[!UICONTROL 帳戶對象]**&#x200B;節點。 此動作會在右側顯示節點屬性。

   ![帳戶對象歷程節點](./assets/account-journey-account-audience-node.png){width="700" zoomable="yes"}

1. 選擇進入歷程的帳戶的輸入型別：

   * **[!UICONTROL 帳戶對象]**

     選擇帳戶對象選項。 然後，按一下&#x200B;**[!UICONTROL 新增帳戶對象]**。

     在&#x200B;_[!UICONTROL 新增對象]_&#x200B;對話方塊中，選取先前建立的對象區段。 然後，按一下&#x200B;**[!UICONTROL 新增對象]**。

     ![選取節點的對象區段](./assets/node-audience-add-dialog.png){width="700" zoomable="yes"}

   * **[!UICONTROL 帳戶清單]**

     選擇帳戶清單選項。 按一下&#x200B;**[!UICONTROL 新增帳戶清單]**。

     在&#x200B;_[!UICONTROL 選取即時帳戶清單]_&#x200B;對話方塊中，選取已發佈的帳戶清單。 然後，按一下&#x200B;**[!UICONTROL 儲存]**。

     ![選取節點的即時帳戶清單](./assets/account-journey-account-audience-select-account-list.png){width="700" zoomable="yes"}

     如需建立與發佈帳戶清單的詳細資訊，請參閱[帳戶清單](../accounts/account-lists.md)。

## 建立對象區段

1. 在左側導覽中，選取&#x200B;**[!UICONTROL 帳戶]** > **[!UICONTROL 對象]**。

1. 按一下右上角的&#x200B;**[!UICONTROL 建立對象]**。

   ![建立對象區段](./assets/audiences-list-create.png){width="800" zoomable="yes"}

1. 請依照[Segmentation Service指南](https://experienceleague.adobe.com/zh-hant/docs/ experience-platform/segmentation/types/account-audiences){target="_blank"}中的步驟操作。
